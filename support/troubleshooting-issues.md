# Troubleshooting issues

This guide provides solutions to common problems for SEED. Follow the steps below to troubleshoot and resolve the problems you're experiencing.


## Experiencing the *You cannot access this right now* error 

![error](/images/troubleshoot-issue.png)

When using SGTS products with Cloudflare WARP turned off, you might encounter an error message saying, *That account does not have access*.

### Solution

- Turn on Cloudflare WARP Client and access the application. 

If you are facing an issue with your Cloudflare WARP, please follow the solutions in this page. Alternatively, [raise a service request](https://go.gov.sg/seed-techpass-support) for assistance.

## Cloudflare WARP is in *Connecting* status

If your Cloudflare WARP is stuck in the connecting status, please follow these steps to resolve the issue:

1. Click the **Start** icon in the taskbar.

2. Navigate to **Settings** > **Apps**.

3. Search for **Cloudflare WARP** and select **Uninstall**.

After uninstalling, proceed to [download Cloudflare WARP](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/download-warp/)

Once downloaded, follow these steps:

1. Click the **gear** icon > **Preferences** > **Account**.

![gear](/images/disconnected-cf.png)

2. Log in with Cloudflare for Teams.
3. Enter **gccgovsg** in the organisation name field.
![gear](/images/gcc-org.png)
4. Test using incognito mode using Google Chrome or Microsoft Edge browser and test using your personal hotspot or home Wi-Fi.

Ensure to re-authenticate your Cloudflare WARP client with the following steps:

1. Clear your browsing history/cache on Chrome.

2. Click the **Cloudflare WARP** icon.
   
   - Click the **gear** icon.
   - Navigate to **Preferences** > **Account**.
   - Click **Re-authenticate with Cloudflare zero trust**.

3. Reboot your machine.


## Experiencing the *Account does not have access* error

When using SGTS products with Cloudflare WARP, you might encounter an error message saying, *That account does not have access*.

### Solution

1.  First, check the following:

    - Have you received the *successfully onboarded* email from SEED?
    - Are you using one of the supported browsers?
    - Is your Cloudflare WARP client connected and up to date?
    - Open Cloudflare WARP **Settings** and ensure "Gateway with WARP" is selected.
    - For Windows users, check if Tanium is listed in the **Start** menu.
    - For macOS users, look for Tanium in **Finder** > **Applications**.
    - Ensure your device's operating system is up to date.
    - Make sure Defender is updated and running.
    - Check if your TechPass account has the necessary permissions for GCC 2.0 CMP or a specific SGTS service.

> **Note**
>- SEED does not support running other VPN clients alongside Cloudflare WARP.
>- It is recommended not to use WARP and a VPN simultaneously.

2. If you are running a VPN client along with WARP, ensure that the VPN configuration doesn't route all traffic and DNS queries to the VPN server.

3. If the issues persist, [generate a diagnostic report](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/generate-diagnostic-files) and upload it to the [service request](https://go.gov.sg/seed-techpass-support).


## Connectivity issues for macOS WARP users

Cloudflare has reported connectivity problems for users with macOS WARP client versions earlier than 2022.12.583.0 (20230112.24). These users may experience intermittent connectivity issues while trying to access websites.


### Solutions

#### Workaround 1: Update Cloudflare WARP client to the latest version

**To update your Cloudflare WARP client**:

1. Open Cloudflare WARP on your GMD.
2. Click **Settings** > **About WARP**.
3. Click **Check for Updates** to see details of the latest version.

>- If you encounter an error when checking for updates, turn off Cloudflare WARP, ensure you can connect to the internet, and then repeat steps 1-3.

4. Click **Install Updates** to download the latest version.
5. Enter your device password when prompted and click **OK**.
6. Click **Install and Relaunch** to install the downloaded latest version of Cloudflare WARP.
7. Repeat steps 1-2 and confirm if the latest Cloudflare version is installed on your GMD.
> **Note**:
> If you still face issues, uninstall WARP and install the latest version**.

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
  3. Choose Cloudflare WARP and click **Uninstall**.

  4. <a href="https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/post-onboarding-instructions/windows">Install the latest WARP client for Windows.</a>
 
<!-- tabs:end -->

Once downloaded,follow the steps below:

1. Click the **gear** icon > **Preferences** > **Account**.

![gear](/images/disconnected-cf.png)

2. Log in with Cloudflare for Teams.
3. Enter **gccgovsg** in the organisation name field.
![gear](/images/gcc-org.png)
4. Test using incognito mode using Google Chrome or Microsoft Edge browser and test using your personal hotspot or home Wi-Fi.

Ensure to re-authenticate your Cloudflare WARP client with the following steps:

1. Clear your browsing history/cache on Chrome.

2. Click the **Cloudflare WARP** icon.
   
   - Click the **gear** icon.
   - Navigate to **Preferences** > **Account**.
   - Click **Re-authenticate with Cloudflare zero trust**.

3. Reboot your machine.


