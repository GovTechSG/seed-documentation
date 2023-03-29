# SEED offboarding FAQs

<details><summary style="font-size:20px;font-weight:bold">I cannot download the offboarding package. What should I do?</summary>

  Create an [incident request](https://go.gov.sg/techpass-sr) and request for request for the offboarding package for your Defender organisation.
  
</details><hr />

<details><summary style="font-size:20px;font-weight:bold">
I cannot log in to my device. What should I do? </summary>

1. Create an [incident support](https://go.gov.sg/techpass-sr) request.
2. In **Details**, enter the text  *I am unable to offboard my device from SEED components but I would like to submit my Intune Device ID to offboard my device from SEED*. 
3. Select SEED as **TechPass Tenant**.
4. Select Production as **Environment**
5. Make sure to provide all the required details and submit the form.

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">While running the offboarding package,I get the following error:<code>Unknown Tenant detected</code>.</summary>

This indicates that you are not a SEED user or your device was not properly enrolled to SEED.

If you had properly onboarded your device to SEED earlier but still get this error message, please submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support.


</details><hr />
<details><summary style="font-size:20px;font-weight:bold">While running the offboarding package on my device, I get the following error:<code>Defender offboarding package has expired! Please download a new offboarding package from the docs portal</code></summary>

This error indicates that your offboarding package is outdated. 

1. On the [Offboard device](offboard-device/offboard-device-from-seed) section, follow the offboarding steps for your device operating system .
2. Make sure to download the offboarding package from this page and complete the offboarding steps.

 !> **Note**<br>If you still experience the same or any other error, submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support.
 

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">when I run the offboarding package on my device, I get the following error: <code>Microsoft Defender for Endpoint Service failed to stop running</code>!</summary>

This error would look like the following:

![offboarding-error-for-defender-windows](/images/offboarding-error-for-defender-windows.png)

Try running the script again. If you still experience the same or any other error, submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support.

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">I get an error on my macOS device while running the offboarding package to remove the SEED components such as Cloudflare WARP, Microsoft Defender or Tanium Client.</summary>

Try running the script again. If you still experience any error, submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support.

</details><hr />

<details><summary style="font-size:20px;font-weight:bold">After I successfully complete Phase A to offboard my device from SEED components, I get the error message<code>Intune ID not found. Please manually input your Intune ID</code>.</summary>

You may experience this error if we are unable to auto-retrieve your Intune Device ID due to some incorrect configurations on your device. There can be multiple reasons for this incorrect configurations. 

1. If you encounter this error, complete one of the following methods to get your Intune Device ID:

    - Go to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile) and get the Intune Device ID from your account profile.
    - If you can't access the TechPass portal, please submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support to get your Intune Device ID.

2. When you have your Intune device ID proceed with **Phase B: Submit Intune Device ID** to remove device record.

!> **Important**<br> If there is a significant time lapse between Phase B and Phase A, the latest version of the SEED components may be reinstalled on your device. If that is the case, you need to repeat **Phase A: Offboard device from SEED components**. 


</details><hr />

<details><summary style="font-size:20px;font-weight:bold">After submitting the Intune Device ID, I received an email stating that my offboarding was unsuccessful. What should I do?</summary>

This can happen if you had submitted an incorrect Intune Device ID. 

1. Complete one of the following steps to get your Intune Device ID:

    - Go to the [TechPass portal](https://portal.techpass.gov.sg/secure/account/profile) and get the Intune Device ID from your account profile.
    - If you can't access the TechPass portal, please submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support to get your Intune Device ID.

2. Complete the [offboarding steps](offboard-device/offboard-device-from-seed) for your device.


!> **Note**<br>-  In spite of submitting a correct Intune Device ID, if your offboarding is unsuccessful, please submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support.<br><br>- If the TechPass support team completes the offboarding for you, you may not receive this successfully offboarded email from the DEEP team. However, the TechPass support team can confirm if you have successfully offboarded your device from SEED.

</details><hr />


<details><summary style="font-size:20px;font-weight:bold">After submitting my Intune Device ID, I did not receive the successfully offboarded email. What should I do?</summary>

It would take up to 30 minutes for the DEEP team to send the successfully offboarded email to you. If you still have not received this email, please submit an [incident request](https://go.gov.sg/techpass-sr) with the TechPass support.

!> **Note**<br> If the TechPass support team has completed the offboarding for you, you may not receive this email from the DEEP team. However, the TechPass support team can confirm if you have successfully offboarded your device from SEED.

</details><hr />





