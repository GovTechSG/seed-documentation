# How to clone GitLab repository using SSH with Cloudflare Access

The following instructions guide you to clone Git repos through SSH connection from https://gitlab-in.ship.gov.sg using Cloudflare tunnel.

>**Note**:
> If you are cloning repos from [SHIP-HATS 2.0 GitLab](https://sgts.gitlab-dedicated.com), use your existing Git client without creating any Cloudflare tunnel. 


**Prerequisites**

- If you are using an Internet Device, [onboard it to SEED](onboard-device/onboard-device-to-seed).
- [Verify if you have an existing SSH key pair](https://gitlab-in.ship.gov.sg/help/user/ssh.md#see-if-you-have-an-existing-ssh-key-pair). If it is available, [add the SSH key in Gitlab](https://gitlab-in.ship.gov.sg/-/profile/keys).
- If you don't have an SSH key pair, [generate SSH key pair](https://gitlab-in.ship.gov.sg/help/user/ssh.md#generate-an-ssh-key-pair) and then add it in GitLab.
- You should know how to setup and use ssh together with Git.

> **Note**:
> Refer to [SSH key pairs](https://gitlab-in.ship.gov.sg/help/user/ssh) for additional information.

**To clone GitLab repository using SSH with Cloudflare Access**

<!-- tabs:start -->

## **macOS**

1. Open **Terminal** and use the following command to install `cloudflared` via Homebrew.

```

$ brew install cloudflare/cloudflare/cloudflared

```
> **Note**:
> you don't need to wrap your SSH commands in any unique way. You just need to make a one-time change to your SSH configuration.

2. To make a one-time change to your SSH configuration file, use `vim ~/.ssh/config`.
3. Append the following lines:

```
Host gitlab-in-ssh.ship.gov.sg
  ProxyCommand /usr/local/bin/cloudflared access ssh --hostname %h
  IdentityFile <PATH TO YOUR SSH PRIVATE KEY> #omit this line if you're using the default id_rsa ssh key
```

> **Note**:
> If your macOS device has M1 chip, then the location of `cloudflared` could be `/opt/homebrew/bin/cloudflared`.

4. Test the SSH flow by attempting to clone the project.

```
$ git clone git@gitlab-in-ssh.ship.gov.sg:gcc2.0/seed/cloudflare-support.git

```

> **Note**:
> If you're copying the clone url from the GitLab Web Interface, change the GitLab hostname from `gitlab-in.ship.gov.sg` to `gitlab-in-ssh.ship.gov.sg`.

<kbd>![clone-gitlab-repo](../images/clone-gitlab-repo-cloudflared.png ':size=600')</kbd>

5. When `cloudflared` prompts you to log in, log in with TechPass.

<kbd>![cloudflare-login-success](../images/cloudflare-login-success-1.png ':size=600')</kbd>

6. Authenticate your login.

![cloudflare-login-success](../images/cloudflare-login-success-2.png ':size=600')

7. If the authentication is successful, the following messages will be displayed.

![cloudflare-login-success](../images/cloudflare-login-success-3.png ':size=600')

The token is saved in your `~/.cloudflared` directory, and the git clone command clones the code repository.


## **Windows**

1. Depending on your Windows processor, download `cloudflared` from the following links:
  - [32-bit](https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-386.exe)
  - [64-bit](https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-amd64.exe)

2. Save the .exe file in a desired location and rename it as `cloudflared.exe`.

> **Note**:
> you don't need to wrap your SSH commands in any unique way. You just need to make a one-time change to your SSH configuration.

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
$ git clone git@gitlab-in-ssh.ship.gov.sg:gcc2.0/seed/cloudflare-support.git

```

> **Note**:
> If you're copying the clone url from the GitLab Web Interface, change the GitLab hostname from `gitlab-in.ship.gov.sg` to `gitlab-in-ssh.ship.gov.sg`.

<kbd>![clone-gitlab-repo](../images/clone-gitlab-repo-cloudflared.png ':size=600')</kbd>

6. When `cloudflared` prompts you to log in, log in with TechPass.

<kbd>![cloudflare-login-success](../images/cloudflare-login-success-1.png ':size=600')</kbd>

7. Authenticate your login.

![cloudflare-login-success](../images/cloudflare-login-success-2.png ':size=600')

8. If the authentication is successful, the following messages will be displayed.

![cloudflare-login-success](../images/cloudflare-login-success-3.png ':size=600')

The token is saved in your `~/.cloudflared` directory, and the git clone command clones the code repository.
<!-- tabs:end -->
