# Onboard to SEED as a vendor

This document provides a step-by-step guide to help vendors through the onboarding process for the Secure Engineering Environment for Developers (SEED). Before proceeding, make sure you meet the prerequisites outlined below.

## Prerequisites

Before proceeding with the onboarding process, vendors must meet the following prerequisites to ensure a seamless experience:

- Your TechPass login ID must end with **techpass.gov.sg**. For example, john_doe@techpass.gov.sg.


## macOS

During the process, you may encounter prompts to restart your device and reset your device's password. It is important to have your recovery keys ready in case you encounter any issues during the password reset or device login.


<div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://www.youtube.com/embed/ytu6oOP6TYA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>

### Step 1: Set up Microsoft Intune

<details>
  <summary style="font-size:18px">Set up Microsoft Intune to get the required applications and device configurations.</summary><br>

  1. Go to [Microsoft Intune documentation](https://learn.microsoft.com/en-us/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) and follow the instructions on this page to complete the following:

   a. Download and install Company Portal.

   b. Enroll your Mac device. 

   
  2. Ensure that your device is connected to the Internet so that Intune is able to install the required SEED components and configurations. 
  3. Within the next two hours, check your inbox (organisational email address) to see if you have received the successfully onboarded email.
  4. If you do not receive this email after two hours, [raise a service request](https://go.gov.sg/seed-techpass-support). 

</details>

### Step 2: Verify installation

<details>
  <summary style="font-size:18px">Verify the installation of the required profiles.</summary><br>

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


## Windows

Based on your Windows settings, you may be prompted to restart or reset your password while onboarding.

<div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://www.youtube.com/embed/PAyKoRZ7WSk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>

### Step 1: Set up Microsoft Intune

<details>
  <summary style="font-size:18px">Set up Microsoft Intune to get the required applications and device configurations.</summary><br>

1. Click **Start** icon on the taskbar.

2. Go to **Settings** > **Accounts** > **Access work or school** and click **Connect** to add your TechPass account.

  ![access-work-or-school](../images/onboarding-instructions-for-windows/access-work-or-school.png)

3. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. 

  ![techpass-sign-in](../images/onboarding-instructions-for-windows/techpass-sign-in.png)

  Your account is added and listed as a connection. This account has **Info** and **Disconnect** options as shown below. 

  ![info-disconnect](../images/onboarding-instructions-for-windows/info-disconnect.png)

4. Select the **Info** option and verify that a similar result to the following is displayed. You will see **TechPass** instead of **SG Govt M365**.

  ![managed-by-tp](../images/onboarding-instructions-for-windows/managed-by-tp.png)

</details>



### Step 2: Verify installation

<details>
  <summary style="font-size:18px">Verify the installation.</summary><br>

1. Go to the Internet Device onboarded to SEED, open **Settings** > **Apps** > **Apps & features**. 
2. Ensure that Cloudflare WARP and Tanium are listed.

  ![cloudflare](../images/onboarding-instructions-for-windows/cloudflare.png)

  ![tanium](../images/onboarding-instructions-for-windows/tanium.png)
  
  ?> You will receive a desktop notification that your device will be renamed according to our standard convention, followed by an automatic restart in 5 minutes. Please save your work to avoid data loss. You can also manually restart your device after the notification for a quicker update. Keep in mind that this naming convention is necessary for administrative purposes, so avoid renaming your device afterward.

</details>






