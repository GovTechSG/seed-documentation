# Known issues

Following is the list of known issues that may impact SEED users:

**Issues**

- [Issue 1: Intermittently experience the error *Account does not have access*](#issue-1)
- [Issue 2: Users may experience connectivity issues](#issue-2)
- [Issue 3: User experience issues while accessing or loading Slack](#issue-3)
- [Issue 4: Unable to access  AWS documentation](#issue-4)


## Issue 1

**Intermittently experience the error *Account does not have access*.**

When accessing SGTS services using Cloudflare WARP, user intermittently experience an error message which states *That account does not have access*.

**Workaround**

1. Confirm the following:

    - If you have received the successfully onboarded email from DEEP.
    - If you are using only the [supported browsers](additional-resources/best-practices).
    - Is your Cloudflare WARP client connected and is it the latest version. 
    - Open Cloudflare WARP **Settings**, and verify if **Gateway with WARP** is selected.
    - If your device is a Windows device, go to the **Start** menu and verify if Tanium is listed.
    - If your device is a macOS device, go to **Finder** > **Applications** and search for Tanium.
    - If your device operating system is updated to the latest version.
    - If Defender is up-to-date and in the running state.
    - If your TechPass account has the required permissions to access the GCC 2.0 CMP or a particular SGTS service.

> **Note**
>- SEED does not support running other VPN clients together with Cloudflare WARP. 
>- We recommend not to turn on WARP and the VPN at the same time.

2.  Verify if you are running any VPN client concurrently with WARP turned on and complete the following steps as needed:

    a. If yes, make sure the VPN configuration does not route all traffic and DNS queries to the VPN server.

    b. If no, proceed to step 3.

3. If you still have issues, [Generate diagnostic report](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/faqs/how-to-generate-and-upload-diagnostic-files-to-incident-support-request) and upload it to the [incident support request](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/raise-an-incident-support-request).

## Issue 2

**Users experience connectivity issues**

Cloudflare has reported connectivity issues for its users whose macOS WARP client version is earlier than 2022.12.583.0 (20230112.24). These users may experience intermittent connectivity issues while trying to access websites over the internet. 

**Workarounds**

**Workaround 1**: Update Cloudflare WARP client to the latest version.

**To update your Cloudflare WARP client**

1. Open Cloudflare WARP on your GMD.
2. Click **Settings** > **About WARP**.
3. Click **Check for Updates**. Details of the latest version are displayed.

> **Note**
>- If you experience an error stating that Cloudflare is unable to check for updates, try turning off Cloudflare WARP, ensure that you are able to connect to Internet sites and repeat steps 1-3.

4. Click **Install Updates** to download the latest version.
5. When prompted, enter your device password and click **OK**.
6. Click **Install and Relaunch** to install the downloaded latest version of Cloudflare WARP.
7. Repeat steps 1-2 and confirm if the latest Cloudflare version is installed on your GMD.

- **If you are unable to upgrade or still have issues, uninstall WARP and install the latest version**

<!-- tabs:start -->

#### **macOS**

1. To uninstall the existing WARP client, open the **Terminal** app and run the following command.

  ```
  sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
  ```
2. Enter your macOS password when prompted. You will be prompted to confirm the uninstallation.

  ```Do you want to uninstall Cloudflare WARP app? Enter Y to proceed or N to exit.```

3. Enter `Y`. When WARP is successfully uninstalled, the message ```Finished uninstallation!``` is displayed.

4. <a href="https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/post-onboarding-instructions/mac-os?id=turn-on-cloudflare-warp-for-macos-13">Install the latest WARP client for macOS.</a>

#### **Windows**

  1. To uninstall the existing WARP client, click the **Start** icon on the taskbar.
  2. Go to **Settings** > **Apps** and search for **Cloudflare WARP**.
  3. Choose Cloudflare WARP and then click **Uninstall**.

  4. <a href="https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/post-onboarding-instructions/windows">Install the latest WARP client for Windows.</a>
 


<!-- tabs:end -->

## Issue 3

**Users experience issues while accessing or loading Slack**

Users experience intermittent connectivity issues while trying to accessing Slack application over the internet.

**Workaround**

See [Issue 2](#issue-2) for the possible workaround. If you still experience this issue, create a [support request](https://go.gov.sg/seed-techpass-support).

## Issue 4

**Unable to access  AWS documentation**

Users are unable to access AWS documentation if Cloudflare Warp is turned on. Cloudflare has stated that it has resolved this issue. 

**Workaround**

If you continue to experience this issue, create a [support request](https://go.gov.sg/seed-techpass-support).














