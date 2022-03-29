### Ensure Microsoft Defender is configured correctly for your OS

<br>
<details>
  <summary>macOS</summary>

  1. Open **Terminal** and run `mdatp health`.
  2. Note down the displayed **org_id**.

  ?> If this command does not return anything, it indicates your device does not have Defender ATP or any antivirus solution and you need to onboard your device in to SEED.

  3. Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping) and based on the **org_id**, identify the organisation of the Defender ATP or the antivirus on your device.
  4. Choose the required step from the following:
  - If your organisation id corresponds to organisations such as WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and ignore the rest of this section.
  - If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [GDS team](mailto:gds_den@tech.gov.sg) to to get the Hive offboarding script and proceed to step 5.
  - For all other organisation ids, contact your organisation's MDM administrator or Defender ATP administrator to get the respective offboarding script and proceed to step 5.

?> Refer to [Get the offboarding scripts for Microsoft Defender ATP ](get-offboarding-scripts-for-microsoft-defender-atp).

  5. Save the offboarding script to the **Downloads** folder.
  6. Go to **Terminal** and run the following command:
    ```
    sudo python ~/Downloads/name_of_offboarding_script.py
    ```
  ?> Name of the python file in this command is only an example. When you run the command, specify the file name of the offboarding script provided to you.

  7. Go back to the **Finder** icon in the **Dock**.
  8. Choose **Applications** and search for **Microsoft Defender for Endpoint.app**.
  9. Drag the app to the Bin, or select the app and choose **File** > **Move to Bin**.

Now, within few hours, **Endpoint Manager** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

At any time, users can Sign in to Company Portal app, click the three dots and choose **Check status** to check for policy or profile updates. Wait while Company Portal syncs your device. When complete, the screen will show the timestamp of the last successful sync.

6. Repeat steps 1-4 to confirm if **Microsoft Defender** is configured correctly.

</details>

<details>
  <summary>Windows</summary>

1. In the search box on the taskbar, type **regedit**.
2. Choose **Registry Editor** from the results and click **Run as administrator**.
3. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Threat Protection** > **Status**. The OrgId of the Defender ATP or antivirus running on your device will be displayed here.

?> If you do not see the **Windows Advanced Threat Protection** folder, it indicates your device is not enrolled with any MDM solution. Proceed to onboard your device to SEED.

4. Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping) and based on the **OrgId**, identify the organisation of the Defender or the antivirus on your device.
5. Based on the organisation, choose the required step from the following:
- If your organisation id corresponds to organisations such as WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and ignore the rest of this section.
- If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [GDS team](mailto:gds_den@tech.gov.sg) to to get the Hive offboarding script and proceed to step 6.
- For all other organisation ids, contact your organisation's MDM administrator or Defender ATP administrator to get the respective offboarding script and proceed to step 6.
 6. Once you get the offboarding script for your current MDM organisation, run it on your device to unenrol your device from it completely.

 ?> For more information on how to run the offboarding script, refer to **step d. Remove Microsoft Defender for Endpoint** on [SEED offboarding guide for Windows users](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-offboarding-instructions-for-windows).

 Now, within few hours, **Endpoint Manager** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

 At any time, users can manually sync by going to **Start** > **Settings** > **Accounts** > **Access work or school** > **Work or School Account** > **Info** > **Sync**. Alternatively, Open the Company Portal app on your device, go to **Settings** > **Sync**. Wait while Company Portal syncs your device. When complete, the screen will show the timestamp of the last successful sync.

7. Repeat steps 1-5 and confirm if **Microsoft Defender** is configured correctly.
