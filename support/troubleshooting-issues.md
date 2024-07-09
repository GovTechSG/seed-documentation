# Troubleshooting issues

This guide provides solutions to common problems for SEED. Follow the steps below to troubleshoot and resolve the problems you're experiencing.

## Receiving notifications on desktop and email for misconfigurations on SEED device

<!-- tabs:start -->

### **Windows**

#### Cloudflare

**Ensure that Cloudflare service is installed and running**

1. Search for *Add or Remove Programs* in the search bar.
2. Ensure that Cloudflare Warp shows up as an installed program.

![cf](/images/cf-installed.png)

3. Search for *Run* in the search bar and run *services.msc*.
4. Ensure that Cloudflare WARP is a running service.

![cf run](/images/cf-running.png)

5. If Cloudflare WARP is not installed or not running, refer to [troubleshooting Cloudflare issues](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/troubleshooting-issues).

**Ensure that Cloudflare is authenticated and verified**

1. Open the taskbar, right-click on the Cloudflare Warp icon, and then click on *Preference*.
2. Navigate to *Account* and ensure that you are authenticated with the team name *gccgovsg*.

![acc-cf](/images/acc-cf.png)

3. If Cloudflare WARP is not authenticated to *gccgovsg*, refer to [troubleshooting issues](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/troubleshooting-issues).

**For any other Cloudflare issues, refer to the Cloudflare troubleshooting information in the relevant section on this page.**

#### Intune

**Ensure that Intune is enrolled with the valid tenant**

1. Search for *Access work or school* in the search bar.
2. Ensure that you have an account added with a *techpass.gov.sg* domain (for vendors) or a *<agency_name>.gov.sg* domain (for all Public officers).

![work](/images/work-school.png)

3. Click the account > *Info*.
4. Ensure that the top of the page shows either *Managed by SG Govt M365* for public officers or *Managed by TechPass* for vendors.

![cf](/images/managed-by.png)

5. If there is no enrollment, refer to the following links for help on how to enroll your device to Intune:
   - [Public officer](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/public-officer)
   - [Vendor](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/vendor)

#### Defender

**Ensure that the Defender service is running**

1. Search for *Run* in the search bar and type *services.msc*.
2. Ensure that *Microsoft Defender Antivirus Service* and *Microsoft Defender Core Service* are running.

![defender run](/images/defender-run.png)

3. If the services are not running, reboot your system and verify again, or try to start them manually by right-clicking and click *Start*.
4. If your services are unable to start after multiple attempts, raise a [service request](http://go.gov.sg/seed-techpass-support)

**Ensure that real-time protection and cloud protection are turned on**

1. Search for *Windows Security* in the search bar.
2. Navigate to *Virus & threat protection* > *Manage Settings* under *Virus & threat protection settings*.
3. Ensure that *Real-time protection* and *Cloud-delivered protection* are enabled.

![rt](/images/realtime-protection.png)

4. If they cannot be enabled, navigate to the previous page and click *Check for Updates* under *Virus & threat protection Updates*, and install the updates, if any.
5. If it is still not enabled, raise a [service request](http://go.gov.sg/seed-techpass-support), and state *Disabled Real-Time protection and Cloud-delivered protection* in the description.

**Ensure that Defender has a valid tenant**

1. Go to the Start menu and enter Powershell.
2. Right-click on the search result for PowerShell and select Run as Administrator
3. On Powershell, run the following command:
```
$reg64 = [Microsoft.Win32.RegistryKey]::OpenBaseKey([Microsoft.Win32.RegistryHive]::LocalMachine, [Microsoft.Win32.RegistryView]::Registry64)
$OrgID =  $reg64.OpenSubKey("SOFTWARE\MICROSOFT\Windows Advanced Threat Protection\Status").GetValue("OrgID")
echo $OrgID
```
4. Take note of the value displayed for OrgID.
5. Ensure that the value is one of the following:
   - Public officers: faa36a5e-2da6-4225-8e27-226177c801a0
   - Vendors: 49237d71-42ac-425a-a803-881b92cc18ce
6. If the values are different, check with your IT administrator to identify which Defender tenant you are currently under and offboard from that tenant before attempting to re-onboard.

### **macOS**

#### Cloudflare

**Ensure that Cloudflare service is installed and running**

1. Access the *Application* folder.
2. Ensure that Cloudflare WARP is appearing as an installed program.

![mac-cf](/images/mac-cf.png)

3. Open *Terminal*.
4. Type `sudo launchctl list | grep -i cloudflare` and ensure the service is running.
5. If Cloudflare WARP is not installed or not running, refer to the Cloudflare troubleshooting information in the relevant section on this page.

> **Note**: Spotlight is used to detect the existence of applications. If you have disabled Spotlight, we would not be able to detect Cloudflare WARP on your device.

**Ensure that Cloudflare is authenticated and verified**

1. Click the *Cloudflare WARP* icon on the taskbar > *Preference*.
2. Navigate to *Account* and ensure that you are authenticated with the team name *gccgovsg*.

![mac-gcc](/images/mac-gcc.png)

3. If Cloudflare WARP is not authenticated to *gccgovsg*, refer to [troubleshooting issues](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/troubleshooting-issues).

#### Intune

**Ensure that Intune is enrolled with the valid tenant**

1. Log into Company Portal using your `<agency_name>.gov.sg` or `techpass.gov.sg` username.
2. Ensure that your device is shown as **managed**.
3. Ensure that the top right-hand corner shows *SG Govt M365* or *TechPass* to show it is managed by the correct tenant.

![mac-365](/images/mac-365.png)

4. If there is no enrollment, refer to the following links for help on how to enroll to Intune:

   - [Public officer](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/public-officer)
   - [Vendor](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/vendor)


> **Note**: Perform a sync to check that the device is able to communicate with Intune.

#### Defender

**Ensure that the Defender service is installed**

1. Access the *Application* folder.

![mac-app](/images/mac-app.png)

**Ensure that the Defender service is running and is healthy**

1. Open *Terminal*.
2. Run `ps aux | grep -i "Defender"`.
3. Ensure you see the following output:

![defender-terminal](/images/defender-terminal.png)

**If the service is not running, refer to the following steps**:

1. Open *Terminal*.
2. Run the following command to start the services:
   - `sudo launchctl kickstart -k system/com.microsoft.wdav`
   - `sudo launchctl kickstart -k system/com.microsoft.wdav.enterprise`
3. Run `ps aux | grep -i "Defender"` to verify if the services are running now.
4. If the issue persists, raise a [service request](http://go.gov.sg/seed-techpass-support)

**Ensure that Defender has real-time protection enabled**

1. Open *Terminal*.
2. Run `mdatp health --field real_time_protection_enabled`.
3. Ensure that the value is *true*.

**Ensure that Defender is cloud enabled**

1. Open *Terminal*.
2. Run `mdatp health --field cloud_enabled`.
3. Ensure that the value is *true*.

![mac-virus](/images/mac-virus.png)

**Ensure that Defender has a valid tenant**

1. Open *Terminal*.
2. Run `mdatp health --field org_id`.
3. Ensure that the value is one of the following:
   - Public officers: faa36a5e-2da6-4225-8e27-226177c801a0
   - Vendors: 49237d71-42ac-425a-a803-881b92cc18ce
4. If the values are different, please check with your IT administrator to identify which Defender tenant you are currently under and offboard from that tenant before attempting to re-onboard.

**Ensure that Defender definitions are updated**

1. Open Microsoft Defender.
2. Under *Virus & threat protection updates*, click *Check for updates*.

![mac-check](/images/mac-check.png)

3. Click *Help* > *Check for product updates*.
4. Click *Update All*.

![mac-virus](/images/mac-update-all.png)

<!-- tabs:end -->


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

1. To uninstall the existing WARP client, open the ***Terminal*** app and run the following command.

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


