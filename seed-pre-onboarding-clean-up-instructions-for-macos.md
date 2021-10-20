# Get your macOS ready for onboarding


**Objective**: This section explains how to get your Mac ready for SEED onboarding. Follow the below instructions to get your device ready.

**Audience**:
- Public officers and vendors who intend to onboard using macOS.
- Defender ATP administrator who intends to share the offboarding scripts to vendors for Microsoft Defender ATP.

<!--If you are using a different You must unenroll your device from your existing Mobile Device Management (MDM) software-->

## Remove existing MDM software
Before proceeding to onboard, verify if your device is currently managed by any other MDM software and unenrol your device from it.

*To verify if you have other MDM*:
1. Choose **Apple** menu > **System Preferences**, or click the **System Preferences** icon in the **Dock**.
2. Go to **Profiles** and from the left menu, choose **Management Profile**.
![verify-other-mdm](images/onboarding-for-macos/verify-other-mdm.png)
At the bottom left, if you see "This Mac is supervised and managed by *your-organisation-name* it indicates you already have an MDM application or service.

If your device is managed by  Intune, follow the below steps to unenrol your device from it. For MDM softwares other than Intune, contact your organisation's IT administrator to unenrol your device.

*To unenrol your device from Intune*:
1. On your Mac, click the **Spotlight** icon or press the Command+space bar to open the **Spotlight Search**.
2. Enter **Company Portal**.
3. Sign in to **Company Portal**.
![sign-in-to-company-portal](images/onboarding-for-macos/sign-in-to-company-portal.png)
4. Go to **Devices** and click the three dots beside the device you want to unenrol.
5. Choose **Remove**.
![devices](images/onboarding-for-macos/devices-2.png)
6.When asked to confirm the removal, select **Remove**. The device is immediately removed from Intune.
7. Click your profile icon and **Sign out** of Company Portal.

<!--

## (1) Unenroll your device from existing Mobile Device Management (MDM) software

To check if your device is currently managed by MDM software, please follow the steps below. Note: If any of the points below cannot be verified, your device is not managed by MDM and you can skip the rest of this section.

1. Open System Preferences and verify the existence of a preference pane called &quot;Profiles&quot;.
2. Under &quot;Profiles&quot;, verify the existence of a profile titled &quot;Management Profile&quot;.
3. At the bottom left corner of the &quot;Profiles&quot; pane, verify the existence of a statement saying &quot;This Mac is supervised and managed by \_\_\_\_\_&quot;.

If your device is managed by **Microsoft Intune** , please follow the instructions below to unenroll. For any other MDM software, please contact your organization&#39;s IT administrator to find out how to properly unenroll your device before proceeding to the next section.

1. Open the &quot;Company Portal&quot; app and sign into the Azure AD account that your device is enrolled under. If you are unsure which account this is, please contact your organization&#39;s IT administrator.
2. Click on the &quot;Devices&quot; tab and select the correct device to unenroll.
3. Click on the three dots on the right side of the device name and select &quot;Remove&quot;.
4. Click the human icon on the top right corner to sign out from your account.-->


## Remove Tanium Client
If Tanium Client is installed on your device, remove it before proceeding further.

The below steps tell you how to verify its availability on your device and remove it.

*To remove Tanium Client*:

1. In you macOS, open **Terminal** and run the following command:
```
sudo ls /Library/Tanium/TaniumClient
```
If you see the below on your Terminal, it indicates that Tanium Client is installed on your device. If not, stop here.
![tanium-client](images/clean-up-instructions-macos.png)
2. Run the following commands in **Terminal**.

```
sudo launchctl unload /Library/LaunchDaemons/com.tanium.taniumclient.plist

sudo launchctl remove com.tanium.taniumclient \&gt; /dev/null 2\&gt;&amp;1

sudo rm /Library/LaunchDaemons/com.tanium.taniumclient.plist

sudo rm /Library/LaunchDaemons/com.tanium.trace.recorder.plist

sudo rm -rf /Library/Tanium/

sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.bom

sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.plist

sudo rm /var/db/receipts/com.tanium.tanium.client.bom

sudo rm /var/db/receipts/com.tanium.tanium.client.plist

```

3. Enter your macOS password when prompted. Once the commands are successfully executed, the Tanium Client is removed from your device.

## Remove pre-existing Cloudflare WARP client
If Cloudflare WARP client is installed on your device, remove it before proceeding further.

The below steps tell you how to verify its availability on your device and remove it.

*To verify if Cloudflare WARP client is on your device*:

1. Click the **Finder** icon in the **Dock**.
2. Choose **Applications**.
3. Search for **Cloudflare WARP.app**.
If this application is not available in your device, you can stop here. if not, proceed to remove it.

*To remove Cloudflare WARP client*:
1. In you macOS, open **Terminal** and run the following command:
```
sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
```

2. Enter your macOS password when prompted. Once the command is successfully executed, the Cloudflare WARP client is removed from your device.

## Remove Microsoft Defender ATP
If Microsoft Defender ATP is available in your device, offboard from it first and then remove it.

The below steps tell you how to verify its availability on your device, offboard from it and remove it.

*To verify if Microsoft Defender ATP is installed*:
1. Click the **Finder** icon in the **Dock**.
2. Choose **Applications**.
3. Search for **Microsoft Defender ATP**.

If this is not installed on your device, there will be no results and you can stop here.

*To offboard from Microsoft Defender ATP*:

**Prerequisites**:

- If you are a Public Officer, [contact GCC2.0 team](gcc2.0_support@tech.gov.sg) to get the offboarding scripts for macOS.

- If you are a vendor, contact your Defender ATP administrator to get your offboarding scripts.

 a. If you are a Defender ATP administrator, go to [Defender Security Center portal](https://securitycenter.windows.com/)

 b. Click **Settings** > **Device Management** > **Offboard**.

 c. Select macOS as operating system and Local Script as **Deployment Method**.

 1. Save the offboarding script in the **Downloads** folder.
 2. Open the **Terminal** and run the following command:
```
sudo python ~/Downloads/name_of_offboarding_script.py
```
3. Click the **Finder** icon in the **Dock**.
4. Choose **Applications** and search for **Microsoft Defender for Endpoint**.
5. Drag the app to the Trash, or select the app and choose **File** > **Move to Trash**.












<!--If you already have Tanium Client on your device, remove it.

To check if the Tanium Client is installed on your device, open the &quot;Terminal&quot; app and run the following command: **sudo ls /Library/Tanium/TaniumClient**. You should see output similar to the following if the client is indeed installed:

![tanium-client](images/clean-up-instructions-macos.png)

If an error is returned saying &quot;No such file or directory&quot;, or if no output is returned, the Tanium Client is not installed on your device and you can skip the rest of this section.

To remove the Tanium Client, open the &quot;Terminal&quot;app and copy the following commands in (you can copy the whole block together), then click &quot;Enter&quot;. Enter your macOS account password when prompted.

```
sudo launchctl unload /Library/LaunchDaemons/com.tanium.taniumclient.plist

sudo launchctl remove com.tanium.taniumclient \&gt; /dev/null 2\&gt;&amp;1

sudo rm /Library/LaunchDaemons/com.tanium.taniumclient.plist

sudo rm /Library/LaunchDaemons/com.tanium.trace.recorder.plist

sudo rm -rf /Library/Tanium/

sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.bom

sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.plist

sudo rm /var/db/receipts/com.tanium.tanium.client.bom

sudo rm /var/db/receipts/com.tanium.tanium.client.plist

```

## (3) Remove pre-existing Cloudflare WARP client

To check if the WARP client is already installed, open the &quot;Finder&quot; app and look for an application named &quot;Cloudflare WARP.app&quot;. If this application does not exist, WARP is not installed on your device and you can skip the rest of this section.

To remove the existing WARP client, open the &quot;Terminal&quot;app and copy the following command in, entering your macOS account password when prompted:

sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh**

## (4) Offboard and uninstall Microsoft Defender ATP

To check if Defender is already installed, open the &quot;Finder&quot; app and look for an application named &quot;Microsoft Defender ATP.app&quot;. If this application does not exist, Defender is not installed on your device and you can skip the rest of this section.

If Defender already exists, follow the steps below to offboard and uninstall it:

1. **Next steps are IMPORTANT** , please do not proceed without offboarding!
2. For **public officers,**** please approach the GCC2.0 team **to request for the specific Defender ATP offboarding script for your OS. For** vendors, please approach your Defender ATP administrator** to obtain your offboarding scripts.
3. Your **administrator** can follow steps a,b &amp; c below to obtain the script.
  1. This script can be found in the [Defender Security Center portal](https://securitycenter.windows.com/).
  2. Go to Settings \&gt; Device management \&gt; Offboarding and select Mac OS as the operating system, with &quot;Local Script&quot; as deployment method.
4. Place the offboarding script in your &quot;Downloads&quot; folder.
5. Open the &quot;Terminal&quot; app and run the following command:

## sudo python ~/Downloads/name\_of\_offboarding\_script.py

1. Open the &quot;Finder&quot; app and navigate to &quot;Applications&quot;. Right click on &quot;Microsoft Defender for Endpoint&quot; and click &quot;Move to Trash&quot;.-->
