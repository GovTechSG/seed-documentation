# Configuration of common Developer CLI tools with Cloudflare WARP

- [Node.js and NPM](#nodejs-and-npm)
- [Docker](#docker)
- [AWS CLI](#aws-cli)
- [Golang](#golang)


## Node.js and NPM


Node.js and NPM use a hardcoded certificate store and requires additional configuration to trust the Cloudflare Certificate.

For Linux & MacOS users:
```bash
mkdir -p "${HOME}/.config/.cloudflare"
curl -sSLj -o "${HOME}/.config/.cloudflare/Cloudflare_CA.pem" "https://developers.cloudflare.com/cloudflare-one/static/documentation/connections/Cloudflare_CA.pem"

# If you are using MacOS or Zsh as your default terminal
echo 'export NODE_EXTRA_CA_CERTS="${HOME}/.config/.cloudflare/Cloudflare_CA.pem"' | tee -a "${HOME}/.zshrc"
source "${HOME}/.zshrc"

# If you are using Linux or Bash as your default terminal
echo 'export NODE_EXTRA_CA_CERTS="${HOME}/.config/.cloudflare/Cloudflare_CA.pem"' | tee -a "${HOME}/.bashrc"
source "${HOME}/.bashrc"
```


## Docker

Docker for Desktop makes use of virtual machines to host the Docker engine. The Docker engine must be configured to trust the Cloudflare Certificate.

Please follow the Documentation for Docker for Desktop for [Mac](https://docs.docker.com/desktop/mac/#add-tls-certificates) or [Windows](https://docs.docker.com/desktop/windows/#adding-tls-certificates) to install the Cloudflare Cert.

## AWS CLI

AWS CLI uses its own certificate store. It must be configured to trust the Cloudflare Certificate.

For Linux & MacOS users:
```bash
mkdir -p "${HOME}/.config/.cloudflare"
curl -sSLj -o "${HOME}/.config/.cloudflare/Cloudflare_CA.pem" "https://developers.cloudflare.com/cloudflare-one/static/documentation/connections/Cloudflare_CA.pem"

# If you are using MacOS or Zsh as your default terminal
echo 'export AWS_CA_BUNDLE="${HOME}/.config/.cloudflare/Cloudflare_CA.pem"' | "tee -a ${HOME}/.zshrc"
source "${HOME}/.zshrc"

# If you are using Linux or Bash as your default terminal
echo 'export AWS_CA_BUNDLE="${HOME}/.config/.cloudflare/Cloudflare_CA.pem"' | "tee -a ${HOME}/.bashrc"
source "${HOME}/.bashrc"
```



## AWS SDK


### Javascript
```js
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
