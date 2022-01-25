# SEED offboarding guide for Mac users

This section guides existing SEED users to offboard from it. The offboarding journey has the following steps:


<details>
  <summary>a. Remove your device from Intune</summary><br>

  1. Open the **Company Portal** application and click **Sign in**.

  <kbd>![sign-in](images/onboarding-for-macos/sign-in.png)</kbd>

  2. Log in using your TechPass account credentials.
     <!--- If you are a public officer, use your [WOG ID](terms-definitions).
     - If you are a vendor, use your [TechPass ID](terms-definitions).-->

     <kbd>![log-in-to-gcc](images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

     ?> If you're using text message method for authentication, after you enter your password, you'll need to enter the verification code sent to your phone. Based on what you [set up](https://account.activedirectory.windowsazure.com/Proofup.aspx), other authentication methods have different ways to perform the 2FA.

  3. Go to **Devices** and click the three dots beside the device you want to unenrol.
  4. Choose **Remove**.

  <kbd>![devices](images/onboarding-for-macos/devices-2.png)</kbd>
  5. When prompted to confirm the removal, select **Remove**.
  6. Click your profile icon and **Sign out** of **Company Portal**.


</details>

<details>
  <summary>b. Remove Tanium Client</summary><br>

  1. Open the **Terminal** app and run the following commands:

  ```
  sudo launchctl unload /Library/LaunchDaemons/com.tanium.taniumclient.plist

  sudo launchctl remove com.tanium.taniumclient > /dev/null 2 > &1

  sudo rm /Library/LaunchDaemons/com.tanium.taniumclient.plist

  sudo rm /Library/LaunchDaemons/com.tanium.trace.recorder.plist

  sudo rm -rf /Library/Tanium/

  sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.bom

  sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.plist

  sudo rm /var/db/receipts/com.tanium.tanium.client.bom

  sudo rm /var/db/receipts/com.tanium.tanium.client.plist
  ```
2. Enter your macOS password when prompted.  

</details>

<details>
  <summary>c. Remove Cloudflare WARP client</summary><br>

  Complete the following steps to remove Cloudflare WARP Client:

  1. Open the **Terminal**app and run the following command.

  ```
  sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
  ```
  2. Enter your macOS password when prompted.

  </details>

  <details id="removeMicrosoftDefenderATPoffBoarding">
  <summary>d. Remove Microsoft Defender ATP</summary><br>

  To remove Microsoft Defender ATP from your device, first you need to offboard from it using the offboarding script.

  Check if the script that you received earlier has not yet expired.

 ?>  The expiry date is indicated on the file name. For example, *MicrosoftDefenderATPOffboardingMacOs_valid_until_2021-11-04.py*

  If the script has already expired, choose one of the below options as appropriate:

  - If you are a public officer, contact [SEED team](mailto:gcc2.0_support@tech.gov.sg) to get the offboarding script.

  - If you are a vendor, contact your Defender ATP administrator to [get the offboarding script](get-offboarding-scripts-for-microsoft-defender-atp).

  Once you have the valid offboarding script, do the following to remove Microsoft Defender ATP:

1. Save the offboarding script in the **Downloads** folder.
2. Go to the **Terminal** and run the following command:
  ```
  sudo python ~/Downloads/name_of_offboarding_script.py
  ```
3. Click the **Finder** icon in the **Dock**.
4. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.
5. Drag the app to the Trash, or select the app and choose **File** > **Move to Trash**.



</details>
