# Remove existing softwares for Windows

There are few softwares which if already installed are to be removed before proceeding with the SEED onboarding process.

This section explains how public officers and vendors can remove those softwares.
<details>
  <summary>a. Remove existing MDM software</summary><br>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Accounts**.
  3. From the left menu, choose **Access work or school**.
  4. If your device is managed by an MDM, your username in your organisation's domain will be displayed under **Work or school account**. Click **Work or school account** and then select **Disconnect**.



</details>

<details>
  <summary>b. Remove Tanium Client</summary><br>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Apps** and search for **Tanium Client**.
  3. If available, choose it and then click **Uninstall**.

</details>

<details>
  <summary>c. Remove pre-existing Cloudflare WARP client</summary><br>

  1. Click **Start** icon on the taskbar.
  2. Go to **Settings** > **Apps** and search for **Cloudflare WARP**.
  3. If available, choose **Cloudflare WARP** and then click **Uninstall**.

</details>
<details>
  <summary>d. Offboard from Windows Defender for Endpoint</summary><br>

  1. In the search box on the taskbar, type **regedit**, then select **Registry Editor** from the results.  
  2. In the **Registry Editor**, go to **Computer** > **HKEY_LOCAL_MACHINE** > **SOFTWARE** > **Policies** > **Microsoft**
  3.Choose **Windows Advanced Threat Protection** and search for **OnboardingInfo**.
  4. If available, [get the offboarding scripts](get-offboarding-scripts-for-microsoft-defender-atp) for your device or you may proceed to [onboard to SEED](seed-onboarding-instructions-windows).
  5. Save the offboarding script in the **Downloads** folder.
  6. Type **cmd** in the search box on the taskbar.
  7. Select **Command Prompt** and right-click to choose **Run as administrator**.
  8. If prompted, enter your Windows password.
  9. Run the below in the Command prompt.

   ```
   cd “%USERPROFILE%\Downloads\”
  .\name_of_offboarding_script.cmd
  ```

</details>  
