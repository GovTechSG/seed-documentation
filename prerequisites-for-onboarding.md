# Prerequisites for SEED
<div class="warn">

Take note of the following before you proceed with the SEED onboarding:

  - You can onboard only a non-GSIB or a non-DWP device to SEED.

  - If you are a public officer, after you enrol in Intune, you need to submit your Intune device ID to complete the SEED onboarding for your device.

  - After you complete the onboarding process, you will receive an email confirming your successful onboarding to SEED and your device will be automatically renamed and restarted.

  - After the automatic restart, macOS users will be prompted to reset their password to enforce a strong password policy.

  - If the device onboarded to SEED is compromised or lost, the respective agency may remotely wipe the device, including any personal information.

</div>

Before you onboard your device to SEED, there are few things which you need to start the onboarding and few things to ensure a successful onboarding.

To begin with, you'll need:

1. An active [TechPass account](#get-a-techpass-account).
1. [SEED provisioning](#seed-provisioning) for you to onboard your device.
1. [Devices with supported operating systems and the required permissions](#supported-operating-systems-and-devices-for-seed).

Things to ensure a successful onboarding:

1. [Remove existing softwares on your device](#remove-existing-softwares-on-your-device).
1. If you are onboarding a macOS device, [verify if System Integrity Protection (SIP) is enabled](#verify-if-system-integrity-protection-is-enabled).
1. [Encrypt your hard disk drive to protect your data at rest](#encrypt-your-hard-disk-drive-to-protect-your-data-at-rest).

### Get a TechPass account

<!-- tabs:start -->

#### **Public officers**

1. [Set up security verification for your WOG account](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-public-officers-using-non-se-machines?id=step-1-set-up-security-verification-for-your-wog-account)
1. [Sign up for a TechPass account](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-public-officers-using-non-se-machines?id=step-2-sign-up-for-techpass) and request SEED provisioning.
1. [Accept invitation](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-public-officers-using-non-se-machines?id=step-3-accept-invitation).
1. [Onboard to TechPass](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-public-officers-using-non-se-machines?id=step-4-onboard-to-techpass).

#### **Vendors/Contractors**

1. [Request for TechPass account and SEED provisioning from your project manager or reporting officer](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-vendors-to-techpass?id=step-1-get-a-techpass-account-and-seed-licence-for-vendors-or-contractors).
2. [Sign in to TechPass](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-vendors-to-techpass?id=step-2-first-time-sign-in-using-initial-password).
3. [Set up MFA for your TechPass account](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-vendors-to-techpass?id=step-3-configure-and-verify-mfa-for-techpass-account).
4. [Reset initial password](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-vendors-to-techpass?id=step-4-reset-your-initial-password).
5. [Accept TechPass and MDM policies](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-vendors-to-techpass?id=step-5-accept-terms-of-use-privacy-policy-and-mobile-device-management-acceptable-use-policy).

<!-- tabs:end -->

### SEED provisioning
If you had requested SEED provisioning while signing up for your TechPass account, SEED will be provisioned to you and you will receive an email with instructions on how to onboard your device to SEED.

?> If you are a public officer, who already has a TechPass account and needs SEED provisioning, go to your profile page on the [TechPass portal](http://portal.techpass.gov.sg/), request SEED provisioning and follow the on-screen instructions. For more information, refer to [TechPass documentation](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/onboard-to-seed).

### Supported operating systems and devices for SEED
- A non-GSIB or a non-DWP device that runs on Windows 10 Pro/Enterprise versions or on macOS Big Sur 11 and later versions.
- You must have Administrator rights on the device.

### Remove existing softwares on your device
Before onboarding to SEED, you need to remove the Following software solutions from your device:

- current MDM software
- Tanium client or any other unified endpoint management and security platform
- Cloudflare WARP or any other software used for privacy and secured connections
- Defender or any other antivirus solution.

This section explains how public officers and vendors can remove those softwares.

<!-- tabs:start -->

#### **macOS**

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
  </div>-->

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

#### **Windows**

<details>
  <summary>a. Remove existing MDM software</summary>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Accounts**.
  3. From the left menu, choose **Access work or school**.

  ?> If your device is managed by an MDM, your username in your organisation's domain will be displayed under **Work or school account**.

  4. Click **Work or school account** and then select **Disconnect**.


</details>

<details>
  <summary>b. Remove Tanium Client</summary>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Apps** and search for **Tanium Client**.
  3. If available, choose it and then click **Uninstall**.

</details>

<details>
  <summary>c. Remove Cloudflare WARP Client</summary>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Apps** and search for **Cloudflare WARP**.
  3. If available, choose **Cloudflare WARP** and then click **Uninstall**.

</details>
<details>
  <summary>d. Remove current antivirus solution on the device</summary><br>

  1. In the search box on the taskbar, type **regedit**.
  2. Choose **Registry Editor** from the results and click **Run as administrator**.
  3. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Threat Protection** > **Status**. The OrgId of the Defender or antivirus running on your device will be displayed here.

  ?> If you do not see the **Windows Advanced Threat Protection** folder, it indicates your device is not enrolled with any MDM solution. Proceed to onboard your device to SEED.

  4. Identify the organisation of the Defender or the antivirus on your device.

  ?> Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping) for identifying your Defender or antivirus organisation.

  5. Based on the organisation, choose the required step from the following:
    - If your organisation id corresponds to WOG, contact [GCC2.0 team](https://form.gov.sg/#!/6099efa30d6a0a0012dff367), to get the offboarding script for Windows.
    - If your organisation id corresponds to TechPass, contact your Defender administrator to get the offboarding scripts for your operating system for Windows.
    - If your organisation id corresponds to Hive, contact [GDS team](mailto:gds_den@tech.gov.sg) to get the Hive offboarding script for Windows and proceed to step 6.
    - For all other organisation ids, contact your current MDM administrator to unerol your device from the respective antivirus.

    ?>  Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, *WindowsDefenderATPOffboardingScript_valid_until_2021-11-10.cmd*


   6. Save the offboarding script in your **Downloads** folder.
   7. Go to **Start** and type **cmd**.
   8. Right-click on **Command Prompt** and select **Run as administrator**.
   9. If prompted, enter your Windows password.
   10. Run the following commands:
     ```
     cd "%USERPROFILE%\Downloads\"

     .\name_of_offboarding_script.cmd
     ```
?> Name of the .cmd file mentioned in this command is only an example. When you run the command, specify the file name of the offboarding script provided to you.

   </details>  


<!-- tabs:end -->

### Verify if System Integrity Protection is enabled

If you are onboarding a macOS device, verify if System Integrity Protection (SIP) is enabled on your device to prevent unauthorised code executions.

1. Open **Terminal** and run the command `csrutil status`.
2. If the result says it is currently disabled, run the command `csrutil enable`.
3. Restart your device.

### Encrypt your hard disk drive to protect your data at rest

<!-- tabs:start -->

#### **macOS**

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.

2. Click the **FileVault** tab.

3. If you see **Turn on FileVault**, click the lock icon and use your Touch ID or enter your password to unlock.

4. Click **Turn on FileVault**.

5. When prompted to specify how you would like to unlock your device if you forget your device password,  select **Create a recovery key and do not use my iCloud account**.

<kbd>![create-recovery-key](images/onboarding-for-macos/create-recovery-key-1.png)</kbd>

6. Save the recovery key on a different device.

#### **Windows**

1. Click the **Start** icon on the taskbar and search for **Manage BitLocker** and choose to open it. Check if BitLocker is turned on for your OSDisk. A padlock on the drive indicates that BitLocker is turned on ![](images/onboarding-instructions-for-windows/bitlocker-enabled.png). If yes, proceed to **Enrol on Cloudflare using WARP client**.
2. If BitLocker is not turned on, select **Turn on BitLocker**.
3. When asked to choose how to unlock your drive at start up, select **Enter a password**.

<kbd>![enter-pwd](images/onboarding-instructions-for-windows/enter-pwd.png ':size=600')</kbd>

4. To backup the recovery key for your computer, insert a thumb drive or any other form of removable storage device into the USB port of your computer.
5. When asked how you would like to back up your recovery key, select **Save to a file**, save the file in the inserted removable storage device and click **Next**.

?> Remove the external storage device and transfer this file to a safe location other than your computer.

<kbd>![save-to-file](images/onboarding-instructions-for-windows/save-to-file.png ':size=600')</kbd>

6. When asked how much of your drive to be encrypted, select **Encrypt entire drive(slower but best for PCs and drives already in use)** and click **Next**.

<kbd>![encrypt-entire-drive](images/onboarding-instructions-for-windows/encrypt-entire-drive.png ':size=600')</kbd>

7. When asked which encryption mode to use, select **New encryption mode(best for fixed drives on this device)** and click **Next**.

<kbd>![new-encryption-mode](images/onboarding-instructions-for-windows/new-encryption-mode.png ':size=600')</kbd>

8. The device encryption page is displayed. <!--Click **Start encrypting**.-->

?> Depending on your system settings, you may be prompted to restart your computer before the encryption can start. If you are prompted to do so, restart your device, then return to the **Manage BitLocker** window to verify if encryption has started. A padlock icon on the hard drives in your Windows 10 File Explorer indicates that the hard drive has been encrypted.

<!-- tabs:end -->








### Next steps
- [Proceed to onboard your device to SEED](onboard-device-to-seed)
