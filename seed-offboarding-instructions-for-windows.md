# SEED Offboarding guide for Windows users

This section guides existing SEED users to offboard from it. The offboarding journey has the following steps:

<details>
<summary>a. Remove your  device from Microsoft Endpoint Manager</summary>

1. Click **Start** icon on the taskbar.
2. Go to  **Settings** > **Accounts** > **Access work or school**.
3. Click your account and select **Disconnect**.
</details>

<details>
<summary>b. Remove the Tanium Client</summary>

1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps**.
3. Search for **Tanium Client** and then select **Uninstall**

</details>

<details>
<summary>c. Remove the Cloudflare WARP client</summary><br>

1. Click **Start** icon on the taskbar.
2. Go to **Settings** > **Apps**.
3. Search for **Cloudflare WARP** and then select **Uninstall**.
</details>
<details>
<summary>d. Offboard from and uninstall Microsoft Defender for Endpoint</summary><br>
To remove Microsoft Defender for Endpoint from your device, first you need to offboard from it using the offboarding script.

Check if the script that you received earlier has not yet expired.

?>  The expiry date is indicated on the file name.

For example, *WindowsDefenderATPOffboardingScript_valid_until_2021-11-10.cmd*

If the script has already expired, choose one of the below options as appropriate:

- If you are a public officer, contact [SEED team](mailto:gcc2.0_support@tech.gov.sg) to get the offboarding script.

- If you are a vendor, contact your Defender administrator to [get the offboarding script](get-offboarding-scripts-for-microsoft-defender-atp).

Once you have the valid offboarding script, do the following to remove Microsoft Defender for Endpoint:
1. Save the offboarding script in your **Downloads** folder.
2. Go to **Start** and type **cmd**.
3. Right-click on **Command Prompt** and select **Run as administrator**.
4. If prompted, enter your Windows password.
5. Run the following commands:
  ```
  cd "%USERPROFILE%\Downloads\"

  .\name\_of\_offboarding\_script.cmd
  ```

</details>
