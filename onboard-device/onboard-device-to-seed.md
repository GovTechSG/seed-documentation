# Onboard your device to SEED

<!-- **IMPORTANT: This page is linked in the TechPass portal-Register Intune Device ID, so please DO NOT RENAME this file. -->

This article explains how to onboard your Internet Device to SEED.

## Audience

Users onboarding their Internet Device to SEED.

## Prerequisites

Ensure that you complete the following:
 
 - [Step 0: Prerequisites for onboarding to SEED](prerequisites-for-onboarding) 
 - [Step 1: Identify your SEED onboarding persona](identify-seed-onboarding-persona)

## Onboard device to SEED

Based on your onboarding persona and operating system of your Internet Device, choose the required onboarding flow:

**Public officers**

- [Onboard macOS device](onboard-device/mac-os)
- [Onboard Windows device](onboard-device/windows)

**Vendors**

- [Onboard macOS device](onboard-device/macos-vendor-onboarding)
- [Onboard Windows device](onboard-device/windows-vendor-onboarding)

### Next steps

- [Post onboarding steps](/post-onboarding-instructions/post-onboarding-steps-and-verification)


<!--
### Onboard as public officers

<!-- tabs:start -->

#### **macOS**

?> <br>- Based on your device settings, while onboarding, you may be prompted to restart your device a couple of times and reset your device password.<br>- Keep your recovery keys ready if you face issues resetting your password or logging in to your device.


<div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://www.youtube.com/embed/P9R5RiMpaVU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>

<details>
  <summary style="font-size:18px">Step A: Set up Microsoft Intune</summary>

  - Go to [Microsoft Intune documentation](https://learn.microsoft.com/en-us/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) and follow the instructions on this page to complete the following:

   a. Download and install Company Portal.

   b. Enroll your Mac device.

  </details>
<details>
<summary style="font-size:18px">Step B: Register Microsoft Intune Device ID</summary>

  1. Open **Terminal** and run the following commands:

```
intune_id="$(security find-certificate -a /Library/Keychains/System.keychain | egrep -B 4 '\"issu\"<blob>=.+MICROSOFT INTUNE MDM DEVICE CA' | grep alis | cut -d '"' -f 4)"
if [ -z "$intune_id" ]
then
    echo "Intune ID not found"
    return
fi

num_candidates="$(echo "$intune_id" | wc -l | xargs echo -n)"
if [ "$num_candidates" -eq 1 ]
then
    echo "$intune_id"
    return
fi

old_ifs="$IFS"
IFS='\n'
actual_id="Intune ID not found"
curr_latest_end_date_unix=0
while read id
do
    end_date="$(security find-certificate -c "$id" -p /Library/Keychains/System.keychain | openssl x509 -noout -enddate | cut -d '=' -f 2)"
    end_date_unix="$(date -j -f "%b %e %H:%M:%S %Y %Z" "$end_date" "+%s")"
    if [ "$end_date_unix" -ge "$curr_latest_end_date_unix" ]
    then
        actual_id="$id"
        curr_latest_end_date_unix="$end_date_unix"
    fi
done <<< "$intune_id"

IFS="$old_ifs"
echo "$actual_id"
```
2. Take note of the Intune Device ID that is displayed on the Terminal window.

<img src="./images/macos-get-intune-device-id-new.png">

3. Choose the appropriate method to register your Intune Device ID:

 - If you only have a **SE GSIB** device, submit a [support request](https://go.gov.sg/techpass-sr) to register your Intune Device ID and proceed to Sub-step 6.
 - If you have a **non-SE GSIB** device,log in to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile).
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

<img src="./images/device-listed-tp-portal.png">

6. Ensure that your Internet Device is connected to the Internet so that Intune is able to install the required software and configurations.

7. Refer to the following table to know about the possible onboarding status and the action required by you.

| Status | Description | Action required |
|---| ---| ---|
| **triggered, waiting for software installation (step 1 of 2)**| Your SEED onboarding has been triggered on the device and is waiting for the software installation to be completed. When the software installation is completed, it approximately takes 30-60 minutes to update the status. | Click the refresh button to update the onboarding status until you see the **onboarded** status.|
| **software installed, waiting for backend onboarding (step 2 of 2)**| Required software has been installed on the device. It approximately takes 30-60 minutes to update this status.  | You may click the refresh button to update the onboarding status until you see the **onboarded** status. |
| **onboarded** | Your SEED onboarding is successful. | 1. check your inbox (organisational email address) to see if you have received the successfully onboarded email.<br> 2. If you don't receive this email after two hours, submit an [incident request](https://go.gov.sg/techpass-sr).  |
| **failed(Software installation error occurred while onboarding. Please restart your device and retry the process. Raise a support ticket if the problem persists.)** | Your SEED onboarding failed due to errors in software installation. | 1. Restart the device you are onboarding to SEED and then click **Retry**. on your TechPass portal.<br>2. If the problem persists, click **Support** to raise a support request. | 
| **failed(unexpected error occurred while onboarding. Please raise a support ticket)** | Your SEED onboarding failed due to some unexpected error .  | Click **Support** to raise a support request.|
 


  </details>

  <details>
  <summary style="font-size:18px">Step C. Verify installation</summary>

  1. Go to the **Apple menu** > **System Settings** > **Privacy and Security**.
2. Select **Profiles** on the right pane. You should be able to see the following profiles.
<ul style="list-style-type: disc; margin-left: -3px;">
  <li style="margin-bottom:-20px">Credential Profile</li>
  <li style="margin-bottom:-20px">Custom Preferences Profile - com.cloudflare.warp</li>
  <li style="margin-bottom:-20px">Custom Preferences Profile - com.microsoft.wdav</li>
  <li style="margin-bottom:-20px">GCC2 ATP Full Disk Access</li>
  <li style="margin-bottom:-20px">GCC2 ATP Kernel Extensions - Custom</li>
  <li style="margin-bottom:-20px">GCC2 ATP Network Filter</li>
  <li style="margin-bottom:-20px">GCC2 ATP Notifications</li>
  <li style="margin-bottom:-20px">GCC2 ATP Onboarding</li>
  <li style="margin-bottom:-20px">Intune MDM Agent SCEP Profile</li>
  <li style="margin-bottom:-20px">Management Profile</li>
  <li style="margin-bottom:-20px">Passcode Profile</li>
  <li style="margin-bottom:-20px">Privacy Preferences Policy Profile</li>
  <li>System Extension Profile</li>
  </ul>


  </details>

  #### **Windows**

<details>
  <summary style="font-size:18px">a. step 1</summary>

  </details>
<details>
  <summary style="font-size:18px">b. Step 2</summary>

  </details>

  
<details>
  <summary style="font-size:18px">b. Step 3</summary>

  </details>

<!-- tabs:end -->  

### To onboard as vendors

<!-- tabs:start -->

#### **macOS**

<details>
  <summary style="font-size:18px">a. step 1</summary>

  </details>
<details>
  <summary style="font-size:18px">b. Step 2</summary>

  </details>

  

  #### **Windows**

<details>
  <summary style="font-size:18px">a. step 1</summary>

  </details>
<details>
  <summary style="font-size:18px">b. Step 2</summary>

  </details>
<!-- tabs:end --> 



  





