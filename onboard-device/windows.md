# Onboard Windows device to SEED as public officers

?> <br>- Based on your Windows settings, you may be prompted to restart or reset your password while onboarding.

<!--
<ifigure>
<iframe title="YouTubeVideoPlayer" src="https://www.youtube.com/embed/Cvb7lppxFqs" height="580" width="1000" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</ifigure>
-->

<div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://www.youtube.com/embed/Cvb7lppxFqs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>


## Step 1: Set up Microsoft Intune 

<details>
  <summary style="font-size:18px"> Set up Microsoft Intune to get the required applications and device configurations.</summary><br>

1. Click **Start** icon on the taskbar.

2. Go to **Settings** > **Accounts** > **Access work or school** and click **Connect** to add your WOG account.

![access-work-or-school](../images/onboarding-instructions-for-windows/access-work-or-school.png)

3. Authorise your WOG account by entering the verification code displayed for your SG Govt M365 profile on the authenticator app before approving your TechPass login.

![log-in-to-gcc](../images/onboarding-for-macos/log-in-to-gcc.png)

Your account is added and listed as a connection. This account has **Info** and **Disconnect** options as shown below. 

![info-disconnect](../images/onboarding-instructions-for-windows/info-disconnect.png)

4. Select the **Info** option and verify that a similar result to the following is displayed.

![managed-by-sg-govt-m365](../images/onboarding-instructions-for-windows/managed-by-sg-govt-m365.png)


</details>

## Step 2: Register Microsoft Intune Device ID

<details>
  <summary style="font-size:18px">Register the Microsoft Intune Device ID for your Windows device.</summary>

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
2. Take note of the Intune Device ID that is displayed on the Powershell window.

3. Choose the appropriate method to register your Intune Device ID:

  3a. If you only have a **SE GSIB** device, submit a [support request](https://go.gov.sg/techpass-sr) to register your Intune Device ID and proceed to step 8 in this section.

  3b. If you have a **non-SE GSIB** device,log in to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile).

4. On the TechPass portal, at the top right, go to your user name and click **My Account**. Your **Profile** details are displayed. 
5. Click **Onboard device to SEED** and follow the on-screen instructions to submit this Intune Device ID.

  <img src="./images/enter-intune-device-id.png">

  You will receive the following confirmation message.

  <img src="./images/ack-of-intune-device-id.png">

  Your Internet Device record is listed under the **SEED Devices** with the following details:

    - Device name
    - Operating system of the device
    - Serial number
    - Intune Device ID
    - Date and time when the onboarding was trigerred or when the device was successfully onboarded
    - Onboarding status

  ![windows-device-listed-tp-portal](../images/windows-device-listed-tp-portal.png)

6. Ensure the device you are onboarding is connected to the Internet so that Intune is able to install the required software and configurations.

7. Refer to the following table to know about the possible onboarding status and the action required by you.


| Status | Description | Action required |
|---| ---| ---|
| **triggered, waiting for software installation (step 1 of 2)**| Your SEED onboarding has been triggered on the device and is waiting for the software installation to be completed. When the software installation is completed, it approximately takes 30-60 minutes to update the status. | Click the refresh button to update the onboarding status until you see the **onboarded** status.|
| **software installed, waiting for backend onboarding (step 2 of 2)**| Required software has been installed on the device. It approximately takes 30-60 minutes to update this status.  | You may click the refresh button to update the onboarding status until you see the **onboarded** status. |
| **onboarded** | Your SEED onboarding is successful. | Go to step 8 in this section.  |
| **failed(Software installation error occurred while onboarding. Please restart your device and retry the process. Raise a support ticket if the problem persists.)** | Your SEED onboarding failed due to errors in software installation. | 1. Restart the device you are onboarding to SEED and then click **Retry**. on your TechPass portal.<br>
2. If the problem persists, click **Support** to raise a support request. | 
| **failed(unexpected error occurred while onboarding. Please raise a support ticket)** | Your SEED onboarding failed due to some unexpected error .  | Click **Support** to raise a support request.|

8. Check your inbox (organisational email address) to see if you have received the successfully onboarded email.

?> If you don't receive this email after two hours, submit an [incident request](https://go.gov.sg/techpass-sr).


</details>

## Step 3: Verify installation

<details>
  <summary style="font-size:18px">Verify the installation.</summary><br>

1. Go to the Internet Device onboarded to SEED, open **Settings** > **Apps** > **Apps & features**. 
2. Ensure that Cloudflare WARP and Tanium are listed.

![cloudflare](../images/onboarding-instructions-for-windows/cloudflare.png)

![tanium](../images/onboarding-instructions-for-windows/tanium.png)

</details>

### Next steps

- [Post onboarding steps](post-onboarding-instructions/post-onboarding-steps-and-verification).
