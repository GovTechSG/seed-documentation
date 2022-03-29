# Remove existing softwares for Windows

Remove the following software solutions from your device before proceeding to onboard in to SEED:

- current MDM software
- Tanium client or any other unified endpoint management and security platform
- Cloudflare WARP or any other software used for privacy and secured connections
- Defender or any other antivirus solution.

This section explains how public officers and vendors can remove those softwares for their Windows device.

<details>
  <summary>a. Remove existing MDM software</summary>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Accounts**.
  3. From the left menu, choose **Access work or school**.
  4. If your device is managed by an MDM, your username in your organisation's domain will be displayed under **Work or school account**. Click **Work or school account** and then select **Disconnect**.


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
  <summary>d. Remove current anitivirus solution on the device</summary><br>

  1. In the search box on the taskbar, type **regedit**.
  2. Choose **Registry Editor** from the results and click **Run as administrator**.
  3. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Threat Protection** > **Status**. The OrgId of the Defender or antivirus running on your device will be displayed here.

  ?> If you do not see the **Windows Advanced Threat Protection** folder, it indicates your device is not enrolled with any MDM solution. Proceed to onboard your device in to SEED.

  4. Identify the organisation of the Defender or the antivirus on your device.

  ?> Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping) for identifying your Defender or antivirus organisation.

  5. Based on the organisation, choose the required step from the following:
    - If your organisation id corresponds to WOG, contact [GCC2.0 team](mailto:gcc2.0_support@tech.gov.sg), to get the offboarding script for Windows.
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
