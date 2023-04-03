# How to clone a Bitbucket repository using SSH with Cloudflare Access

The following instructions guide you to clone Git repos through SSH from https://bitbucket.ship.gov.sg using Cloudflare tunnel. 

>**Note**:
> If you are cloning repos from [SHIP-HATS 2.0 GitLab](https://sgts.gitlab-dedicated.com), use your existing Git client without creating any Cloudflare tunnel. 

**Prerequisites**

- If you are using an Internet Device, [onboard it to SEED](onboard-device/onboard-device-to-seed).
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
> You don't need to wrap your SSH commands in any unique way. You just need to make a one-time change to your SSH configuration.

2. To make a one-time change to your SSH configuration file, use `vim ~/.ssh/config`.
3. Append the following lines:

```
Host bitbucket-ssh.ship.gov.sg
  ProxyCommand /usr/local/bin/cloudflared access ssh --hostname %h
  IdentityFile <PATH TO YOUR SSH PRIVATE KEY> #omit this line if you're using the default id_rsa ssh key
```

> **Note**:
> If your macOS device has M1 chip, then the location of `cloudflared` could be `/opt/homebrew/bin/cloudflared`.

4. Test the SSH flow by attempting to clone the project.

```
$ git clone ssh://git@bitbucket-ssh.ship.gov.sg:7999/ship/ship-lambda-script.git

```
5. When `cloudflared` prompts you to log in, log in with TechPass.

<kbd>![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-1.png ':size=600')</kbd>

6. Authenticate your login.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-2.png ':size=600')

7. If the authentication is successful, the following messages will be displayed.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-3.png ':size=600')

The token is saved in your `~/.cloudflared` directory, and the git clone command clones the code repository.

## **Windows**

1. Depending on your Windows processor, download `cloudflared` from the following links:
  - [32-bit](https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-386.exe)
  - [64-bit](https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-amd64.exe)

2. Save the .exe file in a desired location and rename it as `cloudflared.exe`.

> **Note**:
> You don't need to wrap your SSH commands in any unique way. You just need to make a one-time change to your SSH configuration.

3. To make a one-time change to your SSH configuration file, open your ssh config file `$HOME/.ssh/config`.

> **Note**:
> If this file does not exist, create it.

4. Append the following lines:

```
Host bitbucket-ssh.ship.gov.sg
  ProxyCommand c:\path\to\cloudflared.exe access ssh --hostname %h
  IdentityFile <PATH TO YOUR SSH PRIVATE KEY>
```
5. Test the SSH flow by attempting to clone the project.

```
$ git clone ssh://git@bitbucket-ssh.ship.gov.sg:7999/ship/ship-lambda-script.git

```
6. When `cloudflared` prompts you to log in, log in with TechPass.

<kbd>![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-1.png  ':size=600')</kbd>

7. Authenticate your login.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-2.png ':size=600')

8. If the authentication is successful, the following messages will be displayed.

![cloudflare-login-success](../images/cloudflare-login-success-bitbucket-3.png ':size=600')

The token is saved in your `~/.cloudflared` directory, and the git clone command clones the code repository.
<!-- tabs:end -->
