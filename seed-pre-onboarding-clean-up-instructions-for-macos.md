# Remove existing softwares for macOS

There are few softwares which if already installed are to be removed before proceeding with the SEED onboarding process.

This section explains how public officers and vendors can remove those softwares.

<details>
  <summary>a. Remove existing MDM software</summary><br>

  *To verify if you already have an MDM software* :
  1. Go to the **Apple** menu > **System Preferences** or click the **System Preferences** icon in the **Dock**.
  2. Go to **Profiles** and from the left menu, choose **Management Profile**.
  <kbd>![verify-other-mdm](images/onboarding-for-macos/verify-other-mdm.png)</kbd>
  3. At the bottom left, if you see "This Mac is supervised and managed by *your-organisation-name* it indicates you already have an MDM software.

  ?> To unenrol your device from MDM softwares other than Microsoft Endpoint Manager, contact your organisation's IT administrator.

</details>
<details>
  <summary>b. Unenrol from Microsoft Endpoint Manager</summary><br>

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
  <summary>e. Remove Microsoft Defender for Endpoint</summary><br>

  1. Go to the **Terminal** and run `mdatp health`. If your device is currently using an antivirus solution other than Microsoft Defender ATP, this command returns nothing. It means your device is not enrolled on any MDM solution and proceed to [onboard to SEED](seed-onboarding-instructions-for-macos).
  2. Take note of the **org_id** displayed. This is the organisation id of the MDM solution.
  3. Contact your organisation's MDM Administrator or Defender Administrator to get the respective offboarding script.
   Open Click the **Finder** icon in the **Dock**.
  2. Choose **Applications**.
  3. Search for **Microsoft Defender for Endpoint.app**.
  4. If available, [get the offboarding scripts](get-offboarding-scripts-for-microsoft-defender-atp) for your device or proceed to [onboard to SEED](seed-onboarding-instructions-for-macos).
  5. Save the offboarding script in the **Downloads** folder.
  6. Go to the **Terminal** and run the following command:
    ```
    sudo python ~/Downloads/name_of_offboarding_script.py
    ```
  ?> Type the file name of the offboarding script provided to you.

  7. Go back to the **Finder** icon in the **Dock**.
  8. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.
  9. Drag the app to the Trash, or select the app and choose **File** > **Move to Trash**.


</details>
