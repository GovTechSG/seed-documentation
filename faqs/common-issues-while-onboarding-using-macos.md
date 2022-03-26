# Common onboarding questions for macOS users

<details>
  <summary>1. What should I do if profile installation fails while installing the management profile?</summary>

<!--<kbd>![profile-installation-failed](images/onboarding-for-macos/profile-installation-failed.png)</kbd>-->

1. Ensure you received an email from us confirming the licence required for SEED onboarding has been assigned to you. If yes, proceed to step 2.
2. Go to the **Apple** menu > **System Preferences** > **Profiles**.
3. If **Management Profile** is already an existing profile, select it and remove it by clicking the minus icon at the lower-left corner.
4. If you are unable to remove Management Profile, uninstall **Company Portal**.
5. Reinstall [Company Portal](https://go.microsoft.com/fwlink/?linkid=853070).
6. Retry onboarding your device to SEED from step [**a. Set up Microsoft Endpoint Manager to get the required applications and device configuration**](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-onboarding-instructions-for-macos).


</details>
<hr/>


<details>
  <summary>2. While enabling FDA, I can't find <b>TaniumClient</b>. What should I do?</summary>

  1. Open the **Terminal** application and run the command: ``sudo chmod 755 /Library/Tanium/TaniumClient``.
  2. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
  3. Click the **Privacy** tab.
  4. From the left pane, choose **Full Disk Access**.
  5. Click the lock icon at the lower left and use your Touch ID or enter your password to unlock.
  6. Click the plus icon on the **Full Disk Access** pane.
  7. Go to **Macintosh HD** > **Library** > **TaniumClient** and select the application file **TaniumClient**.
  8. Ensure the checkbox beside **TaniumClient** is selected.

</details>
<hr/>

<details>
<summary>3. While enabling FDA, I can't find <b>Microsoft Intune Agent</b> and <b>Microsoft Defender for Endpoint</b>. What should I do?</summary>

1. Go to the **Apple** menu > **System Preferences** > **Security & Privacy**.
2. Click the **Privacy** tab.
3. From the left pane, choose **Full Disk Access**.
4. Click the lock icon at the lower left and use your Touch ID or enter your password to unlock.
5. Click the plus icon on the Full Disk Access pane and do the following as required:
  - To add **Microsoft Intune Agent**, go to **Macintosh HD** >  **Library** > **Intune** and open **Microsoft Intune Agent.app**.
  - To add **Microsoft Defender for Endpoint**, go to **Application** > select **Microsoft Defender for Endpoint** and click **Open**.
</details>
<hr/>

<details>

<summary>4. While enabling FDA, I can't find <b>Microsoft Defenders Endpoint Security Extension</b>. Can I proceed with my onboarding?</summary>

<p>Yes, you may proceed with your SEED onboarding and the Microsoft Defenders Endpoint Security Extension should be available within four hours time. If it is still not available after four hours, please contact gcc2.0_support@tech.gov.sg as it is required to ensure the completeness of your onboarding.</p>

</details>
<hr/>

<details>

<summary>5. While enabling FileVault or FDA, I am unable to unlock <strong>Security & Privacy</strong> preferences using my current password.</summary>

<p>When your device is enrolled with Microsoft Endpoint Management's Intune, a new password policy comes into effect and this requires you to reset password.  If you enable FileVault or FDA only while onboarding to SEED, reset your password before <strong>step c. Encrypt your hard disk to protect your data at rest</strong> as mentioned on the <a href="https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/seed-onboarding-instructions-for-macos">SEED onboarding guide for macOS users</a>.</p>

*To reset password while enabling FileVault or FDA*:
1. Go to the **Apple** menu > **Lock Screen** or use keyboard shortcut **Command+Control+Q** .
2. Enter your password and press **return**. You will be prompted to reset password.
3. Reset your password and make sure it meets the following requirements:
  - Contain at least 12 characters
  - Not have two consecutive or three sequential characters
  - Contain at least one number and one alphabetic character
  - Not be the same as the previous three passwords

</details>
<hr />

<details>
<summary>After resetting my macOS password, I am unable to log in using the new password, why?</summary>
<p>This occurs if your new password does not meet the following password requirements:</p>
<ul>
<li>have at least 12 characters</li>
<li>should not have two consecutive or three sequential characters</li>
<li>have at least one number and one alphabetic character</li>
<li>should not be the same as the previous three passwords.</li>
</ul>

<p>There are three password reset options and you may choose one of them to reset password.</p>

<details><summary>Reset password using your Apple ID</summary>
 <p>Refer to <a href="https://support.apple.com/en-gb/guide/mac-help/mh35902/mac">Reset your Mac login password uisng Apple ID</a> for step-by-step instructions.</p></details>

  <details><summary>Reset password using a recovery key</summary>

  *To reset password using recovery key* :
  1. Click the question mark next to the password field in the login window.

  ?> If you don't see a question mark, press and hold the power button until your Mac shuts down, then press the power button to restart your Mac. Alternatively, enter any password three times.

  2. Click  **If you forgot your password, you can reset it using your Recovery Key**.
  3. Enter the recovery key. Make sure to use uppercase letters and to enter the hyphens.
  4. Reset your password.

  </details>

  <details><summary>Reset password using recovery mode</summary>
  <p>If you have do not have an Apple ID or a recovery key, start your Mac in recovery mode.</p>

  *Restart Mac in recovery mode to reset password* :
  1. If your macOS device has M1 chip, turn off the device by pressing the power button and if your macOS device has Intel chip, turn off the device by pressing the power button while holding down `Command + R` keys.

  ?> Release the keys when you see the load bar.

  2. Go to **Applications** > **Utilities** > **Terminal**.
  3. Enter `resetpassword` and press `return`. The **Reset Password** assistant will be displayed.
  4. Select **My password doesn’t work when logging in** and click **Next**.
  5. If prompted, select the user account for which you need to change password.
  6. Type the old password and new password in the respective fields.
  7. Type the new password in **Verify password** and specify a **Password hint**.
  8. Click **Next**.

  ?> If you are still unable to reset your password, boot into Recovery Mode again repeat steps 2-4 and disable FileVault on the volume “Macintosh HD.

  9. Restart your device and in the login screen, choose your user account and type your new password.

  </details>
