# Configuration of common developer CLI tools with Cloudflare WARP

This article explains how to configure common developer CLI tools so they work correctly when Cloudflare WARP is enabled on a SEED-managed device.

The instructions ensure the Cloudflare CA certificate is trusted while keeping the standard public CA bundle intact.

> **Note**  
> - Tools listed here are commonly used by software developers in Singapore Government agencies.  
> - To configure other applications or tools, refer to the [Cloudflare documentation](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert).  
> - If you are experiencing issues while using any CLI tools and applications to access SGTS services, [create a support request](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/raise-service-request).  
> - For issues that are not related to SGTS services, contact the [Cloudflare Community Support Forums](https://support.cloudflare.com/hc/en-us).

---

## What this guide covers

Use this guide if Cloudflare WARP is enabled and you encounter any of the following issues:

1. TLS or HTTPS connection errors on a macOS host  
2. TLS or HTTPS connection errors inside a Linux virtual machine (including when pulling Docker images)  
3. TLS or HTTPS connection errors when building container images locally  

---

## Before you begin

Most developer tools require access to:

- The standard public CA bundle (for example, Mozilla public CAs)  
- The Cloudflare CA certificate used by SEED or SGTS TLS inspection  

On macOS, many tools trust the system keychain by default. Others require environment variables or manual imports.

On Linux (including VMs and containers), you must install the Cloudflare CA into the correct system trust store and configure tool-specific certificate variables if needed.

This guide stores downloaded certificates under:

```text
${HOME}/.config/cloudflare/
```

If you previously used `${HOME}/.config/.cloudflare/`, both formats work. Update your shell paths accordingly.

---

## macOS hosts

### Initial setup (required)

Run these commands in your macOS terminal:

```bash
mkdir -p "${HOME}/.config/cloudflare/"

curl -fsS -o "${HOME}/.config/cloudflare/Cloudflare_CA.pem"   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"

curl -fsS --cacert "${HOME}/.config/cloudflare/Cloudflare_CA.pem"   -o "${HOME}/.config/cloudflare/mozilla-bundle.pem"   "https://mkcert.org/generate/"

cat "${HOME}/.config/cloudflare/mozilla-bundle.pem" > "${HOME}/.config/cloudflare/combined-bundle.pem"
cat "${HOME}/.config/cloudflare/Cloudflare_CA.pem" >> "${HOME}/.config/cloudflare/combined-bundle.pem"
```

You will now have:

- `Cloudflare_CA.pem` → Cloudflare CA used by SEED inspection  
- `mozilla-bundle.pem` → Standard public CA root bundle  
- `combined-bundle.pem` → Combined bundle containing both the public CAs and the Cloudflare CA  

If your default shell is zsh (the macOS default), you will add environment variables to `${HOME}/.zshrc` in the following sections, then run:

```bash
source "${HOME}/.zshrc"
```

---

### Node.js (npm, pnpm, yarn)

#### Recommended configuration

```bash
echo 'export NODE_EXTRA_CA_CERTS="${HOME}/.config/cloudflare/Cloudflare_CA.pem"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

#### Alternative (newer Node versions)

```bash
echo 'export NODE_OPTIONS="--use-system-ca"' | tee -a "${HOME}/.zshrc"
echo 'export NODE_USE_SYSTEM_CA=1' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

#### Do not

Do not configure npm to trust only Cloudflare (`npm config set cafile`) because this overrides the public CA store. If needed, point `cafile` at the combined bundle instead.

---

### Python (including pip, uv)

#### Recommended configuration

```bash
echo 'export SSL_CERT_FILE="${HOME}/.config/cloudflare/combined-bundle.pem"' | tee -a "${HOME}/.zshrc"
echo 'export REQUESTS_CA_BUNDLE="${HOME}/.config/cloudflare/combined-bundle.pem"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

#### Notes

- `requests` 2.x respects `REQUESTS_CA_BUNDLE` or `CURL_CA_BUNDLE` but not `SSL_CERT_FILE`.  
- `pip` 24.2+ with Python 3.10+ checks the macOS keychain by default. Older versions may need configuration using `PIP_CERT` or bundle environment variables.  
- `uv` can use `SSL_CERT_FILE` or set `UV_NATIVE_TLS=true`.

---

### Go

Recent Go binaries trust the macOS keychain by default and should not need extra configuration.

If you encounter DNS resolution errors with a Go tool, ensure the binary was built with cgo enabled to support the system DNS resolver behind VPNs.

---

### JVM tools (Maven, Gradle)

#### Recommended configuration

```bash
"$JAVA_HOME/bin/keytool" -import   -file "${HOME}/.config/cloudflare/Cloudflare_CA.pem"   -alias CloudflareRootCA   -keystore "${JAVA_HOME}/lib/security/cacerts"   -storepass changeit -trustcacerts -noprompt
```

Repeat this for each JVM installation that requires the certificate.

#### Alternative (may vary)

```bash
echo 'export JAVA_TOOL_OPTIONS="-Djavax.net.ssl.trustStoreType=KeychainStore"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

This option may not be supported universally. If it fails, import the certificate manually using `keytool`.

---

### Docker

#### Docker via Colima

If you see TLS errors when pulling images via Colima, install the CA inside the Colima VM:

```bash
colima ssh -- sudo curl -fsS -o /usr/local/share/ca-certificates/Cloudflare_CA.crt   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"

colima ssh -- sudo update-ca-certificates
colima restart
```

#### Private registry on host

For private registries under WARP inspection, add the Cloudflare CA under `certs.d`:

```bash
mkdir -p "${HOME}/.docker/certs.d/registry-in.ship.gov.sg"
curl -fsS -o "${HOME}/.docker/certs.d/registry-in.ship.gov.sg/ca.crt"   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"
```

Restart Docker after saving the certificate.

> **Tip**  
> For production-ready Docker images, consider building using [SHIP-HATS CI/CD](https://www.ship.gov.sg) instead of a local SEED device.

---

### Git

Git relies on curl for HTTPS connections on macOS, which trusts the macOS keychain by default.

No configuration is needed unless you use a custom curl build that does not support keychain trust. In that case, configure curl as described in the next section.

---

### Curl

The default macOS curl and Homebrew curl trust the macOS keychain by default and should work.

If your curl binary does not trust the keychain (for example, installed by Anaconda), set:

```bash
echo 'export SSL_CERT_FILE="${HOME}/.config/cloudflare/combined-bundle.pem"' | tee -a "${HOME}/.zshrc"
# or
echo 'export CURL_CA_BUNDLE="${HOME}/.config/cloudflare/combined-bundle.pem"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

---

### Wget

#### Recommended configuration

```bash
echo 'export SSL_CERT_FILE="${HOME}/.config/cloudflare/combined-bundle.pem"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

#### Alternative `.wgetrc`

```text
ca_certificate = ${HOME}/.config/cloudflare/combined-bundle.pem
```

---

### AWS CLI (v1 and v2)

#### Recommended configuration

```bash
echo 'export AWS_CA_BUNDLE="${HOME}/.config/cloudflare/combined-bundle.pem"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"
```

#### Do not

Do not point AWS CLI’s CA only to `Cloudflare_CA.pem`, because AWS API endpoints still require the public CA bundle.

---

### Kubectl

If your Kubernetes API server requires mutual TLS using a client certificate, Cloudflare TLS interception may break the connection.

Recommended alternatives:

- Use `kubectl` from a jumphost or cloud administration device that does not go through TLS inspection.  
- If you must use a SEED-managed device, speak to the SEED team to request Do-Not-Inspect (DNI) on the relevant DNS name to bypass TLS inspection.

---

### Rust-based tools (for example uv, Railway CLI)

Rust CLI tools do not have a universal certificate trust configuration.

- Tools using `reqwest` with `rustls-tls` typically include WebPKI roots but ignore the system keychain.  
- To add system root support, they must be rebuilt with the `rustls-tls-native-roots` feature.

Known limitation:

- Railway CLI (current versions) does not support macOS keychain trust or manual CA bundling unless rebuilt from source. Treat this as a known limitation.

---

## Linux virtual machines (including WSL)

These steps apply when you run a Linux VM (for example, local VM, WSL, Colima VM) and see TLS errors inside the VM.

### Debian and Ubuntu

Run inside your Linux VM:

```bash
sudo curl -fsS -o /usr/local/share/ca-certificates/Cloudflare_CA.crt   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"
sudo update-ca-certificates
```

### CentOS and RHEL

```bash
sudo curl -fsS -o /usr/share/pki/ca-trust-source/anchors/Cloudflare_CA.pem   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"
sudo update-ca-trust
```

### Alpine, Wolfi, and Chainguard

If `wget` is available:

```bash
wget --no-check-certificate -q -O -   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"   >> /etc/ssl/certs/ca-certificates.crt
```

If only `curl` is available:

```bash
curl -fsS   "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"   >> /etc/ssl/certs/ca-certificates.crt
```

---

## Container builds

### Overview

- Add the Cloudflare CA only to builder stages in multi-stage Docker builds.  
- Avoid copying the Cloudflare CA into the final runtime image unless required at runtime for network calls.

---

### Debian and Ubuntu-based images (builder stage)

```dockerfile
RUN   curl -fsS -o /usr/local/share/ca-certificates/Cloudflare_CA.crt     "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"   && update-ca-certificates
```

---

### Alpine, Wolfi, and Chainguard images (builder stage)

```dockerfile
RUN   apk --no-cache --no-check-certificate add wget   && wget --no-check-certificate -q -O -     "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"     >> /etc/ssl/certs/ca-certificates.crt   && apk del wget
```

---

### RHEL and UBI images (builder stage)

```dockerfile
RUN   curl -fsS -o /usr/share/pki/ca-trust-source/anchors/Cloudflare_CA.pem     "https://seed-general-public-files.s3.ap-southeast-1.amazonaws.com/seed-cloudflare-root-certs/Cloudflare_CA.pem"   && update-ca-trust
```

---

## Additional examples: AWS SDK

### AWS SDK for JavaScript (v2)

```js
import { readFileSync } from "fs";
import { Agent } from "https";
import { config } from "aws-sdk";

const certs = [readFileSync("/path/to/combined-bundle.pem")];

config.update({
  httpOptions: {
    agent: new Agent({ ca: certs }),
  },
});
```

---

## Support

If TLS or HTTPS errors persist after configuration:

- For SEED issues, raise a [support request](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/raise-service-request).  
- For other issues, use the [Cloudflare Community Support Forums](https://support.cloudflare.com/hc/en-us).
