# Set up Secure Enclave

Secure Enclave allows passwordless, phish-resistant sign-in on macOS using hardware-bound cryptographic keys. This setup enables seamless access to Microsoft Entra ID applications after the initial device unlock.

**Prerequisite:** Your device must already be onboarded to SEED before you set up Secure Enclave.


## Platform SSO registration

1. Navigate to the **Registration required** pop-up at the top right of the screen. Hover over the pop-up and select **Register**.  
   ![Registration required pop-up](/images/enclave-1.png)

   For macOS 13 Ventura users, a prompt appears to register your device with Microsoft Entra ID. Enter your sign-in credentials and select **Next**.

2. You are prompted to register your device with Microsoft Entra ID. Enter your sign-in credentials and select **Next**.  
   ![Device registration prompt](/images/enclave-2.png)

   If your administrator has configured multi-factor authentication (MFA) for device registration, open the Authenticator app on your mobile device and complete the MFA flow.

3. When the **Single sign-on** window appears, enter your local account password and select **OK**.  
   ![Single sign-on window](/images/enclave-3.png)

   If you are on macOS 14, you will be prompted to unlock your local account beforehand.

4. When the Microsoft Entra sign-in window appears, enter your Microsoft Entra ID password and select **Sign in**.  
   ![Microsoft Entra sign-in](/images/enclave-4.png)

5. Enable Company Portal as a passkey provider:  
   - Navigate to **Settings** > **General** > **Autofill & Passwords** > **Autofill form**.  
   - Enable **Company Portal**.  
   ![Enable Company Portal as passkey provider](/images/enclave-5.png)

6. You can now use Platform SSO to access Microsoft app resources. From this point on, you will be automatically signed in to Microsoft applications and other apps configured with Entra ID (such as SGTS, GCC 2.0 AWS). Password entry will no longer be required, although MFA challenges will still apply.  
   ![Automatic sign-in to Microsoft apps](/images/enclave-6.png)

7. Your local Mac password is not affected and will still be required to log on to the Mac.

8. For selected users (excluding CEP), your local Mac profile will become a **Standard User** after registering with Platform SSO.  
   ![Standard user profile](/images/enclave-7.png)

   If you do not see the registration prompt, check that the SSO profile is present in your Mac settings.
   ![Profile Settings](/images/enclave-8.png)
   ![Profile Settings](/images/enclave-9.png)
   Alternatively, open **Company Portal**, select your profile icon, and choose **Register for SSO**.

---

## Check device registration status

1. Navigate to **Settings** and select **Users & Groups**.  

2. Select **Edit** next to **Network Account Server** and confirm that **Platform SSO** is listed as **Registered**.

3. To verify the authentication method, select your username in the **Users & Groups** window, then select the **Information** icon. Confirm that the method listed is **Secure Enclave**, **Smart Card**, or **Password**.

4. You can also verify registration using the **Terminal** app. Run the provided command to check the registration status. The output should indicate that SSO tokens have been retrieved. For macOS 13 Ventura users, this command is required to verify registration.
`app-sso platform -s`

6. Once issued, an SSO token is valid for 14 days and will be continuously renewed as long as the device is actively used.  
   ![Verify registration](/images/enclave-10.png)
