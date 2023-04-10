# Onboard macOS to SEED as public officer

<!-- This page is linked in the TechPass portal-Register Intune Device ID, so please do not rename this file. -->

> **Note**:
>Based on your device settings, while onboarding, you may be prompted to restart your device a couple of times and reset your device password.
>Keep your recovery keys ready if you face issues resetting your password or logging in to your device.

<!--<ifigure>
<iframe title="YouTubeVideoPlayer" src="https://www.youtube.com/embed/P9R5RiMpaVU?showinfo=0" height="640" width="960" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</ifigure>-->

<div style="position:relative;padding-bottom:56.25%;padding-top:30px;height:0;overflow:hidden;">
<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" src="https://www.youtube.com/embed/P9R5RiMpaVU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="true"></iframe>
</div>

> **Note**: Please complete **Step 1** and **Step 2** within the same session.

## Step 1: Set up Microsoft Intune

<details>
  <summary style="font-size:18px">Set up Microsoft Intune to get the required applications and device configurations.</summary><br>

  1. Go to [Microsoft Intune documentation](https://learn.microsoft.com/en-us/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) and follow the instructions on this page to complete the following:

   a. Download and install Company Portal.

   b. Enroll your Mac device.

  
</details>

## Step 2: Register Microsoft Intune Device ID

<details>
  <summary style="font-size:18px">Register the Microsoft Intune Device ID for your macOS device.</summary><br>

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

<img src="./images/macos-find-org-id-2.png">

3. Choose the appropriate method to register your Intune Device ID:

 - If you only have a **SE GSIB** device, submit a [support request](https://go.gov.sg/techpass-sr) to register your Intune Device ID and proceed to Sub-step 6.
 - If you have a **non-SE GSIB** device,log in to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile).
4. On the TechPass portal, at the top right, go to your user name and click **My Account**. Your **Profile** details are displayed. 
5. Click **Onboard device to SEED** and follow the on-screen instructions to submit this Intune Device ID.
6. Ensure that your device is connected to the Internet so that Intune is able to install the required SEED components and configurations. 
7. Within the next 2 hours, check your inbox (organisational email address) to see if you have received the successfully onboarded email.
8. If you don't receive this email after two hours, submit an [incident request](https://go.gov.sg/techpass-sr). 

</details>

## Step 3: Verify profiles installation

<details>
  <summary style="font-size:18px">Verify the  installation of the required profiles.</summary><br>

1. Go to the **Apple menu** > **System Settings** > **Privacy and Security**.
2. Select **Profiles** on the right pane. You should be able to see the following profiles.
<ul style="list-style-type: disc; margin-left: -3px;">
  <li style="margin-bottom:-20px">Credential Profile</span></li>
  <li style="margin-bottom:-20px">Custom Preferences Profile - com.cloudflaare.warp</span></li>
  <li style="margin-bottom:-20px">Custom Preferences Profile - com.microsoft.wdav</li>
  <li style="margin-bottom:-20px">GCC2 ATP Full Disk Access</li>
  <li style="margin-bottom:-20px">GCC2 ATP Kernel Extensions - Custom</li>
  <li style="margin-bottom:-20px">GCC2 ATP Network Filter</li>
  <li style="margin-bottom:-20px">GCC2 ATP Notifications</li>
  <li style="margin-bottom:-20px">GCC2 ATP Onboarding</li>
  <li style="margin-bottom:-20px">Intune MDM Agent SCEP Profile</li>
  <li style="margin-bottom:-20px" style="margin-bottom:-20px">Management Profile</li>
  <li style="margin-bottom:-20px">Passcode Profile</li>
  <li style="margin-bottom:-20px">Privacy Preferences Policy Profile</li>
  <li>System Extension Profile</li>
  </ul>

**Next step**: Proceed to [Post onboarding steps](post-onboarding-instructions/post-onboarding-steps-and-verification).



<!--
<img src="./images/list-of-profiles.png" width=50% height=50%>
  >**Tip**:
   >If **Profiles** page is not displayed, go to the **Apple** menu > **System Preferences** > **Profiles**.
   >If **Management Profile** is not displayed, then from the left side menu, select **Management Profile**.
   

  !> If you are a public officer, complete all the substeps in [Step 2: Register the Microsoft Intune Device ID for your macOS device](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/onboard-device/mac-os?id=step-2-register-microsoft-intune-device-id-only-for-gsib-users-onboarding-their-internet-device) to get the profiles installed. 

  If you are a vendor or a contractor, the required configuration profiles will be installed as shown below. If profile installation fails, refer to [Common onboarding issues for macOS users](faqs/common-onboarding-issues).

  <kbd>![list-of-profiles](./images/onboarding-for-macos/list-of-profiles.png)</kbd>

  9. Open the **Company Portal** application again.

  10. You will see the success message. Click **Done**.

  <kbd>![all-set](./images/onboarding-for-macos/all-set-2.png)</kbd> 

  intune device id notes: This step is applicable only if you have a GSIB device and your TechPass ID is the same as your organisation email address. In other words, this is applicable for users whose TechPass ID's domain **is not** ```techpass.gov.sg```.



- Skip the following steps if your TechPass ID belongs to the TechPass AAD and has its domain as *techpass.gov.sg*. For example, *peter_wilson<span>@</span>techpass.gov.sg*.

-->

