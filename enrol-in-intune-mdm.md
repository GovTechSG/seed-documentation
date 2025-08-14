# Enrol in Intune MDM (macOS)

Before registering a Mac device with Platform SSO (PSSO), you must enrol it in Microsoft Intune using the Company Portal app. Once enrolled, you can use Secure Enclave, smart card, or password to register your device with PSSO.

If you have already onboarded to SEED, you can skip this step.

## Steps to enrol

1. **Open the Company Portal app** and select **Sign in**.  
2. **Enter your Microsoft Entra ID credentials** and select **Next**.  
3. When prompted to **Set up {Company} access**, select **Begin**. On the next screen, select **Continue**.  
4. Follow the instructions to install the management profile. This profile should have been set up by your administrator in Microsoft Intune. Select **Download profile**.  
5. If the profile window does not open automatically, navigate to **Settings** > **Privacy & Security** > **Profiles** and select **Management Profile**.  
6. Select **Install** to grant access to company resources.  
7. Enter your local device password in the **Profiles** window and select **Enrol**.  
8. Once installation is complete, you will see a notification in Company Portal. Select **Done**.  


After completing these steps, your device will be enrolled in Intune MDM and ready for Platform SSO registration.
