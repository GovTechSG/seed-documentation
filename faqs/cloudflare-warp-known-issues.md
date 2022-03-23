## Known Issues with Cloudflare WARP

<details>
<summary>1. Though my VPN is connected, I am unable to browse the Internet once my WARP reconnects?</summary>


If you disconnect WARP on your device, it gets automatically reconnected
after three hours. At that time, if you are still connected to your VPN,
you may not be able to access the internet as this conflicts with your
DNS resolver configuration.


To resolve this, disconnect the device from your WiFi and reconnect it
to your WiFi to reset the DNS resolver settings or restart your device.


In addition, make sure the VPN configuration does not route all traffic
and DNS queries to the VPN server. Our recommendation is not to turn on
WARP and the VPN at the same time.

</details>
<hr />

<details>
<summary>2. I am unable to access a particular website, is it because of WARP?</summary>

WARP works with Cloudflare Gateway to block websites that are identified
as malware sources or a security risk. If sites related to your
developer resources are blocked and you still need to access the site,
then turn off WARP. Ensure Microsoft Defender is active to protect your
device against malware.

?> The WARP connection will automatically reconnect after three hours.

If the site is not blocked by Cloudflare Gateway and instead shows a DNS
Error even after several tries, please follow our
[instructions to raise a SEED Support Request][raise-support-request].

</details>
<hr />

<details>
<summary>3. While using some tools and applications with Cloudflare WARP Client, why do I get SSL errors?</summary>

Your tool or application may be using a certificate store that is
separate from your system's trusted root certificate store.

1. Download the Cloudflare CA Certificate to your root system store(s)
   from the [Cloudflare documentation
   page][install-cloudflare-cert-operating-system].
2. Refer to your CLI tool documentation and configure it to trust the
   Cloudflare Root certificate.</li>
3. You can also refer to the following links for instructions to
   configure your tool or application:

* [Our instructions for commonly used CLI tools across Singapore
  Government developers][config-cli-tools-with-warp], or
* [Cloudflare instructions for configuring commonly used developer CLI
  tools][install-cloudflare-cert-applications].


</details>
<hr />


<details>
<summary>4.  I am unable to access the GCC 2.0 Cloud Management Portal, or Singapore Tech Stack Service (e.g. SHIP-HATS) Portal, is there a problem with my Government Managed Device?</summary>

SEED uses TechPass, Cloudflare Access and DEEP to ensure you and your
GMD is authorized to access the GCC 2.0 CMP or SGTS service. Please
follow these instructions to troubleshoot if you are having problems
accessing the GCC 2.0 CMP or SGTS service.

1. Ensure that you have received the DEEP onboarding email that marks
   you as onboarded.
2. Ensure that you are using Google Chrome or Microsoft Edge. Mozilla
   Firefox will need to be configured to trust your system's trusted
   root certificate store. Safari is not supported.
3. Ensure Cloudflare WARP is connected and is set to "Gateway with
   WARP".
4. Ensure that Tanium is present on your device. Check that it is listed
   in the Windows Start Menu or macOS Finder Applications folder.
5. Ensure that your device's operating system is patched to the latest
   version, and that Defender ATP is also up-to-date and running on your
   system.
6. Ensure that your TechPass account has been granted the correct
   permissions to access the GCC 2.0 CMP or SGTS service.

If you continue to have issues accessing the GCC 2.0 CMP or SGTS
service, please follow our
[instructions to raise a SEED Support Request][raise-support-request].

</details>

[raise-support-request]: ../raise-an-incident-support-request.md
[install-cloudflare-cert-operating-system]: https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert/#add-the-certificate-to-your-system
[config-cli-tools-with-warp]: ../configuration-of-common-developer-cli-tools-with-cloudflare-warp.md
[install-cloudflare-cert-applications]: https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/install-cloudflare-cert/#adding-to-applications
