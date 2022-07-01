# Offboard macOS device from SEED


## Step 1: Remove your device from Microsoft Intune

  1. Open the **Company Portal** application and click **Sign in**.

  <kbd>![sign-in](../images/onboarding-for-macos/sign-in.png)</kbd>

  2. Log in using your TechPass account credentials.

     <kbd>![log-in-to-gcc](../images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

> **Note:**
>- Your two-factor authentication(2FA) varies based on the authentication method you have [set up](https://account.activedirectory.windowsazure.com/Proofup.aspx). If you're using the text message method for authentication, after you enter your password, enter the verification code sent to your phone.

  3. Go to **Devices** and click the three dots beside the device you want to unenrol.
  4. Choose **Remove**.

  <kbd>![devices](../images/onboarding-for-macos/devices-2.png)</kbd>
  5. When prompted to confirm the removal, select **Remove**.
  6. Click your profile icon and **Sign out** of **Company Portal**.

## Step 2: Remove Tanium Client

  1. Open the **Terminal** app and run the following commands:

  ```
  sudo launchctl unload /Library/LaunchDaemons/com.tanium.taniumclient.plist

  sudo launchctl remove com.tanium.taniumclient > /dev/null 2>&1

  sudo rm /Library/LaunchDaemons/com.tanium.taniumclient.plist

  sudo rm /Library/LaunchDaemons/com.tanium.trace.recorder.plist

  sudo rm -rf /Library/Tanium/

  sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.bom

  sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.plist

  sudo rm /var/db/receipts/com.tanium.tanium.client.bom

  sudo rm /var/db/receipts/com.tanium.tanium.client.plist
  ```
2. Enter your macOS password when prompted.  

## Step 3: Remove Cloudflare WARP client

  1. Open the **Terminal**app and run the following command.

  ```
  sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
  ```
  2. Enter your macOS password when prompted.

## Step 4: Remove Microsoft Defender for Endpoint

To remove Microsoft Defender for Endpoint from your device, offboard your device from it using the offboarding script.

1. Open **Terminal** and run `mdatp health`.
2. Note down the displayed **org_id**.
3. Identify the organisation of the Defender or the antivirus on your device.

>- **Note:**
> Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping.md) for identifying your Defender or antivirus organisation.

4. Based on the organisation, choose the required step from the following:
  - If your organisation id corresponds to WOG, contact [GCC2.0 team](https://form.gov.sg/#!/6099efa30d6a0a0012dff367), to get the offboarding script for macOS.
  - If your organisation id corresponds to TechPass, contact your Defender administrator to get the offboarding scripts for your operating system for macOS.

>- **Note:**
> Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, *WindowsDefenderATPOffboardingScript_valid_until_2021-11-10.sh*

5. Save the offboarding script to the **Downloads** folder.
6. Go to **Terminal** and run the following command:
  ```
  sudo /bin/sh ~/Downloads/name_of_offboarding_script.sh
  ```
>- **Note:**
> The file name *name_of_offboarding_script* in this command is only an example. When you run the command, specify the file name of the offboarding script provided to you.

7. Go back to the **Finder** icon in the **Dock**.
8. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.
9. Drag the app to the Bin, or select the app and choose **File** > **Move to Bin**.
