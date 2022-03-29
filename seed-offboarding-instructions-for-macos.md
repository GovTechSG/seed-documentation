# SEED offboarding guide for macOS users

This section guides existing SEED users to offboard from it. The offboarding journey has the following steps:

<details>
  <summary>a. Remove your device from Microsoft Endpoint Manager</summary><br>

  1. Open the **Company Portal** application and click **Sign in**.

  <kbd>![sign-in](images/onboarding-for-macos/sign-in.png)</kbd>

  2. Log in using your TechPass account credentials.
     <!--- If you are a public officer, use your [WOG ID](terms-definitions).
     - If you are a vendor, use your [TechPass ID](terms-definitions).-->

     <kbd>![log-in-to-gcc](images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

     ?> Your two-factor authentication(2FA) varies based on the authentication method you have [set up](https://account.activedirectory.windowsazure.com/Proofup.aspx). If you're using the text message method for authentication, after you enter your password, enter the verification code sent to your phone.

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
  <summary>d. Remove Microsoft Defender for Endpoint</summary><br>

  To remove Microsoft Defender for Endpoint from your device, first you need to offboard from it using the offboarding script.

  Check if you already have the correct offboarding script and if you still have the script, check the expiry date to see if it is still valid.

 ?>  The expiry date is indicated on the file name. For example, *MicrosoftDefenderATPOffboardingMacOs_valid_until_2021-11-04.py*

  If the script has already expired, choose one of the below options as appropriate:

  - If you are a public officer, contact [SEED team](mailto:gcc2.0_support@tech.gov.sg) to get the offboarding script.

  - If you are a vendor, contact your Defender administrator to [get the offboarding script](get-offboarding-scripts-for-microsoft-defender-atp).

  1. Open **Terminal** and run `mdatp health`.
  2. Note down the displayed **org_id**.

  ?> If this command does not return anything, it confirms that your device does not have Microsoft Defender. Proceed to onboard your device to SEED.

  3. Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping) and based on the **org_id**, identify the organisation of the Defender or the antivirus on your device.
  4. Based on the organisation, choose the required step from the following:
  - If your organisation id corresponds to organisations such as WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and ignore the rest of this section.
  - If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [GDS team](mailto:gds_den@tech.gov.sg) to to get the Hive offboarding script and proceed to step 5.
  - For all other organisation ids, contact your organisation's MDM administrator or Defender administrator to get the respective offboarding script and proceed to step 5.

?> Refer to [Get the offboarding scripts for Microsoft Defender ](get-offboarding-scripts-for-microsoft-defender-atp).

  5. Save the offboarding script to the **Downloads** folder.
  6. Go to **Terminal** and run the following command:
    ```
    sudo python ~/Downloads/name_of_offboarding_script.py
    ```
  ?> Name of the python file in this command is only an example. When you run the command, specify the file name of the offboarding script provided to you.

  7. Go back to the **Finder** icon in the **Dock**.
  8. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.
  9. Drag the app to the Bin, or select the app and choose **File** > **Move to Bin**.


</details>
