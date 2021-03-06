# Onboard macOS to SEED

> **Note:**
>- Based on your device settings, while onboarding, you may be prompted to restart your device a couple of times and reset device password.
>- For a smooth onboarding journey, make sure to link your Apple ID to your device.
>- Keep your recovery keys ready if you face issues in resetting your password or logging in to your device.



<ifigure>
<iframe title="YouTubeVideoPlayer" src="https://www.youtube.com/embed/P9R5RiMpaVU?showinfo=0" height="315" width="560" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</ifigure>


## Step 1: Set up Microsoft Intune

 **Set up Microsoft Intune to get the required applications and device configuration**


  1. Download and install [**Company Portal**](https://go.microsoft.com/fwlink/?linkid=853070).

  2. Open the **Company Portal** application and click **Sign in** to log in using your TechPass credentials.

  <kbd>![sign-in](../images/onboarding-for-macos/sign-in.png)</kbd>

  3. Approve your TechPass login using the authenticator app that was used to set up TechPass MFA. However, if you are a public officer, approve your WOG login first by entering the verification code displayed for your SG Govt M365 profile on the authenticator app before approving your Techpass login.

  <kbd>![log-in-to-gcc](../images/onboarding-for-macos/log-in-to-gcc.png)</kbd>

  ?> The above page is displayed only for public officers. Refer to [TechPass documentation](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/) for more information.

  4. Once you have signed in, click **Begin**.

  <kbd>![](../images/onboarding-for-macos/begin.png)</kbd>

  5. Review privacy information. Then click **Continue**.

  <kbd>![review-privacy-info](../images/onboarding-for-macos/review-privacy-info-blurred.png)</kbd>

  6. When prompted to authenticate your WOG account, enter the verification code displayed for your SG Govt M365 profile on the authenticator app.

  <kbd>![enter-verification-code-for-wog](../images/onboarding-for-macos/second-prompt-for-ver-code.png)</kbd>

  7. On the **Install management profile** page, click **Download profile**.

  <kbd>![install-management-profile](../images/onboarding-for-macos/install-management-profile.png)</kbd>

  8. Follow the on-screen instructions to allow Microsoft Intune to manage your device. The **Profiles** page is displayed.

  <kbd>![profile-1](../images/onboarding-for-macos/profile-1.png)</kbd>

  >**Tip**:
   >- If **Profiles** page is not displayed, go to the **Apple** menu > **System Preferences** > **Profiles**.
   >- If **Management Profile** is not displayed, then from the left side menu, select **Management Profile**.

  9. Click **Install** to get the required configuration profiles.

  - If you are a public officer, the profiles will be installed only after you register the Microsoft Intune device ID on the TechPass portal. Intune device ID will be generated only when you complete the device enrolment in Intune. After you complete all the steps in **step a**, follow the instructions listed under **step b. Register the Microsoft Intune device ID for your macOS device**.

  <kbd>![profile](../images/onboarding-for-macos/profile-2.png)</kbd>

  If you are a vendor or a contractor, the required configuration profiles will be installed as shown below. If profile installation fails, refer to [Common onboarding issues for macOS users](faqs/common-issues-while-onboarding).

  <kbd>![list-of-profiles](../images/onboarding-for-macos/list-of-profiles.png)</kbd>

  9. Open the **Company Portal** application again.

  10. You will see the success message. Click **Done**.

  <kbd>![all-set](../images/onboarding-for-macos/all-set-2.png)</kbd>



## Step 2: Register Microsoft Intune device ID

This step is applicable only for public officers to get the required applications and device configurations on their device.

?> If you are a public officer; your TechPass ID will be your official email address such as *your_name<span>@</span>agency.gov.sg* or *your_name<span>@</span>tech.gov.sg*. Ignore this step if your TechPass ID format is *your_name<span>@</span>techpass.gov.sg*.

**To get the Intune device ID**:

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
2. Take note of the Intune device ID that will be displayed on the Terminal window.
3. Using your GSIB device, go to your profile page on the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile).
4. Click **Onboard device to SEED** and follow the on-screen instructions to submit this Intune device ID. Intune installs the required softwares and configurations to complete your device onboarding.

If your onboarding is successful, within an hour, you will receive a successfully onboarded email to  your organisational email address.

5. To verify if the required profiles are installed correctly, go to **System Preferences** > **Profiles**. You should be able to see the profiles listed as shown here.

<kbd>![list-of-profiles](../images/onboarding-for-macos/list-of-profiles.png)</kbd>


>**Notes:**
>- If you do not receive the successfully onboarded to SEED email, [check if Microsoft Defender is configured correctly](verify-microsoft-defender-is-configured-correctly-for-your-os) and also check if Tanium and Cloudflare are installed. If Tanium or Cloudflare is not installed, [create a support request](raise-an-incident-support-request).
>- Shortly after this email, you will receive a desktop notification informing you that your device has been renamed and will automatically restart in the next five minutes. When you log in again, you will be prompted to reset your password. This is to enforce a strong password policy.
>- If you had reset your password while onboarding, you will not be prompted to reset password when your device automatically restarts.
>- Refer to [Best practices](additional-resources/best-practices) to know about the supported browsers.
