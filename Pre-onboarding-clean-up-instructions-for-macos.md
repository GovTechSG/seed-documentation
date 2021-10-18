# Pre-onboarding clean-up instructions for macOS

## About this document
This section explains the pre-onboarding instructions for users onboarding into SEED using their macOS.

## Audience
Public officers and vendors who likes to onboard into SEED using macOS.

*To clean up your Mac for onboarding into SEED:*
1. Choose **Apple** menu ![apple-icon](images/apple-icon.png ':size=75%') > **System Preferences**, or click the System Preferences icon  ![](images/system-preference-icon.png ':size=75%')in the **Dock**.







## (1) Unenroll your device from existing Mobile Device Management (MDM) software

To check if your device is currently managed by MDM software, please follow the steps below. Note: If any of the points below cannot be verified, your device is not managed by MDM and you can skip the rest of this section.

1. Open System Preferences and verify the existence of a preference pane called &quot;Profiles&quot;.
2. Under &quot;Profiles&quot;, verify the existence of a profile titled &quot;Management Profile&quot;.
3. At the bottom left corner of the &quot;Profiles&quot; pane, verify the existence of a statement saying &quot;This Mac is supervised and managed by \_\_\_\_\_&quot;.

If your device is managed by **Microsoft Intune** , please follow the instructions below to unenroll. For any other MDM software, please contact your organization&#39;s IT administrator to find out how to properly unenroll your device before proceeding to the next section.

1. Open the &quot;Company Portal&quot; app and sign into the Azure AD account that your device is enrolled under. If you are unsure which account this is, please contact your organization&#39;s IT administrator.
2. Click on the &quot;Devices&quot; tab and select the correct device to unenroll.
3. Click on the three dots on the right side of the device name and select &quot;Remove&quot;.
4. Click the human icon on the top right corner to sign out from your account.

## (2) Remove pre-existing Tanium Client

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

1. Open the &quot;Finder&quot; app and navigate to &quot;Applications&quot;. Right click on &quot;Microsoft Defender for Endpoint&quot; and click &quot;Move to Trash&quot;.
