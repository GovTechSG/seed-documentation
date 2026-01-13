# Troubleshooting issues

This guide provides solutions to common problems for SEED. Follow the steps below to troubleshoot and resolve the problems you are experiencing.

## Repair SSO

Users may encounter the error **The device is not registered**.

![device not registered error](/images/repair-sso1.png)

### Solution

1. Navigate to **System Settings** > **Users & Groups** > **Network Servers**.
2. Select **Repair**.

![Prepair network servers](/images/repair-sso1.png)

## How to sync the latest device posture

Use the steps below if the SEED dashboard does not reflect your current device posture, for example, when your operating system has been updated to the latest version but the update is not shown in the dashboard.

<!-- tabs:start -->

#### **Windows OS**

##### Sync device with Intune
1. Navigate to **Access work or school**.
2. Select your TechPass account and click **Info**.
3. Select **Sync**.

##### Sync device with Tanium
1. Press **Windows + R** and open `services.msc`.
2. Locate **Tanium Client**.
3. Right-click the service and select **Restart**.

#### **macOS**

##### Sync device with Intune
1. Launch **Company Portal**.
2. Select **Device**.
3. Select the three dots (**…**) and choose **Check status**.

##### Sync device with Tanium
1. Launch **Terminal**.
2. Run the following command:
``` 
sudo launchctl kickstart -k -p system/com.tanium.taniumclient

```
<!-- tabs:end -->

## How to verify if Crowdstrike is configured correctly


If your device is blocked in the SEED dashboard due to Crowdstrike Falcon, follow the instructions below to restore access.

![Launchpad showing Falcon app](/images/r0.png)


## Step 1 – Launch CrowdStrike app
Open **Falcon** from the Launchpad.  
![Launchpad showing Falcon app](/images/r1.png)


## Step 2 – Check Falcon sensor
If the Falcon window shows red indicators, click **Configure settings**.  
![CrowdStrike Falcon status – configure settings](/images/r2.png)


## Step 3 – Set up Falcon sensor system extension
Click **Setup** under *Network filter not loaded*.  
![Setup network filter](/images/r3.png)


## Step 4 – Allow network filter
When prompted, click **Allow**.  
![Allow network filter](/images/r4.png)


## Step 5 – Confirm network filter loaded
Once the filter is loaded, click **Continue**.  
![Network filter loaded](/images/r5.png)


## Step 6 – Set up system extension
Click **Setup** under *Extension not loaded*.  
![Setup extension](/images/r6.png)


## Step 7 – Approve extension in system settings
Click **Open system settings** when prompted.  
![Open system settings](/images/r7.png)


## Step 8 – Enable Falcon in endpoint security extensions
In **System settings → Extensions**, enable the toggle for *Falcon sensor*. Enter your admin credentials if required.  
![Enable Falcon endpoint security extension](/images/r8.png)


## Step 9 – Confirm extension loaded
Once enabled, the status will show **Extension loaded**. Click **Continue**.  
![Extension loaded](/images/r9.png)


## Step 10 – Grant full disk access
Go to **System settings → Privacy & security → Full disk access**.  
Enable the toggle for **Falcon sensor**.  
![Grant full disk access](/images/r10.png)


## Step 11 – Confirm full disk access
Once enabled, the status will show **Full disk access granted**. Click **Continue**.  
![Full disk access granted](/images/r11.png)



## Step 12 – Verify Falcon sensor
Ensure that all indicators are green:
- Sensor is registered  
- Sensor is operational  
- Sensor is cloud connected  

![Falcon all green](/images/r12.png)

## Step 13 – Sync to Tanium
Open **Terminal** and run:

```bash
sudo launchctl kickstart -k -p system/com.tanium.taniumclient

```


## Cloudflare connectivity issue: turns orange

![cf](/images/orange-wrap.png)


When having difficulty accessing SGTS or GCC services, Cloudflare WARP may display an **Orange** status.  

### Suggested steps

1. Launch **Cloudflare WARP**.  
2. Click the **Gear** icon.  
3. Navigate to **Preferences > Account**.  
4. Log in to **GovTech Zero Trust** using the account name `gccgovsg`.  


## Cloudflare connectivity issue – Limited connectivity: A certificate is missing

![lc](/images/limited-connectivity.png)

When having difficulty accessing SGTS or GCC services, Cloudflare WARP may show a **Missing certificate** error.  

### Suggested steps

1. Download the required certificate from the [Cloudflare certificate update guide](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/cloudflare-cert-update-guide).  
2. Trust the certificate on your device.


## Unable to log in to MacBook – login loop

This is a known issue affecting older versions of macOS, where users are unable to log in despite entering the correct password.
The problem typically occurs because some key presses are not registered properly at the login screen, resulting in an incorrect password input — even if the user typed it correctly.
This issue is fixed from macOS **15.4 or later**.
To resolve the issue, and aligning to our OS baselining, we recommend you to upgrade your macOS to version **15.4.1 or later**, to avoid encountering the login loop issue.

### Suggested steps to log in and update

1. **Log in and upgrade macOS**
   - Attempt to log in to the MacBook a few times using the correct password. Once logged in, upgrade your macOS.
   - Alternatively, log in with a different user account (if available). Once logged in, upgrade your macOS.

2. **Reset password in recovery mode**
   - If you are unable to log in at all, reset your password using recovery mode. Follow the steps in [Apple’s guide to resetting passwords](https://support.apple.com/en-sg/102673). Once the password is reset, log in and upgrade your macOS.

### Recovery mode instructions

Follow the steps below depending on your Mac model. If you are unsure whether your Mac uses Apple silicon, you can try both sets of steps.

#### For Macs with Apple silicon

1. Shut down your Mac. If you are unable to shut it down normally, press and hold the power button for up to 10 seconds until it turns off. (On laptops with Touch ID, press and hold the Touch ID button.)
2. Press and hold the power button. Continue holding it until your Mac turns on and displays the startup options screen. When you see **Options**, release the power button.
3. Click **Options**, then click the **Continue** button below it.

#### For other Mac models

1. Shut down your Mac. If you are unable to shut it down normally, press and hold the power button for up to 10 seconds until it turns off. (On laptops with Touch ID, press and hold the Touch ID button.)
2. Press and release the power button to turn on your Mac.
3. Immediately after releasing the power button, press and hold **Command (⌘)-R** on your keyboard.
4. Keep holding the keys until you see the Apple logo or a spinning globe.
5. If your Mac starts up to the login window again, review the [startup key combinations guide](https://support.apple.com/en-sg/HT201255), then start again from step 1.

### Reset password in recovery mode

1. From the **Utilities** menu in the menu bar, select **Terminal**.
2. In the Terminal window, type `resetpassword` and press **Return**. This will open the Reset Password assistant.
3. If prompted to select an admin user, click **Forgotten all passwords?**.
4. At the Reset Password window:
   - Click **Deactivate Mac**, then confirm by clicking **Deactivate**.
   - If the Activation Lock window appears, enter your Apple ID credentials and click **Next**.
5. Enter your new password information. If multiple user accounts are listed, click **Set Password** next to each account name and provide a new password for each.
6. When finished, click **Exit**, then restart your Mac from the **Apple menu > Restart**. Log in with your new password.

### Reinstall macOS if necessary

If you are still unable to log in, reinstall macOS through recovery mode. Refer to [Apple’s guide on reinstalling macOS](https://support.apple.com/en-sg/102655).

### Additional reference

Apple has acknowledged this issue in their enterprise support article:  
[https://support.apple.com/en-gb/121011](https://support.apple.com/en-gb/121011)



## Resolving *Cloudflare CF_DNS_Lookup_Failure* error on macOS 15

![Firewall settings](/images/cferror.png)

If you encounter the `CF_DNS_Lookup_Failure` error while using Cloudflare WARP on macOS 15, follow these steps to resolve the issue:


### Upgrade macOS
Cloudflare recommends upgrading to **macOS 15.1 or later**, as macOS 15.1 resolves several issues that could cause the WARP client to misbehave.

- Open **System Preferences**.
- Select **Software Update**.
- Follow the on-screen instructions to update to **macOS 15.1 or later**.

### Enable firewall settings

Ensure your firewall settings are properly configured to allow Cloudflare WARP to function.

- Open **System Preferences**.
- Navigate to **Settings > Network > Firewall**.
- Turn on the firewall.

![Firewall settings](/images/firewall-macos15.png)


### Disable *block all incoming connections*
Adjust your firewall settings to allow incoming connections.

- Go to **Settings > Network > Firewall > Options**.
- Ensure **"Block all incoming connections"** is **unchecked**.


### Allow incoming connections for Cloudflare WARP
Enable incoming connections explicitly for the following applications:

1. **CloudflareWARP** located at:  
   `/Applications/CloudflareWARP.app/Contents/Resources/CloudflareWARP`
2. **Cloudflare WARP** with the bundle ID:  
   `com.cloudflare.1dot1dot1dot1dot1.macos`

![Allow incoming connections](/images/allow-warp.png)

After completing these steps, the `CF_DNS_Lookup_Failure` error should no longer occur.


## Troubleshooting access issues for SGTS Resources


When using SGTS products with Cloudflare WARP, you may encounter an error message stating **“That account does not have access”**, as shown in the screen below.

![Error Screen](/images/cf-i1.png)


Follow these steps to diagnose the issue:

   **Verify the following:**
   1. The Cloudflare WARP client is connected and enrolled in the `gccgovsg` organisation (refer to this guide).
   2. The Tanium Client is installed and running on your device (refer to this guide).
   3. Your operating system meets the prerequisites.
   4. Check the SEED dashboard to confirm the reason access to certain resources is restricted, and perform any remediation steps if required.
   5. Sync the latest device posture using this guide (*to be created by Huda in step 10 below*).
   6. Retry access:
      a. Wait at least 15 minutes before trying again.
      b. If access still fails, try using an incognito window.
      c. If access works in incognito mode, clear your browser cache and retry.
      4d. If the issue persists, log a ticket at <http://go.gov.sg/seed-techpass-support>.

### Possible reasons for blocking

Access to SGTS resources may be blocked for the following reasons:

| **Issue** | **Description** | **Category** |
|---|---|---|
| Malware on the device | The device is infected with malware or exhibits suspicious behavior, causing it to be classified as high-risk and blocking access to SGTS. | Security |
| Incorrect Cloudflare configuration | The Cloudflare WARP client is either stopped or not enrolled in the `gccgovsg` organization, marking the device as misconfigured. | Configuration |
| Incorrect Intune configuration | Device not enrolled in the correct tenants (`SG Govt M365` or `TECHPASS`), or unable to sync with Intune, blocking access to resources. | Configuration |
| Tanium Client cannot communicate | The Tanium Client is unable to communicate with our servers, leading to blocked access due to lack of necessary status updates.| Configuration |


## Tanium issues

<!-- tabs:start -->

### **Windows**

**Check for Tanium Client installation**

1. Click the Start icon on the taskbar.
2. Go to *Settings* > *Apps* and search for Tanium Client.
   
![tanium](/images/tanium-client-win.png)

3. If you are unable to find it, try to resync your Intune to install the Tanium Client on your device.

### **macOS**

**Check for Tanium Client installation**

1. Open *Terminal*.
2. Run the following command:
   ```sudo ls /Library/Tanium/TaniumClient```
3. Enter your macOS password when prompted.
4. If you see confirmation, as shown in the image below, Tanium Client is installed on your device.
![tanium-client](/images/tanium-client-mac.png)
5. If you are unable to find it, log into Company Portal to install the Tanium Client on your device. Otherwise, you might need to re-onboard your device following the steps [here](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/seed-prerequisites).


<!-- tabs:end -->

## Other Tanium issues

If your device remains blocked after checking all other settings, please try to connect using a mobile hotspot and wait for 15-20 minutes for the Tanium server to find your device.

If your device is unblocked after connecting via mobile hotspot, it is likely that the firewall of the previous network you are connecting to is blocking the Tanium IPs. Whitelist the Tanium IPs to resolve this issue. The IP addresses can be found at this [link](https://docs.developer.tech.gov.sg/docs/tanium-and-egress-ip/?product=security%20suite%20for%20engineering%20endpoint%20devices%20(seed)&id=firewall-blocking-tanium-access) (accessible via TechPass login).

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

#### Crowdstrike

**Ensure that Crowdstrike is running**

1. Ensure that *Crowdstrike* is running and it is healthy via this [guide](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/vendor?id=step-3-verify-installation).
2. If the services are not running, reboot your system and verify again, or try to start them manually by right-clicking and click *Start*.
3. If your services are unable to start after multiple attempts, raise a [service request](http://go.gov.sg/seed-techpass-support)

**Ensure that real-time protection and cloud protection are turned on**

1. Search for *Windows Security* in the search bar.
2. Navigate to *Virus & threat protection* > *Manage Settings* under *Virus & threat protection settings*.
3. Ensure that *Real-time protection* and *Cloud-delivered protection* are enabled.

![rt](/images/realtime-protection.png)

4. If they cannot be enabled, navigate to the previous page and click *Check for Updates* under *Virus & threat protection Updates*, and install the updates, if any.
5. If it is still not enabled, raise a [service request](http://go.gov.sg/seed-techpass-support), and state *Disabled Real-Time protection and Cloud-delivered protection* in the description.


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
3. Ensure that the top left-hand corner shows *SG Govt M365* or *TechPass* to show it is managed by the correct tenant.

![mac-365](/images/mac-365.png)

4. If there is no enrollment, refer to the following links for help on how to enroll to Intune:

   - [Public officer](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/public-officer)
   - [Vendor](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/vendor)


> **Note**: Perform a sync to check that the device is able to communicate with Intune.

#### Crowdstrike

Ensure that *Crowdstrike* is running and it is healthy via this [guide](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/support/troubleshooting-issues?id=macos-device-blocked-in-seed-dashboard-no-remediation-steps&product=security%20suite%20for%20engineering%20endpoint%20devices%20(seed).



<!-- tabs:end -->


## Experiencing the *You cannot access this right now* error 

![error](/images/troubleshoot-issue.png)

When using SGTS products with Cloudflare WARP turned off, you might encounter an error message saying, *That account does not have access*.

### Solution

- Turn on Cloudflare WARP Client and access the application. 

If you are facing an issue with your Cloudflare WARP, please follow the solutions in this page. Alternatively, [raise a service request](https://go.gov.sg/seed-techpass-support) for assistance.


## Connectivity issues for macOS and windows WARP users

Users may experience intermittent connectivity issues while trying to access websites.


### Solutions

#### Workaround: Uninstall and reinstall Cloudflare WARP

<!-- tabs:start -->

#### **macOS**

1. To uninstall the existing WARP client, open the ***Terminal*** app and run the following command.

  ```
  sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
  ```
2. Enter your macOS password when prompted. You will be prompted to confirm the uninstallation.

  ```Do you want to uninstall Cloudflare WARP app? Enter Y to proceed or N to exit.```

3. Enter `Y`. When WARP is successfully uninstalled, the message ```Finished uninstallation!``` is displayed.

4. Proceed to [download Cloudflare WARP](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/download-warp/).
  - **macOS**: Version 2025.7.176.0

#### **Windows**

1. To uninstall the existing WARP client, click the **Start** icon on the taskbar.
2. Go to **Settings** > **Apps** and search for **Cloudflare WARP**.
3. Choose Cloudflare WARP and click **Uninstall**.
4. Proceed to [download Cloudflare WARP](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/download-warp/).
   - **Windows**: Version 2025.7.176.0

<!-- tabs:end -->

Once downloaded, follow the steps below:

1. Click the **gear** icon > **Preferences** > **Account**.

   ![gear](/images/disconnected-cf.png)

2. Log in with Cloudflare for Teams.
3. Enter **gccgovsg** in the organisation name field.

   ![gear](/images/gcc-org.png)
   
5. Test using incognito mode using Google Chrome or Microsoft Edge browser and test using your personal hotspot or home Wi-Fi.

Ensure to re-authenticate your Cloudflare WARP client with the following steps:

1. Clear your browsing history/cache on Chrome.

2. Click the **Cloudflare WARP** icon.
   
   - Click the **gear** icon.
   - Navigate to **Preferences** > **Account**.
   - Click **Re-authenticate with Cloudflare zero trust**.

3. Reboot your machine.




