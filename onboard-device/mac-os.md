# Onboard macOS to SEED as public officer

<!-- This page is linked in the TechPass portal-Register Intune Device ID, so please do not rename this file. -->

> **Note**:
>- Based on your device settings, while onboarding, you may be prompted to restart your device a couple of times and reset your device password.
>- Keep your recovery keys ready if you face issues resetting your password or logging in to your device.

<!--<ifigure>
<iframe title="YouTubeVideoPlayer" src="https://www.youtube.com/embed/P9R5RiMpaVU?showinfo=0" height="640" width="960" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</ifigure>-->

<ifigure>
<iframe style="width:100%; height:auto" src="https://www.youtube.com/embed/P9R5RiMpaVU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</ifigure>


> **Note**: Please complete **Step 1** and **Step 2** within the same session.

## Step 1: Set up Microsoft Intune

<details>
  <summary style="font-size:18px">Set up Microsoft Intune to get the required applications and device configurations.</summary><br>

  1. Download and install [**Company Portal**](https://go.microsoft.com/fwlink/?linkid=853070).

  2. Open the **Company Portal** application and click **Sign in**.

  3. Enter your organisational email address and click **Next**.

  <img src="./images/wog-login-email-address.png" width=50% height=50%>

  4. Open the authenticator app on your mobile phone and view your **SG Govt M365 profile**. A one-time password will be displayed. 
  5. Go back to your computer and enter this one-time password as the **Verification code** and click **Sign in**.

  <img src="./images/wog-login-otp.png" width=50% height=50%>

  A number will be displayed on your computer.

  <img src="./images/approve-tp-login-via-number.png" width=50% height=50%>
  
  
  6. Go back to the authenticator app and enter this number to sign in to your TechPass account. 
  7. Click **Begin**.

  <img src="./images/begin-po.png">

  8. Review privacy information and then click **Continue**.

  <img src="./images/review-privacy-info-blurred-po.png">

  9. On the **Install management profile** page, click **Download profile**.

  <img src="./images/install-management-profile-po.png">

  10. Click **Install** and follow the on-screen instructions.

  <img src="./images/profile-1-po.png">

  

</details>

## Step 2: Register Microsoft Intune Device ID

<details>
  <summary style="font-size:18px">Register the Microsoft Intune Device ID for your macOS device.</summary><br>

?> - This step is mandatory for users using a public officer onboarding flow. <br>- When you submit your Intune Device ID, the required SEED components and configurations will be installed on the device you are onboarding to SEED.

!> If you do not have **non-SE GSIB** device:<br>1. Complete substeps 1 and 2 to get your Intune Device ID.<br>2. Submit a [support request](https://go.gov.sg/techpass-sr) to register your Intune Device ID.  


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


3. On your **non-SE GSIB** device, go to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile) > **My Account** > **Profile**.
4. Click **Onboard device to SEED** and follow the on-screen instructions to submit this Intune Device ID. 

!> - Keep the device connected to the Internet so that Intune is able to install the required SEED components and configurations.<br>- If your onboarding is successful, within two hours, you should receive a successfully onboarded email to  your organisational email address.<br>- If you don't receive this email after two hours, submit an [incident request](https://go.gov.sg/techpass-sr).

</details>

## Step 3: Verify profiles installation

<details>
  <summary style="font-size:18px">Verify the  installation of the required profiles.</summary><br>

1. Go to the **Apple menu** > **System Settings** > **Privacy and Security**.
2. Select **Profiles** on the right pane. You should be able to see the following profiles.

- Credential Profile
- Custom Preferences Profile - com.cloudflaare.warp
- Custom Preferences Profile -com.microsoft.wdav
- GCC2 ATP Full Disk Access
- GCC2 ATP Kernel Extensions - Custom
- GCC2 ATP Network Filter
- GCC2 ATP Notifications
- GCC2 ATP Onboarding
- Intune MDM Agent SCEP Profile
- Management Profile
- Passcode Profile
- Privacy Preferences Policy Profile
- System Extension Profile

<img src="./images/list-of-profiles.png" width=50% height=50%>



</details>

**Next step**: Proceed to [Post onboarding steps](post-onboarding-instructions/post-onboarding-steps-and-verification).



<!--
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

