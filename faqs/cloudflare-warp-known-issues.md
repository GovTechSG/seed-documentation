## Known Issues with Cloudflare WARP

<details>
  <summary>1. Though my VPN is connected, I am unable to browse the Internet once my WARP reconnects?</summary>

If you disconnect WARP on your device, it gets automatically reconnected after three hours. At that time, if you are still connected to your VPN, you may not be able to access the internet as this conflicts with your DNS resolver configuration.

To resolve this, disconnect the device from your WiFi and reconnect it to your WiFi to reset the DNS resolver settings or restart your device. <br><br>In addition, make sure the VPN configuration does not route all traffic and DNS queries to the VPN server. Our recommendation is not to turn on WARP and the VPN at the same time.
</details>
     <hr />

<details>
<summary>2. I am unable to access a particular website, is it because of WARP?</summary>

WARP works with Cloudflare Gateway to block websites that are identified as malware sources or a security risk. If sites related to your developer resources are blocked and you still need to access the site, then turn off WARP. Ensure Microsoft Defender is active to protect your device against malware.

?> The WARP connection will automatically reconnect after three hours.

If the site is not blocked by Cloudflare Gateway and instead shows a DNS Error even after several tries, please follow our [instructions to raise a SEED Support Request](../raise-an-incident-support-request.md).
</details>
     <hr />

<details>
 <summary>3. While using CLI tools with Cloudflare WARP Client why do I get SSL errors?</summary>

 Your CLI tool may be using a certificate store that is separate from your system's trusted root certificate store.

 <ol>
   <li>Download the Cloudflare CA Certificate to your root system store(s) from the <a href="https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert#base-operating-system">Cloudflare documentation page</a>.</li>
   <li>Refer to your CLI tool documentation and configure it to trust the Cloudflare Root certificate.</li>
   <li>Alternatively, refer to [our instructions for commonly used CLI tools across Singapore Government developers](configuration-of-common-developer-cli-tools-with-cloudflare-warp), or <a href="https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert/#adding-to-applications">Cloudflare instructions for configuring commonly used developer CLI tools</a>.
</li>
   </ol>
   </details>
      <hr />

<details>
<summary>4.  I am unable to access the GCC 2.0 Cloud Management Portal, or Singapore Tech Stack Service (e.g. SHIP-HATS) Portal, is there a problem with my Government Managed Device?</summary>

SEED uses TechPass, Cloudflare Access and DEEP to ensure you and your GMD is authorized to access the GCC 2.0 CMP or SGTS service. Please follow these instructions to troubleshoot if you are having problems accessing the GCC 2.0 CMP or SGTS service.

1. Ensure that you have received the DEEP onboarding email that marks you as onboarded.
2. Ensure that you are using Google Chrome or Microsoft Edge. Mozilla Firefox will need to be configured to trust your system's trusted root certificate store. Safari is not supported.
3. Ensure Cloudflare WARP is connected and is set to "Gateway with WARP".
4. Ensure that Tanium is present on your device. Check that it is listed in the Windows Start Menu or macOS Finder Applications folder.
5. Ensure that your device's operating system is patched to the latest version, and that Defender ATP is also up-to-date and running on your system.
6. Ensure that your TechPass account has been granted the correct permissions to access the GCC 2.0 CMP or SGTS service.

If you continue to have issues accessing the GCC 2.0 CMP or SGTS service, please follow our [instructions to raise a SEED Support Request](../raise-an-incident-support-request.md).

</details>
<!--

Why am I unable to use my CLI tools such as NPM, Docker and the
   AWS CLI tool with WARP?

   Visit [Cloudflare CLI tools configurations](https://gitlab-in.ship.gov.sg/gcc2.0/seed/cloudflare-support/-/blob/master/cloudflare-cli-tools-configuration.md) for instructions on how to configure applications and CLI tools to work with WARP.


4. When using Cloudflare WARP Client

   * We are finetuning the configuration of Cloudflare Gateway rules to
     Do Not Inspect the Do Not Decrypt group of Applications.
   * Despite having this rule, we are having users report that NPM,
     Docker and the AWS CLI are still raising SSL certificate
     verification errors

4. Users are unable to resolve the DNS services of resources behind the
   SHIP OpenVPN with WARP connected.
   * We demonstrated to Antonio during the POC period that queries for
     SHIP service hostnames were not resolving, even with the SHIP
     service hostnames being in the domain exclusion list and the SHIP
     internal DNS server IP Addresses being in the split tunnel list
   * Antonio is still trying to replicate this issue on his end.
   * The workaround to configure Cloudflare DNS to override responses
     for SHIP service hostnames is working presently, but this solution
     is unscalable as we will be onboarding Developers from across the
     Whole of Government with their own VPNs



### When using Cloudflare WARP Client together with SHIP OpenVPN client, users are unable to visit SHIP services.

When the WARP client and SHIP OpenVPN are connected, DNS requests are
not being sent to SHIP DNS to resolve SHIP Service URLs. We have
presently worked around this by configuring DNS request overrides
returned by Cloudflare.


### When using Cloudflare WARP Client together with SHIP OpenVPN/CheckPoint VPN client on WiFi, users are disconnected from the Internet when switching WARP on or off, or when connecting or disconnecting from the VPN.

We have observed that this occurs after a specific order of events:
1. User disconnects WARP Client
2. User connects to VPN Client
3. WARP Client reconnects after 60 minutes
4. Operating System DNS is altered by VPN and WARP Clients, resulting in
   no Internet.

![windows-no-internet.png](images/windows-no-internet.png)


If this is happening to you, please help report the issue to us, using
the template above and submitting logs and screenshots. Please follow
the section on Collecting Logs and telemetry for Cloudflare WARP and
your VPN client, then follow the section on Restoring Internet
connectivity to your endpoint.


### When using Cloudflare WARP Client, users are unable to visit some public websites on the Internet

Occasionally Cloudflare may fail to resolve public websites on the
Internet. This occurs randomly and quickly resolves itself, so it is
hard to catch. If you do catch it, please follow the section on
Collecting Logs and telemetry for Cloudflare WARP and collect nslookup
output to send to us through the issue tracker.

![microsoft-edge-cannot-resolve-dns.png](images/microsoft-edge-cannot-resolve-dns.png)


## Workarounds


### Restoring WiFi Internet Connectivity

For Windows, please refer to the following guide to restore Internet
connectivity:
https://support.microsoft.com/en-us/windows/fix-wi-fi-connection-issues-in-windows-9424a1f7-6a3b-65a6-4d78-7f07eee84d2c

* Flush your DNS Cache by running the following command:

  ```cmd
  ipconfig /flushdns
  ```


    ```
    sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
    ```

  ![Flush DNS command](images/windows-run-ipconfig-flushdns.png)


* Repair your Network Adapter

For Windows:
1. Right click the Wireless icon in the System Tray
   ![windows-wireless-network-icon.png](images/windows-wireless-network-icon.png)

2. Click on Troubleshoot problems

   ![windows-wireless-network-icon-troubleshoot-problems.png](images/windows-wireless-network-icon-troubleshoot-problems.png)

3. Follow the wizard to reset your Wireless network adapter.

   ![windows-network-troubleshooting-wizard-select-adapter.png](images/windows-network-troubleshooting-wizard-select-adapter.png)

* Reboot your Laptop

  If none of the steps above work to restore Internet Connectivity,
  please reboot your device.


-->
