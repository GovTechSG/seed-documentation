# Cloudflare WARP FAQ

<details open>
<summary style="font-size:20px;font-weight:bold">What should I do if I am unable to browse the internet using Cloudflare WARP?</summary>

Check if you are connected to any VPN. If you are still connected to your VPN, you may not be able to access the internet as it conflicts with your DNS resolver configuration. To resolve this, disconnect from your VPN and make sure only Cloudflare WARP is connected.

</details>
     <hr />
<details open><summary style="font-size:20px;font-weight:bold">I had to use my VPN and as recommended by SEED, I had turned off Cloudflare WARP and connected to VPN. After three hours, when Cloudflare WARP automatically reconnects, I am unable to browse the internet. What could be the reason and how to resolve it?</summary>

If you disconnect Cloudflare WARP on your device, it gets automatically reconnected after three hours. At that time, if you are still connected to your VPN, you may not be able to access the internet as it conflicts with your DNS resolver configuration.

To resolve this, disconnect the device from your WiFi and reconnect it to your WiFi to reset the DNS resolver settings or restart your device.

In addition, make sure the VPN configuration does not route all traffic and DNS queries to the VPN server. Our recommendation is not to turn on WARP and the VPN at the same time.

</details>
     <hr />

<details open>
<summary style="font-size:20px;font-weight:bold">I am unable to access a particular website. I get an <em>Access restricted</em> error or <em>DNS error</em> while accessing this website.</summary>

The following can cause this issue:

- Gateway may have blocked these sites as WARP works with Cloudflare Gateway to block websites that are identified as malware sources or a security risk as per our security policy.

- DNS resolution for the website may fail because of WARP and Gateway.

*To resolve gateway issues for trusted sites*

1. Turn off WARP.
2. Ensure Microsoft Defender is running to protect your device against malware.

?> Note WARP connection will automatically reconnect after three hours.

*To resolve DNS error for your device*

<details><summary style="font-size:20px;font-weight:bold">macOS</summary>

1. Go to **Apple** menu > **System Preferences** > **Network**.

<kbd>![network](../images/resolve-dns-error-macos/network.png)</kbd>


2. Select **Wi-Fi** from the left pane and click **Advanced**.

?> If the lock icon at the lower left appears locked, click it to unlock the preference pane.

<kbd>![wifi](../images/resolve-dns-error-macos/wifi.png)</kbd>

3. Go to the **DNS tab** and click the plus icon.

<kbd>![DNS](../images/resolve-dns-error-macos/advanced-dns.png)</kbd>

4. Enter 1.1.1.1 and click the plus icon again.

<kbd>![DNS1](../images/resolve-dns-error-macos/dns-1.png)</kbd>

5. Enter 1.0.0.1 and click **OK**.

<kbd>![DNS2](../images/resolve-dns-error-macos/dns-2.png)</kbd>

6. Click **Apply**

<kbd>![apply DNS changes](../images/resolve-dns-error-macos/apply-dns-changes.png)</kbd>

7. Restart your browser and verify if you can access the SEED-trusted websites such as GCC 2.0 CMP and any secured public website.
8. If you still cannot access SEED-trusted websites, [create a support request][raise-support-request].
</details><br>

<details><summary style="font-size:20px;font-weight:bold">Windows</summary>

1. Select **Start** > **Settings** > **Network & Internet**.

<kbd>![change-adapter-options](../images/resolve-dns-error-windows/change-adapter-options.png)</kbd>

2. In the **Status** page, under **Advanced network settings** , select **Change adapter options**. The **Network Connections** page is displayed.
3. Right-click **Wi-Fi** and select **Properties**.

<kbd>![wifi-properties](../images/resolve-dns-error-windows/wifi-properties.png)</kbd>

4. Select **Internet Protocol Version 4(TCP/IPv4)** and click **Properties**.

<kbd>![ipv4](../images/resolve-dns-error-windows/ipv4.png)</kbd>

5. In the **General** tab, select **Use the following DNS server addresses**.

<kbd>![existing-dns-server-address](../images/resolve-dns-error-windows/existing-dns-server-address.png)</kbd>

?> Note down your existing settings for future reference.

6. Enter **1.1.1.1** as **Preferred DNS server** and **1.0.0.1** as **Alternate DNS server** addresses.

<kbd>![new-dns-server-address](../images/resolve-dns-error-windows/new-dns-server-address.png)</kbd>

7. Click **OK** and exit the window.
8. Restart your browser and verify if you can access the SEED-trusted websites such as GCC 2.0 CMP and any secured public website.
9. If you still cannot access SEED-trusted websites, [create a support request][raise-support-request].

</details>
</details>
     <hr />

<details open>
<summary style="font-size:20px;font-weight:bold">While using some tools and applications with Cloudflare WARP Client, why do I get SSL errors?</summary>

Your tool or application may be using a certificate store that is separate from the trusted root certificate store of your system.

  1. Download the Cloudflare CA certificate to your root system store(s) from the [Cloudflare documentation page][install-cloudflare-cert-operating-system].
  2. Refer to your CLI tool documentation and configure it to trust the Cloudflare root certificate.
  3. You can also refer to the following links for instructions to configure your tool or application:
     * [GovTech instructions for commonly used CLI tools across Singapore
       Government developers][config-cli-tools-with-warp], or
     * [Cloudflare instructions for configuring commonly used developer CLI
       tools][install-cloudflare-cert-applications].

</details>
<hr />

<details open>
<summary style="font-size:20px;font-weight:bold">I am unable to access the GCC 2.0 Cloud Management Portal, or a Singapore Tech Stack service. Is there a problem with my Government Managed Device?</summary>

If you are unable to access the GCC 2.0 CMP or any SGTS service, do the following:

1. Confirm the following:
    - If you have received the successfully onboarded email from DEEP.
    - If you are using only the [supported browsers](additional-resources/best-practices).
    - Ensure that Cloudflare WARP client is updated to the latest version and is connected. Go to Cloudflare WARP **Settings**, and ensure that **Gateway with WARP** is selected.
    - If Tanium is listed in the **Start** menu for Windows and in **Finder** > **Applications** for macOS.
    - If your device operating system is updated to the latest version.
    - If Defender is up-to-date and in the running state.
    - If your TechPass account has the required permissions to access the GCC 2.0 CMP or a particular SGTS service.

2. Make sure the VPN configuration does not route all traffic and DNS queries to the VPN server. Our recommendation is not to turn on WARP and the VPN at the same time.

If you still have issues, [Generate diagnostic report](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/faqs/how-to-generate-and-upload-diagnostic-files-to-incident-support-request) and upload it to the [incident support request][raise-support-request].

</details>
<hr />

<details open>
<summary style="font-size:20px;font-weight:bold">I intermittently experience the error message: "<em>That account does not have access</em>" when accessing SGTS services using Cloudflare WARP.</summary>

This is a known issue with Cloudflare WARP. If you are unable to access any SGTS service, do the following:

1. Confirm the following:
    - If you have received the successfully onboarded email from DEEP.
    - If you are using only the [supported browsers](additional-resources/best-practices).
    - Ensure that Cloudflare WARP client is updated to the latest version and is connected. Go to Cloudflare WARP **Settings**, and ensure that **Gateway with WARP** is selected.
    - If Tanium is listed in the **Start** menu for Windows and in **Finder** > **Applications** for macOS.
    - If your device operating system is updated to the latest version.
    - If Defender is up-to-date and in the running state.
    - If your TechPass account has the required permissions to access the GCC 2.0 CMP or a particular SGTS service.

2. Make sure the VPN configuration does not route all traffic and DNS queries to the VPN server. Our recommendation is not to turn on WARP and the VPN at the same time.

If you still have issues, [Generate diagnostic report](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/faqs/how-to-generate-and-upload-diagnostic-files-to-incident-support-request) and upload it to the [incident support request][raise-support-request].

</details>
<hr />

<details open>
<summary style="font-size:20px;font-weight:bold">Tanium client returns a 400 Bad Request Error when contacted by the Cloudflare Access landing page via localhost. What should I do? </summary>

This is due to the time synchronisation issue between Cloudflare and Tanium client. To fix this, resync the local time of your macOS or Windows machine.

To check and synchronise your device time with the internet time server:

  <details><summary style="font-size:20px;font-weight:bold">For macOS device</summary>

   1. From the **Apple** menu, go to **System Preferences** > **Date & Time**.
   2. Click the lock icon and use your Touch ID or enter your password to unlock.
   3. Select the **Set date and time automatically** checkbox.
   4. To use a custom network time server, enter the domain name of the server in the .
   ![synchronise your Mac time](../images/sync-clock-on-mac.png)
  </details>

  <details><summary style="font-size:20px;font-weight:bold">For Windows 10 device</summary>

    1. Open the **Start** menu and click **Settings**.
    1. Choose **Time & Language**.
    1. Turn on **Set time automatically**.
    1. Click **Sync now** to synchronise with the time server.
    1. If you’d like to use a custom network time server, click **Date, time & regional formatting** from **Related Settings** at the upper-right corner. The **Region** settings page is displayed.
    1. Click **Additional date, time & regional settings** from **Related settings** at the upper-right corner. The **Clock and Region settings** page is displayed.
    1. Click **Date and Time**.
    1. Go to the **Internet Time** tab and select **Change settings**.
    1. Enter the domain name of the server.

  </details>
  </details>  
  <hr />

  <details open>
  <summary style="font-size:20px;font-weight:bold">Can I request to include IP addresses or domains in the Cloudflare WARP split tunnel list to exclude them from going through WARP and redirect them to go though other VPN?</summary>

  Currently, we do not accept requests for split tunnel or fallback domain entries because from a security compliance perspective, it would allow endpoints to access other VPN networks and act as a network bridge. If you want to connect to other VPN networks, turn off Cloudflare WARP temporarily. Note that Cloudflare WARP when manually turned off, will be automatically turned on after three hours.

  </details>
  </hr>











[raise-support-request]: raise-an-incident-support-request.md
[install-cloudflare-cert-operating-system]: https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert/#add-the-certificate-to-your-system
[config-cli-tools-with-warp]: faqs/configuration-of-common-developer-cli-tools-with-cloudflare-warp
[install-cloudflare-cert-applications]: https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert/#adding-to-applications
