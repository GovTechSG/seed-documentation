# How to clone a Bitbucket repository using SSH with Cloudflare Access

**Prerequisites**

- If you are using an internet device which is a non-GSIB or non-DWP device, [onboard it to SEED](onboard-device/onboard-device-to-seed).
- [Verify if you have an existing SSH key pair](https://confluence.atlassian.com/bitbucketserver0717/creating-ssh-keys-1087535541.html#CreatingSSHkeys-1.CheckforexistingSSHkeys). If it is available, [add the SSH key in Bitbucket](https://bitbucket.ship.gov.sg/plugins/servlet/ssh/account/keys).
- If you don't have an SSH key pair, [generate SSH key pair](https://confluence.atlassian.com/bitbucketserver0717/creating-ssh-keys-1087535541.html#) and then add it in Bitbucket.
- You should know how to setup and use ssh together with Git.

**To clone Bitbucket repository using SSH with Cloudflare Access**

<!-- tabs:start -->

## **macOS**

1. Open **Terminal** and use the following command to install `cloudflared` via Homebrew.

```

$ brew install cloudflare/cloudflare/cloudflared

```
> **Note**:
> you don't need to wrap your SSH commands in any unique way. You just need to make a ome-time change to your SSH configuration.

1. To make a one-time change to your SSH configuration file, use `vim ~/.ssh/config`.
1. Append the following lines:

```
Host bitbucket-ssh.ship.gov.sg
  ProxyCommand /usr/local/bin/cloudflared access ssh --hostname %h
  IdentityFile <PATH TO YOUR SSH PRIVATE KEY> #omit this line if you're using the default id_rsa ssh key
```

> **Note**:
> If your macOS device has M1 chip, then the location of `cloudflared` could be `/opt/homebrew/bin/cloudflared`.

1. Test the SSH flow by attempting to clone the project.

```
$ git clone ssh://git@bitbucket-ssh.ship.gov.sg:7999/ship/ship-lambda-script.git

```


1. When `cloudflared` prompts you to log in, log in with TechPass.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-1.png ':size=600')

1. Authenticate your login.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-2.png ':size=600')

1. If the authentication is successful, the following messages will be displayed.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-3.png ':size=600')

The token is saved in your `~/.cloudflared` directory, and the git clone command clones the code repository.

## **Windows**

1. Depending on your Windows processor, download `cloudflared` from the following links:
  - [32-bit](https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-386.exe)
  - [64-bit](https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-amd64.exe)

1. Save the .exe file in a desired location and rename it as `cloudflared.exe`.

> **Note**:
> you don't need to wrap your SSH commands in any unique way. You just need to make a one-time change to your SSH configuration.

1. To make a one-time change to your SSH configuration file, open your ssh config file `$HOME/.ssh/config`.

> **Note**:
> If this file does not exist, create it.


1. Append the following lines:

```
Host bitbucket-ssh.ship.gov.sg
  ProxyCommand c:\path\to\cloudflared.exe access ssh --hostname %h
  IdentityFile <PATH TO YOUR SSH PRIVATE KEY>
```
1. Test the SSH flow by attempting to clone the project.

```
$ git clone ssh://git@bitbucket-ssh.ship.gov.sg:7999/ship/ship-lambda-script.git

```



1. When `cloudflared` prompts you to log in, log in with TechPass.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-1.png  ':size=600')

1. Authenticate your login.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-2.png ':size=600')

1. If the authentication is successful, the following messages will be displayed.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-3.png ':size=600')

The token is saved in your `~/.cloudflared` directory, and the git clone command clones the code repository.
<!-- tabs:end -->