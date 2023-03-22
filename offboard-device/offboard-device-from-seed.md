# Offboard device from SEED

We have now automated most of the offboarding steps to simplify the process. This new offboarding method consists of the following two phases:

- Phase A: Offboard device from SEED components
- Phase B: Submit Intune Device ID

In **Phase A**, you need to do the following:

1. Identify and download the appropriate offboarding script for your Defender. 
2. Run this offboarding script on your device to:

    - unenroll your device from the SEED components such as Intune, Tanium, Defender and Cloudflare WARP. 
    - reset some of the configuration settings that were modified during SEED onboarding.

When you complete them, you are directed to Phase B.
  

In **Phase B**, you need to submit a request to remove the device record from the server side.

When we delete your device record from the server side, we notify you about your successful offboarding.

- [Offboard macOS device using a script](offboard-device/mac-os-using-script)


<!--
## Method 2: Offboard manually



- [Offboard macOS device manually](offboard-device/mac-os)
- [Offboard Windows device manually](offboard-device/windows)

-->
