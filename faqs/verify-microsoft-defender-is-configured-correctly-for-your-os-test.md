### Ensure Microsoft Defender is configured correctly for your OS

<br>
<details>
  <summary>macOS</summary>

  1. Open **Terminal** and run `mdatp health`.
  2. Note down the displayed **org_id**.   

  ?> If this command does not return anything, it indicates your device does not have Defender. Hence, [proceed to onboard your device to SEED](seed-onboarding-instructions-for-macos).

  The org_id displayed depends on the TechPass account used for enrolling your device to SEED. For more information, refer to [organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping).

  3. Based on the **org_id**, identify the organisation of the Defender or the antivirus on your device.
  4. Choose the required step from the following:

  - If your organisation id corresponds to organisations such as WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and you can ignore the rest of this section.

  - If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [GDS team](mailto:gds_den@tech.gov.sg) to to get the Hive offboarding script and proceed to step 5.

  - For all other organisation ids, contact your organisation's MDM administrator or Defender administrator to get the respective offboarding script and proceed to step 5.

  5. Once you get the offboarding script, run it on your device to unenrol Defender from your device completely.

   ?> For more information on how to run the offboarding script to remove Defender, refer to **step d. Remove Microsoft Defender for Endpoint** on [Get the offboarding scripts for Microsoft Defender](get-offboarding-scripts-for-microsoft-defender-atp).


Now, within few hours, **Intune** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

At any time, users can Sign in to Company Portal app, click the three dots and choose **Check status** to check for policy or profile updates. It may take a while to complete the synchronisation. When completed, the screen will show the timestamp of the last successful sync.


</details>

<details>
  <summary>Windows</summary>

1. In the search box on the taskbar, type **regedit**.
2. Choose **Registry Editor** from the results and click **Run as administrator**.
3. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Threat Protection** > **Status**. The OrgId of the Defender or antivirus running on your device will be displayed here.

?> If you do not see the **Windows Advanced Threat Protection** folder, it indicates your device does not have Microsoft Defender. Hence, [proceed to onboard your device to SEED](seed-onboarding-instructions-windows).

The org_id displayed depends on the TechPass account used for enrolling your device to SEED. For more information, refer to [organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping).

4. Based on the **OrgId**, identify the organisation of the Defender or the antivirus on your device.
5. Choose the required step from the following:

- If your organisation id corresponds to organisations such as WOG or TechPass, it indicates that **Microsoft Defender** has been configured correctly and ignore the rest of this section.

- If your organisation id corresponds to Hive, it indicates that your device is still enrolled with Hive. Contact [GDS team](mailto:gds_den@tech.gov.sg) to to get the Hive offboarding script and proceed to step 6.

- For all other organisation ids, contact your organisation's MDM administrator or Defender administrator to get the respective offboarding script and proceed to step 6.

6. Once you get the offboarding script for your current MDM organisation, run it on your device to unenrol your device from it completely.

 ?> For more information on how to run the offboarding script, refer to **step d. Remove Microsoft Defender for Endpoint** on [SEED offboarding guide for Windows users](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-offboarding-instructions-for-windows).

 Now, within few hours, **Intune** pushes the **Microsoft Defender** client to your device with the correct configurations. For more information on the duration, refer to [Microsoft Documentation](https://docs.microsoft.com/en-us/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

 At any time, users can manually sync by going to **Start** > **Settings** > **Accounts** > **Access work or school** > **Work or School Account** > **Info** > **Sync**. Alternatively, Open the Company Portal app on your device, go to **Settings** > **Sync**. Wait while Company Portal syncs your device. When complete, the screen will show the timestamp of the last successful sync.

<!--7. Repeat steps 1-5 to confirm if **Microsoft Defender** is configured correctly.-->
