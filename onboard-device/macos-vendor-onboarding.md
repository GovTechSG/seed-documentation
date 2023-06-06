# Onboard macOS device to SEED as vendors

<!-- This page is linked in the TechPass portal-Register Intune Device ID, so please do not rename this file. -->

?> <br>- Based on your device settings, while onboarding, you may be prompted to restart your device a couple of times and reset your device password.<br>- Keep your recovery keys ready if you face issues resetting your password or logging in to your device.



<div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://www.youtube.com/embed/P9R5RiMpaVU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>

## Step 1: Set up Microsoft Intune

<details>
  <summary style="font-size:18px">Set up Microsoft Intune to get the required applications and device configurations.</summary><br>

  1. Go to [Microsoft Intune documentation](https://learn.microsoft.com/en-us/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) and follow the instructions on this page to complete the following:

   a. Download and install Company Portal.

   b. Enroll your Mac device. 

   
  2. Ensure that your device is connected to the Internet so that Intune is able to install the required SEED components and configurations. 
  3. Within the next two hours, check your inbox (organisational email address) to see if you have received the successfully onboarded email.
  4. If you don't receive this email after two hours, submit an [incident request](https://go.gov.sg/seed-techpass-support). 

</details>

## Step 2: Verify installation

<details>
  <summary style="font-size:18px">Verify the  installation of the required profiles.</summary><br>

1. Go to the **Apple menu** > **System Settings** > **Privacy and Security**.
2. Select **Profiles** on the right pane. You should be able to see the following profiles.

 <ul style="list-style-type: disc; margin-left: -3px;">
  <li>Credential Profile</span></li>
  <li>Custom Preferences Profile - com.cloudflaare.warp</span></li>
  <li>Custom Preferences Profile - com.microsoft.wdav</li>
  <li>GCC2 ATP Full Disk Access</li>
  <li>GCC2 ATP Kernel Extensions - Custom</li>
  <li>GCC2 ATP Network Filter</li>
  <li>GCC2 ATP Notifications</li>
  <li>GCC2 ATP Onboarding</li>
  <li>Intune MDM Agent SCEP Profile</li>
  <li>Management Profile</li>
  <li>Passcode Profile</li>
  <li>Privacy Preferences Policy Profile</li>
  <li>System Extension Profile</li>
  </ul>

  ?> You may receive a desktop notification that your device has been renamed according to convention, and that a timed restart will occur in 5 minutes. This is completely expected, and you should save any existing work to prevent data loss. Alternatively, you can also opt to manually restart your device, after receiving the desktop notification, to speed up the process. As the naming convention is required for administrative purposes, please refrain from renaming your device thereafter.

</details>





<!--

<ifigure>
<iframe title="YouTubeVideoPlayer" src="https://www.youtube.com/embed/P9R5RiMpaVU?showinfo=0" height="640" width="960" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</ifigure>

 







?> Sign in to the Company Portal using your TechPass and authenticate it by entering the number displayed on your computer.

<img src="./images/list-of-profiles.png" width=50% height=50%>
  >**Tip**:
   >- If **Profiles** page is not displayed, go to the **Apple** menu > **System Preferences** > **Profiles**.
   >- If **Management Profile** is not displayed, then from the left side menu, select **Management Profile**.
   

  !> If you are a public officer, complete all the substeps in [Step 2: Register the Microsoft Intune Device ID for your macOS device](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/mac-os?id=step-2-register-microsoft-intune-device-id-only-for-gsib-users-onboarding-their-internet-device) to get the profiles installed. 

  If you are a vendor or a contractor, the required configuration profiles will be installed as shown below. If profile installation fails, refer to [Common onboarding issues for macOS users](faqs/common-onboarding-issues).

  <kbd>![list-of-profiles](./images/onboarding-for-macos/list-of-profiles.png)</kbd>

  9. Open the **Company Portal** application again.

  10. You will see the success message. Click **Done**.

  <kbd>![all-set](./images/onboarding-for-macos/all-set-2.png)</kbd> 

  intune device id notes: This step is applicable only if you have a GSIB device and your TechPass ID is the same as your organisation email address. In other words, this is applicable for users whose TechPass ID's domain **is not** ```techpass.gov.sg```.



- Skip the following steps if your TechPass ID belongs to the TechPass AAD and has its domain as *techpass.gov.sg*. For example, *peter_wilson<span>@</span>techpass.gov.sg*.

-->

