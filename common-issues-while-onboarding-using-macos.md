## Common issues while onboarding using macOS

<details>
  <summary>1. What should I do if profile installation fails while installing the management profile?</summary><br>

  <kbd>![profile-installation-failed](images/onboarding-for-macos/profile-installation-failed.png)</kbd>

    1. Go to the **Apple** menu > **System Preferences** > **Profiles**.
    2. If **Management Profile** is already an existing profile, select it and remove by clicking the minus icon at the bottom left corner.

</details>


<details>
  <summary>2. While enabling FDA, I can't find <b>TaniumClient</b>. What should I do?</summary><br>

  1. Open the **Terminal** application and run the command: ``sudo chmod 755 /Library/Tanium/TaniumClient``.
  2. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  3. Click the **Privacy** tab.
  4. From the side menu, choose **Full Disk Access**.
  5. Click the lock icon at the bottom and use your Touch ID or enter your password to unlock.
  6. Click the plus icon at the bottom and from **Applications**, select **TaniumClient**.
  7. Select the checkbox beside **TaniumClient**.

</details>
