<details>
  <summary>Do I need to change my SEED onboarding password after a year, and what are the password requirements for it?</summary>

  Yes, you are required to change your SEED onboarding password after a year. The password requirements for SEED onboarding are as follows:

- It should contain at least 12 characters.
- It should not be the same as the previous three passwords.
- The same character cannot be used consecutively.
- It cannot have three sequential characters.
- It should contain at least one number and one alphabetic character.

  > **Note**: Users of macOS devices running version 10.14.2 and later (excluding all versions of macOS 10.15 Catalina) are required to change their password after upgrading to a new major OS version. For example, following an update to Big Sur (macOS 11) or Monterey (macOS 12), users must update their password before they can sign in, even if their current password complies with the new requirements.
  
</details>

<details>
  <summary>When enabling FileVault or FDA, I am unable to unlock Security & Privacy preferences using my current password. What should I do?</summary>

  This issue may arise due to a new password policy that requires you to reset your password. 
  
  Follow these steps:

1. Go to the **Apple** menu and choose **Lock Screen** or press **Command+Control+Q**.
2. Enter your current password and press **Return**.
3. You will be prompted to reset your password.
</details>


<details>
  <summary>How can I reset my password on macOS?</summary>
If you encounter password reset issues on macOS, it may be due to new password requirements. Before you proceed to reset your macOS password, please ensure that the new password meets the following requirements:

- It should contain at least 12 characters.
- It should not be the same as the previous three passwords.
- The same character cannot be used consecutively.
- It cannot have three sequential characters.
- It should contain at least one number and one alphabetic character.

Now, here are three options for resetting your macOS password:

<details>
  <summary>Reset password using Apple ID</summary>

Refer to [Reset your macOS login password using Apple ID](https://support.apple.com/en-gb/guide/mac-help/mh35902/mac) for step-by-step instructions.
</details>

<details>
<summary>Reset password Using recovery key</summary>

**To reset your password using a recovery key**:

1. Click the question mark next to the password field in the login window.

?> If you do not see a question mark, press and hold the power button until your Mac shuts down, then press the power button to restart your Mac. Alternatively, enter any password three times.

2. Click **If you forgot your password, you can reset it using your Recovery Key**.
3. Enter the recovery key, making sure to use uppercase letters and include hyphens.
4. Reset your password.
</details>

<details>
  <summary>Reset password using recovery mode</summary>

If you do not have an Apple ID or a recovery key, you can reset your password in recovery mode based on your Mac's chip:

<!-- tabs:start -->
#### **Apple silicon chip**
1. Restart or shut down your device by pressing the power button until the screen is black and all lights, including the Touch Bar, are off.
2. Press and hold the power button on your Mac until the **Loading startup options** screen appears. After a few seconds, you’ll see two icons: **Macintosh HD** and **Options**.
3. Click **Options** and select your user account, then click **Next**.
4. Enter your password to continue.
5. Go to **Applications** > **Utilities** > **Terminal**.
6. Enter `resetpassword` and press `return`. The **Reset Password** assistant will be displayed.
7. Choose **My password doesn’t work when logging in** and click **Next**.
8. If prompted, select the user account for which you need to change the password.
9. Enter the old password and your new password in the respective fields.
10. Type the new password again to verify and provide a password hint.
11. Click **Next**.
12. Restart your device and, on the login screen, select your user account and enter the new password.

> **Note**:

> 1. If you still cannot reset your password, repeat steps 1-6.
> 2. Select **My keyboard isn't working when typing my password to log in** and click **Next**.
> 3. Disable FileVault on the **Macintosh HD** volume.
> 4. Restart your device. On the login screen, select your user account and enter the new password.

#### **Intel chip**

1. Restart your device by pressing the power button while holding down the `Command + R` keys.
2. Release the keys when you see the load bar.
3. Go to **Applications** > **Utilities** > **Terminal**.
4. Enter `resetpassword` and press `return`. The **Reset Password** assistant will be displayed.
5. Choose **My password does not work when logging in** and click **Next**.
6. If prompted, select the user account for which you need to change the password.
7. Enter the old password and your new password in the respective fields.
8. Type the new password again to verify and provide a password hint.
9. Click **Next**.
10. Restart your device. On the login screen, select your user account and enter the new password.

> **Note**:

> 1. If you still cannot reset your password, repeat steps 1-4.
> 2. Select **My keyboard is not working when typing my password to log in** and click **Next**.
> 3. Disable FileVault on the **Macintosh HD** volume.
> 4. Restart your device and, on the login screen, select your user account and enter the new password.

<!-- tabs:end -->

</details>
