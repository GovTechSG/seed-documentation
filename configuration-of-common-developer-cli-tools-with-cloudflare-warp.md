# Configuration of common Developer CLI tools with Cloudflare WARP

- [Node.js and NPM](#nodejs-and-npm)
- [Docker](#docker)
- [AWS CLI](#aws-cli)
- [Golang](#golang)


## Node.js and NPM


Node.js and NPM use a hardcoded certificate store and requires additional configuration to trust the Cloudflare Certificate.

For Linux & MacOS users:
```bash

cat <<-EOF | tee ~/.bash_profile

if [[ -f "~/.config/.cloudflare/Cloudflare_CA.crt" ]]; then
    mkdir -p "~/.config/.cloudflare"
    curl -sSLj -o "~/.config/.cloudflare/Cloudflare_CA.crt" https://developers.cloudflare.com/cloudflare-one/9922abcf75b55a3bb68a8e42ebe5c4a5/Cloudflare_CA.crt
    export NODE_EXTRA_CA_CERTS="~/.config/.cloudflare/Cloudflare_CA.crt"
fi

EOF
```


## Docker

Docker for Desktop makes use of virtual machines to host the Docker engine. The Docker engine must be configured to trust the Cloudflare Certificate.

Please follow the Documentation for Docker for Desktop for [Mac](https://docs.docker.com/desktop/mac/#add-tls-certificates) or [Windows](https://docs.docker.com/desktop/windows/#adding-tls-certificates) to install the Cloudflare Cert.

## AWS CLI

AWS CLI uses its own certificate store. It must be configured to trust the Cloudflare Certificate.

For Linux & MacOS users:
```bash


if [[ ! -f "${HOME}/.config/.cloudflare/cloudflare.pem" ]]; then
mkdir -p "${HOME}/.config/.cloudflare"
cat <<-EOF | tee "${HOME}/.config/.cloudflare/cloudflare.pem"
-----BEGIN CERTIFICATE-----
MIIC6zCCAkygAwIBAgIUI7b68p0pPrCBoW4ptlyvVcPItscwCgYIKoZIzj0EAwQw
gY0xCzAJBgNVBAYTAlVTMRMwEQYDVQQIEwpDYWxpZm9ybmlhMRYwFAYDVQQHEw1T
YW4gRnJhbmNpc2NvMRgwFgYDVQQKEw9DbG91ZGZsYXJlLCBJbmMxNzA1BgNVBAMT
LkNsb3VkZmxhcmUgZm9yIFRlYW1zIEVDQyBDZXJ0aWZpY2F0ZSBBdXRob3JpdHkw
HhcNMjAwMjA0MTYwNTAwWhcNMjUwMjAyMTYwNTAwWjCBjTELMAkGA1UEBhMCVVMx
EzARBgNVBAgTCkNhbGlmb3JuaWExFjAUBgNVBAcTDVNhbiBGcmFuY2lzY28xGDAW
BgNVBAoTD0Nsb3VkZmxhcmUsIEluYzE3MDUGA1UEAxMuQ2xvdWRmbGFyZSBmb3Ig
VGVhbXMgRUNDIENlcnRpZmljYXRlIEF1dGhvcml0eTCBmzAQBgcqhkjOPQIBBgUr
gQQAIwOBhgAEAVdXsX8tpA9NAQeEQalvUIcVaFNDvGsR69ysZxOraRWNGHLfq1mi
P6o3wtmtx/C2OXG01Cw7UFJbKl5MEDxnT2KoAdFSynSJOF2NDoe5LoZHbUW+yR3X
FDl+MF6JzZ590VLGo6dPBf06UsXbH7PvHH2XKtFt8bBXVNMa5a21RdmpD0Pho0Uw
QzAOBgNVHQ8BAf8EBAMCAQYwEgYDVR0TAQH/BAgwBgEB/wIBAjAdBgNVHQ4EFgQU
YBcQng1AEMMNteuRDAMG0/vgFe0wCgYIKoZIzj0EAwQDgYwAMIGIAkIBQU5OTA2h
YqmFk8paan5ezHVLcmcucsfYw4L/wmeEjCkczRmCVNm6L86LjhWU0v0wER0e+lHO
3efvjbsu8gIGSagCQgEBnyYMP9gwg8l96QnQ1khFA1ljFlnqc2XgJHDSaAJC0gdz
+NV3JMeWaD2Rb32jc9r6/a7xY0u0ByqxBQ1OQ0dt7A==
-----END CERTIFICATE-----
EOF

fi



echo 'export AWS_CA_BUNDLE="${HOME}/.config/.cloudflare/cloudflare.pem"' | tee -a ~/.bash_profile
```


```
import { readFileSync } from “fs”;
import { Agent } from “https”;
import { config } from “aws-sdk”:

const certs = [ readFileSync(“path-to-cert”) ];

config.update({
        httpOptions: {
            agent: new Agent({
                ca: certs,
            }),
        },
    });
```


## Golang
Golang on MacOS does not use the Big Sur DNS resolver by default, resulting in DNS resolution by golang binaries not being able to work with VPN clients such as OpenVPN or Cloudflare WARP. Please ensure that you build your golang binaries with cgo enabled.
