# SEED onboarding guide for Windows users

This sections explains public officers and vendors how to onboard to SEED using their Windows device.


?>  Based on your Windows settings, you may be prompted to restart or reset your password while onboarding.

During this onboarding journey you will do the following:


<details>
  <summary>a. Set Up Intune</summary><br>

1. Click **Start** icon on the taskbar.

2. Go to **Settings** > **Accounts** > **Access work or school** and click **Connect** plus sign to add your work or school account.

<kbd>![access-work-or-school](images/onboarding-instructions-for-windows/access-work-or-school.png ':size=600')</kbd>

3. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. However, if you are a public officer using your GMD device, you must first sign in to your WOG account before approving your Techpass login.
<!-- the appropriate login credentials to sign in with two-factor authentication:
   - If you are a public officer, use your [WOG ID](terms-definitions).
   - If you are a vendor, use your [TechPass ID](terms-definitions). -->

<kbd>![log-in-to-gcc](images/onboarding-for-macos/log-in-to-gcc.png ':size=500')</kbd>

?> The above page will be displayed only for public officers.

GCC2 Tanium and Cloudflare WARP clients will be installed on your device. Microsoft Intune Management Extension sends you a desktop notification about once the installation is complete.
<!--3. Within a few minutes, you should receive some desktop notifications from **Microsoft Intune Management Extension** telling you that certain software has been installed onto your device.-->

<kbd>![settings](images/onboarding-instructions-for-windows/settings.png ':size=600')</kbd>

5. <!--After around 5 minutes, check the **Access work or school** page again.--> Your account will be added and listed as a connection. This account has the <b>Info</b> and <b>Disconnect</b> options as shown below. Click on the <b>Info</b> option and verify that you see something like the following.

?> Vendors will see **TechPass** instead of **SG Govt M365**.

<kbd>![managed-by-sg-govt-m365](images/onboarding-instructions-for-windows/managed-by-sg-govt-m365.png ':size=600')</kbd>

Now your device is enrolled on Microsoft Intune.
</details>

<details>
  <summary>b. Encrypt drive using BitLocker</summary><br>

1. Click the **Start** icon on the taskbar and search for **Manage BitLocker** and choose to open it. Check if BitLocker is turned on for your OSDisk. A padlock on the drive indicates that BitLocker is turned on ![](images/onboarding-instructions-for-windows/bitlocker-enabled.png). If yes, proceed to **Enrol on Cloudflare using WARP client**.
2. If BitLocker is not turned on, select **Turn on BitLocker**.
3. When asked to choose how to unlock your drive at start up, select **Enter a password**.

<kbd>![enter-pwd](images/onboarding-instructions-for-windows/enter-pwd.png ':size=600')</kbd>

4. To backup the recovery key for your computer, insert a thumb drive or any other form of removable storage device into the USB port of your computer.
5. When asked how you would like to back up your recovery key, select **Save to a file**, save the file in the inserted removable storage device and click **Next**.

!> Remove the external storage device and transfer this file to a safe location other than your computer.

<kbd>![save-to-file](images/onboarding-instructions-for-windows/save-to-file.png ':size=600')</kbd>

5. When asked how much of your drive to be encrypted, select **Encrypt entire drive(slower but best for PCs and drives already in use)** and click **Next**.

<kbd>![encrypt-entire-drive](images/onboarding-instructions-for-windows/encrypt-entire-drive.png ':size=600')</kbd>

6. When asked which encryption mode to use, select **New encryption mode(best for fixed drives on this device)** and click **Next**.

<kbd>![new-encryption-mode](images/onboarding-instructions-for-windows/new-encryption-mode.png ':size=600')</kbd>

7. The device encryption page is displayed. <!--Click **Start encrypting**.-->

?> Depending on your system settings, you may be prompted to restart your computer before the encryption can start. If you are prompted to do so, restart your device, then return to the **Manage BitLocker** window to verify if encryption has started. A padlock icon on the hard drives in your Windows 10 File Explorer indicates that the hard drive has been encrypted.

</details>
<details id="d3">
  <summary>c. Enrol on Cloudflare using WARP client</summary><br>

1. Click the **Show hidden icons** arrow next to the notification area and make sure that Cloudflare WARP icon is displayed on your device or go to the **Start** menu and search for **Cloudflare WARP**.

<kbd>![](images/cloudflare-warp-windows/check-cloudflare-warp-desktop-client.png ':size=400')</kbd>

<!--<kbd>![cloudflare-systemtray-icon](images/cloudflare-warp-windows/cloudflare-systemtray-icon.png)</kbd>-->

?> If it is not available on your device, install it from [Cloudflare App Center](https://install.appcenter.ms/orgs/cloudflare/apps/1.1.1.1-windows-1/distribution_groups/release).

2. Disconnect from any other VPN that might be running as that could clash with Cloudflare.

3. Run the Cloudflare WARP client. You will see an information page, followed by a privacy policy.

4. Click **Next** and accept the policy.

<kbd>![cloudflare-for-teams](images/cloudflare-warp-windows/cloudflare-for-teams.png ':size=400')</kbd>

<!--You will be prompted to sign in with one of the three options.-->

3. When prompted to sign in, choose **Azure AD – TechPass Prod**.

![azure-ad-techpass-prod](images/cloudflare-warp-windows/azure-ad-techpass-prod.png ':size=400')

5. Sign on using your TechPass credentials.

6. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. However, if you are a public officer, you must first approve your WOG login before approving your Techpass login.

<kbd>![techpass-sigin](images/cloudflare-warp-windows/techpass-sigin.png ':size=400')</kbd>

6. Once you have successfully signed in, click the Cloudflare WARP icon. You should see the following page.

<kbd>![after-signed-in](images/cloudflare-warp-windows/after-signed-in.png ':size=400')</kbd>


?> The WARP client connects your device to the Cloudflare network, which functions like a VPN. If you want to connect to a different VPN, first disconnect from WARP and exit it before doing so. If you do not exit the WARP client, it will attempt to automatically reconnect every hour and this may affect your existing VPN connection.

</details>


If your onboarding is successful, within an hour, you will receive a successfully onboarded email to your organisational email address.

?> If you do not receive this email, please contact the [SEED team](mailto:gcc2.0_support@tech.gov.sg).

Shortly after this email, when you receive a desktop notification prompting to restart the device, do the following:

1. Restart your device.
2. If prompted to enter your password, enter it.

?>  While restarting, you will be notified that your device is renamed and will be prompted to reset your password.

3. Reset your password.
