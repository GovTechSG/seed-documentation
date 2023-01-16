# Known issues

Following is the list of known issues that may impact SEED users:

**Issues**

-[Issue 1](#issue-1)

-[Issue 2](#issue-2)


## Issue 1

When accessing SGTS services using Cloudflare WARP, user intermittently experience an error message which states *That account does not have access*.

**Workaround**

1. Ensure you answer "Yes" to the following verifications:

    - If you have received the successfully onboarded email from DEEP.
    - If you are using only the [supported browsers](additional-resources/best-practices).
    - Is your Cloudflare WARP client connected and is it the latest version. 
    - Open Cloudflare WARP **Settings**, and verify if **Gateway with WARP** is selected.
    - If your device is a Windows device, go to the **Start** menu and verify if Tanium is listed.
    - If your device is a macOS device, go to **Finder** > **Applications** and search for Tanium.
    - If your device operating system is updated to the latest version.
    - If Defender is up-to-date and in the running state.
    - If your TechPass account has the required permissions to access the GCC 2.0 CMP or a particular SGTS service.

    2. If you answered "No" to anyone of the questions, take the required actions until you answer "yes" to all the above queries.

> **Note**
>- SEED does not support running other VPN clients together with Cloudflare WARP. 
>- We recommend not to turn on WARP and the VPN at the same time.

3.  Verify if you are running any VPN client concurrently with warp on and complete the following steps as needed:

    a. If yes, make sure the VPN configuration does not route all traffic and DNS queries to the VPN server.

    b. If no, proceed to step 3.

4. If you still have issues, [Generate diagnostic report](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/faqs/how-to-generate-and-upload-diagnostic-files-to-incident-support-request) and upload it to the [incident support request][raise-support-request].

## Issue 2

Cloudflare has reported connectivity issues for its users whose macOS WARP client version is earlier than 2022.12.583.0 (20230112.24). These users may experience connectivity issues while trying to access websites over the internet.

**Workaround**

Upgrade to the latest version of Cloudflare WARP.

1. Open Cloudflare WARP on your GMD.
2. Click **Settings** > **About WARP**.
3. If your Cloudflare version is earlier than 2022.12.583.0 (20230112.24), click **Check for Updates**. Details of the latest version are displayed.
3. Click **Install Updates**. The new version gets downloaded to your GMD.
4. When prompted, enter your device password and click **OK**.
5. Click **Install and Relaunch** to install the downloaded latest version of Cloudflare WARP.
6. Repeat steps 1-2 and confirm if the latest Cloudflare version is installed on your GMD.











