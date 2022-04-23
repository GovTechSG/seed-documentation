<!--# Remove existing softwares for macOS
Remove the following software solutions from your device before proceeding to onboard to SEED:

- current MDM software
- Tanium client or any other unified endpoint management and security platform
- Cloudflare WARP or any other software used for privacy and secured connections
- Defender or any other antivirus solution.

This section explains how public officers and vendors can remove those softwares from macOS device.


<details>
  <summary>a. Verify if your device is already managed by any MDM software</summary><br>

  *To verify if you already have an MDM software* :
  1. Go to the **Apple** menu > **System Preferences** or click the **System Preferences** icon in the **Dock**.
  2. Go to **Profiles** and from the left menu, choose **Management Profile**.
  <kbd>![verify-other-mdm](images/onboarding-for-macos/verify-other-mdm.png)</kbd>
  3. At the lower left, if you see "This Mac is supervised and managed by *your-organisation-name*", it indicates you already have an MDM software.

  ?> If you confirm your device is not managed by any MDM currently, proceed to step **c.Remove Tanium Client**.

  4. To view the details of the current MDM software, go to **Settings** in the right side of **profiles**.
  ![verify-other-mdm](images/onboarding-for-macos/management-profile-settings.png)

  >**Notes:**
  >* If you see Microsoft Intune in the settings, it indicates that **Microsoft Intune** is your MDM. Proceed to the next **step b. Unenrol from Microsoft Intune**    
  >* To unenrol your device from MDM softwares other than Microsoft Intune, contact your organisation's IT administrator.

<!--
  <div class="warn">
  <ul>
  <li>If you see Microsoft Intune in the settings, it indicates that **Microsoft Intune** is your MDM. Proceed to the next step <strong>b. Unenrol from Microsoft Intune</strong>.</li>
  <li>To unenrol your device from MDM softwares other than Microsoft Intune, contact your organisation's IT administrator.</li>
  </ul>
  </div>

</details>
<details>
  <summary>b. Unenrol from Microsoft Intune</summary><br>

  1. Click the **Spotlight** icon or press the ``Command+Spacebar`` to open the **Spotlight Search**.
  2. Enter **Company Portal**.
  3. Sign in to **Company Portal**.
  <kbd>![sign-in-to-company-portal](images/onboarding-for-macos/sign-in-to-company-portal.png)</kbd>
  4. Go to **Devices** and click the three dots beside the device you want to unenrol.
  5. Choose **Remove**.
  <kbd>![devices](images/onboarding-for-macos/devices-2.png)</kbd>
  6. When prompted to confirm the removal, select **Remove**.
  7. Click your profile icon and **Sign out** of **Company Portal**.

</details>

<details>
  <summary>c. Remove Tanium Client</summary><br>

  1. Open **Terminal** and run the following command:

   ```
  sudo ls /Library/Tanium/TaniumClient
   ```
  2. If prompted for password, enter your macOS password.

  3. If you see the below on your **Terminal**, it indicates that Tanium Client is installed on your device and go to step 3. If not, proceed to step d. **Remove Cloudflare WARP client**.

   <kbd>![tanium-client](images/clean-up-instructions-macos.png)</kbd>

  4. Run the following commands in **Terminal**.

     ```
     sudo launchctl unload /Library/LaunchDaemons/com.tanium.taniumclient.plist

     sudo launchctl remove com.tanium.taniumclient > /dev/null 2 >&1

     sudo rm /Library/LaunchDaemons/com.tanium.taniumclient.plist

     sudo rm /Library/LaunchDaemons/com.tanium.trace.recorder.plist

     sudo rm -rf /Library/Tanium/

     sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.bom

     sudo rm /var/db/receipts/com.tanium.taniumclient.TaniumClient.pkg.plist

     sudo rm /var/db/receipts/com.tanium.tanium.client.bom

     sudo rm /var/db/receipts/com.tanium.tanium.client.plist

    ```

4. Enter your macOS password when prompted. Once the commands are successfully executed, Tanium Client is removed from your device.

</details>
<details>
  <summary>d. Remove Cloudflare WARP Client</summary><br>

  1. Click the **Finder** icon in the **Dock**.
  2. Choose **Applications**.
  3. Search for **Cloudflare WARP.app**.
  4. If available, open **Terminal** and run the following command:
    ```
    sudo /bin/sh /Applications/Cloudflare\ WARP.app/Contents/Resources/uninstall.sh
    ```

  5. When prompted, enter your macOS password.

</details>


<details>
  <summary>e. Remove current antivirus solution on the device</summary><br>

  1. Open **Terminal** and run `mdatp health`.
  2. Note down the displayed **org_id**.

  ?> If this command does not return anything, it confirms that your device does not have Microsoft Defender. Proceed to onboard your device to SEED.

  3. Identify the organisation of the Defender or the antivirus on your device.

  ?> Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping.md) for identifying your Defender or antivirus organisation.

  4. Based on the organisation, choose the required step from the following:
    - If your organisation id corresponds to WOG, contact [GCC2.0 team](https://form.gov.sg/#!/6099efa30d6a0a0012dff367), to get the offboarding script for macOS.
    - If your organisation id corresponds to TechPass, contact your Defender administrator to get the offboarding scripts for your operating system for macOS.
    - If your organisation id corresponds to Hive, contact [GDS team](mailto:gds_den@tech.gov.sg) to get the Hive offboarding script for macOS and proceed to step 5.
    - For all other organisation ids, contact your current MDM administrator to unerol your device from the respective antivirus.

  ?>  Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, *WindowsDefenderATPOffboardingScript_valid_until_2021-11-10.py*

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
