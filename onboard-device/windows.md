# Windows

<!-- This page is linked in the TechPass portal-Register Intune Device ID, so please do not rename this file. -->

> **Note:** Based on your Windows settings, you may be prompted to restart or reset your password while onboarding.


<ifigure>
<iframe title="YouTubeVideoPlayer" src="https://www.youtube.com/embed/Cvb7lppxFqs" height="580" width="1000" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</ifigure>

> **Note**: Please complete all the steps within the same session.

## Step 1: Enrol your device in Microsoft Intune
<details>
  <summary style="font-size:18px">Enrol your device in Microsoft Intune</summary><br>

1. Click **Start** icon on the taskbar.

2. Go to **Settings** > **Accounts** > **Access work or school** and click **Connect** plus sign to add your work or school account.

<kbd>![access-work-or-school](../images/onboarding-instructions-for-windows/access-work-or-school.png ':size=600')</kbd>

3. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. If you are a public officer onboarding your device to SEED, authorise your WOG account by entering the verification code displayed for your SG Govt M365 profile on the authenticator app before approving your Techpass login.

<kbd>![log-in-to-gcc](../images/onboarding-for-macos/log-in-to-gcc.png ':size=500')</kbd>

?> The above page is displayed only for public officers and you may refer to [TechPass documentation](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/) for more information.

<kbd>![settings](../images/onboarding-instructions-for-windows/settings.png ':size=600')</kbd>

Your account is added and listed as a connection. This account has the **Info** and **Disconnect** options as shown below. 

4. Click on the **Info** option and verify that you see something like the following.

?> Vendors will see **TechPass** instead of **SG Govt M365**.

<kbd>![managed-by-sg-govt-m365](../images/onboarding-instructions-for-windows/managed-by-sg-govt-m365.png ':size=600')</kbd>

>**Notes**:
>- Your device is now enrolled in Microsoft Intune.
>
>- If you are a vendor or contractor, Tanium and Cloudflare WARP are installed on your device. When the installation is complete, Microsoft Intune Management Extension sends you a desktop notification.


!> If you are a public officer, Tanium and Cloudflare WARP will be installed only after you complete [step 2. Register Microsoft Intune device ID for your Windows device](#step-2-register-microsoft-intune-device-id-only-for-gsib-users-onboarding-their-internet-device).


</details>

## Step 2: Register Microsoft Intune device ID (only for GSIB users onboarding their internet device)

<details><summary style="font-size:18px">Register the Microsoft Intune device ID for your Windows device</summary>

> **Note**:  
>
>- This step is applicable only if you have a GSIB device and your TechPass ID is the same as your organisation email address. In other words, this is applicable for users whose TechPass ID's domain **is not** ```techpass.gov.sg```.
>
>- If you only have a SE-GSIB device, complete substeps 1 and 2, and then contact the [support team](https://go.gov.sg/techpass-sr) with your Intune device ID to register your Intune device ID.  

<!--

- Skip the following steps if your TechPass ID belongs to the TechPass AAD and has its domain as *techpass.gov.sg*. For example, *peter_wilson<span>@</span>techpass.gov.sg*.-->

1. Open **PowerShell** and run the following commands:
```
$rootKey = [Microsoft.Win32.RegistryKey]::OpenBaseKey(
    [Microsoft.Win32.RegistryHive]::LocalMachine,
    [Microsoft.Win32.RegistryView]::Registry64
)
$enrollmentsKey = $rootKey.OpenSubKey("Software\Microsoft\Enrollments")
$intune_id = "Intune ID not found"
foreach ($name in $enrollmentsKey.GetSubKeyNames()) {
    $enrollmentIdKey = $enrollmentsKey.OpenSubKey($name)
    if ($enrollmentIdKey.GetValue("ProviderID") -ieq "MS DM Server") {
        $intune_id = $enrollmentIdKey.OpenSubKey("DMClient\MS DM Server").GetValue("EntDMID", "Intune ID not found")
        break
    }
}
Write-Output $intune_id
```
2. Take note of the Intune device ID that will be displayed on the Powershell window.
3. On your **non-SE GSIB** device, go to [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile) > **My Account** > **Profile**.
4. Click **Onboard device to SEED** and follow the on-screen instructions to submit this Intune device ID.  Intune installs the required software and configurations to complete your device onboarding.

  If your onboarding is successful, within an hour, you will receive a successfully onboarded email to your organisational email address.

5. Shortly after this email, when you receive a desktop notification informing about the device name change and about the device being restarted, do the following:

    i. Save your current work and restart your device.

    ii. If prompted to specify your password, enter it.

5. To verify if the required profiles are installed correctly, go to the internet device onboarded to SEED, open **Settings** > **Apps** > **Apps & features** and ensure that Tanium and Cloudflare WARP are listed.

</details>

**Next step**: Proceed to [Post onboarding steps](post-onboarding-instructions/post-onboarding-steps-and-verification).
