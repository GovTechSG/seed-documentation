# Common issues while onboarding using macOS

<details>
  <summary>1. What should I do if profile installation fails while installing the management profile?</summary>

<kbd>![profile-installation-failed](images/onboarding-for-macos/profile-installation-failed.png)</kbd>

1. Ensure you received an email from us confirming the licence required for SEED onboarding has been assigned to you. If yes, proceed to step 2.
2. Go to the **Apple** menu > **System Preferences** > **Profiles**.
3. If **Management Profile** is already an existing profile, select it and remove it by clicking the minus icon at the lower-left corner.

</details>


<details>
  <summary>2. While enabling FDA, I can't find <b>TaniumClient</b>. What should I do?</summary>

  1. Open the **Terminal** application and run the command: ``sudo chmod 755 /Library/Tanium/TaniumClient``.
  2. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  3. Click the **Privacy** tab.
  4. From the side menu, choose **Full Disk Access**.
  5. Click the lock icon at the bottom and use your Touch ID or enter your password to unlock.
  6. Click the plus icon at the bottom.
  7. Go to **Macintosh HD** > **Library** > **TaniumClient** and select the application file **TaniumClient**.
  8. Ensure the checkbox beside **TaniumClient** is selected

</details>

<details>
<summary>3. While enabling FDA, I can't find <b>Microsoft Intune Agent</b> and <b>Microsoft Defender ATP</b>. What should I do?</summary>

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **Privacy** tab.
3. From the side menu, choose **Full Disk Access**.
4. Click the lock icon at the bottom and use your Touch ID or enter your password to unlock.
5. Click the plus icon at the bottom and do the following as required:
  1. To add **Microsoft Intune Agent**, go to **Macintosh HD** >  **Library** > **Intune** and choose **Microsoft Intune Agent** and click **Open**.
  2. To add **Microsoft Defender ATP**, go to **Application** > select **Microsoft Defender ATP** and click **Open**.
</details>

<details>

<summary>4. While enabling FDA, I can't find <b>Microsoft Defender ATP Security Extension</b>. Can I proceed with my onboarding?</summary>

Yes, you may proceed with your SEED onboarding and the Microsoft Defender ATP Security Extension should be available within four hours time. If it is still not available after four hours, please contact gcc2.0_support@tech.gov.sg as it is required to ensure the completeness of your onboarding.

</details>
