# Offboard device from SEED

We have now automated most of the offboarding steps to simplify the process. This new offboarding method consists of the following two phases:

- **Phase A: Offboard device from SEED components**
- **Phase B: Submit Intune Device ID to remove device record to remove device record**

!>**Important note**<br> Make sure you complete **Phase B** immediately after **Phase A**. If not, your device update policy may reinstall the latest version of the deleted SEED components. 

To know the steps in each phase see:

- [Offboard macOS device](offboard-device/mac-os-using-script)

<!--
## Overview of the offboarding phases

| Phase A: Offboard device from SEED components  | Phase B: Submit Intune Device ID to remove device record to remove device record |
| ------------- |:-------------:|
| Step 1. Download the offboarding script for your Defender.<br><br>Step 2.Run this offboarding script on your device to:<br><br>-&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;unenroll your device from the SEED components.<br>-&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; reset some configuration settings modified while onboarding.<br><br>When you complete these, you are directed to **Phase B**.| Step 1: EnsureSubmit a request to remove the device record from the server side.<br>When we delete your device record from the server side, we notify you about your successful offboarding.     |

In **Phase A**, you need to do the following:

1. Download the offboarding script for your Defender. 
2. Run this offboarding script on your device to:

    - unenroll your device from the SEED components such as Intune, Tanium, Defender and Cloudflare WARP. 
    - reset some of the configuration settings that were modified during SEED onboarding.

    When you complete them, you are directed to **Phase B**.

!>**Important note**<br> Make sure you complete **Phase B** immediately after **Phase A**. If not, your device update policy may reinstall the latest version of the deleted SEED components.  

In **Phase B**, you need to submit a request to remove the device record from the server side.

When we delete your device record from the server side, we notify you about your successful offboarding.





## Method 2: Offboard manually



- [Offboard macOS device manually](offboard-device/mac-os)
- [Offboard Windows device manually](offboard-device/windows)
-->

