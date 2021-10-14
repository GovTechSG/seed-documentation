# SEED offboarding instructions for macOS

**Objective:** This section guides an existing SEED users to offboard their devices.

Audience: Existing SEED users

**(a) Remove your device from Intune**

1. Open **Company Portal** app and sign in to the account that you used to enroll your device.

?> Note: If you are a public officer, this will be your WOG ID and if you are a vendor, it will be your TechPass ID.

2. Go to **Devices** tab and select the device you want to unenroll.
3. Click the three dots on the right side of the device and choose **Remove**.
4. Click the human icon on the top right corner to sign out from your account.

**(b) Remove the Tanium Client**

1. Open the **Terminal** app and run the following commands.

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

  ?> Tip: You may copy and paste all the commands together.

2. Enter your macOS account password when prompted.



**(c) Remove the Cloudflare WARP client**

1. Open the **Terminal**app and run the following command.

```
sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
```
2. Enter your macOS account password when prompted.

**(4) Offboard from and uninstall Microsoft Defender ATP**

Prerequisites:
- If you are a public officer, contact the GCC2.0 team to request for the specific Defender ATP offboarding script for your OS.
-  If you are a vendor, contact your Defender ATP admins to obtain your offboarding scripts.

*To offboard from Microsoft Defender ATP:*
1. Make sure the offboarding script is in your **Downloads** folder.
2. Open the **Terminal** app and run the following command:

```
sudo python ~/Downloads/name_of_offboarding_script.py
```

3. Go to **Finder** > **Applications** > **Microsoft Defender ATP**.
4. Right click **Microsoft Defender ATP** > **Move to Bin**.
