# Offboard device from SEED

We have now automated most of the offboarding steps to simply the process. This new offboarding method consists of two steps. 

In the first step, you identify your Defender organisation to download the appropriate script. When you run the script, it unenrolls your device from the SEED components such as Intune, Tanium, Defender and WARP, and resets some of the configuration settings that were modified during SEED onboarding. When you successfully complete this, you are directed to the second step. 

In the second step, you need to submit the Intune Devcie ID. We delete your device record from the server-side and notify you about a successful offboarding.

?>**Note**<br> By default, the Intune Device ID is auto-retrieved for you. If it is not displayed on this form, follow the guidelines on the form to get your Intune Device ID.

- [Offboard macOS device using a script](offboard-device/mac-os-using-script)


<!--
## Method 2: Offboard manually



- [Offboard macOS device manually](offboard-device/mac-os)
- [Offboard Windows device manually](offboard-device/windows)

-->
