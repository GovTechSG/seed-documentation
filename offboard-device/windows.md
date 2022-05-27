# Windows

## Step 1: Remove your  device from Microsoft Intune

1. Click **Start** icon on the taskbar.
2. Go to  **Settings** > **Accounts** > **Access work or school**.
3. Click your account and select **Disconnect**.

## Step 2: Remove the Tanium Client

1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps**.
3. Search for **Tanium Client** and then select **Uninstall**

## Step 3: Remove the Cloudflare WARP client

1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps**.
3. Search for **Cloudflare WARP** and then select **Uninstall**.

## Step 4: Remove Microsoft Defender for Endpoint

To remove Microsoft Defender for Endpoint from your device, offboard the device from it using the offboarding script.

  1. In the search box on the taskbar, type **regedit**.
  2. Choose **Registry Editor** from the results and click **Run as administrator**.
  3. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Microsoft** > **Windows Advanced Threat Protection** > **Status**. The OrgId of the Defender or antivirus running on your device will be displayed here.
  4. Identify the organisation of the Defender or the antivirus on your device.

> **Note:**
> Refer to [Organisation IDs and organisation mapping](faqs/organisation-ids-and-mapping) for identifying your Defender or antivirus organisation.

  5. Based on the organisation, choose the required step from the following:
    - If your organisation id corresponds to WOG, contact [GCC2.0 team](https://form.gov.sg/#!/6099efa30d6a0a0012dff367), to get the offboarding script for Windows.
    - If your organisation id corresponds to TechPass, contact your Defender administrator to get the offboarding scripts for your operating system for Windows.

> **Note:**
> Check if the script that you received has not yet expired. The expiry date is indicated on the file name. For example, *WindowsDefenderATPOffboardingScript_valid_until_2021-11-10.cmd*


   6. Save the offboarding script in your **Downloads** folder.
   7. Go to **Start** and type **cmd**.
   8. Right-click on **Command Prompt** and select **Run as administrator**.
   9. If prompted, enter your Windows password.
   10. Run the following commands:
     ```
     cd "%USERPROFILE%\Downloads\"

     .\name_of_offboarding_script.cmd
     ```
> **Note:**
> Name of the .cmd file mentioned in this command is only an example. When you run the command, specify the file name of the offboarding script provided to you.  
