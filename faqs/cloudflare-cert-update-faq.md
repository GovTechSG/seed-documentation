<!-- !> This documentation is obsolete. Refer to [SHIP-HATS documentation](https://docs.developer.tech.gov.sg/docs/ship-hats-docs/) for more details. -->

# Cloudflare Certificate Update

This article guides you to update the Cloudflare Cert on your GMD

## Download Cloudflare Root Certificates

Click on the links to download the certifcate to your GMD.

| Environment | Certificate | Validity |
| --- | --- |--- |
| Cloudflare PROD | [Cloudflare_CA_old.crt](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA_old.crt)<br>[Cloudflare_CA_old.pem](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA_old.pem) | Currently active until 13 Jan 2025|
| Cloudflare PROD | [Cloudflare_CA.crt](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA.crt)<br>[Cloudflare_CA.pem](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA.pem) | 13 Jan 2025 to 26 Dec 2029 |
| Cloudflare DEV | [Cloudflare_CA _dev.crt](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA_dev.crt)<br>[Cloudflare_CA_dev.pem](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA_dev.pem) | Currently active 18 Dec 2029 |
| Cloudflare STG |[Cloudflare_CA _stg.crt](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA_stg.crt)<br>[Cloudflare_CA_stg.pem](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/assets/Cloudflare_CA_stg.pem) | Currently active 23 Dec 2029 |

## Certificate update for macOS

To install a Cloudflare certificate in macOS, you need to download a certificate in .crt format.
1.	Download a Cloudflare certificate.
2.	Open the .crt file in Keychain Access. If prompted, enter your local password.
3.	In **Keychain**, choose the access option that suits your needs and select **Add**.
4.	In the list of certificates, locate the newly installed certificate. Keychain Access will mark this certificate as not trusted. Right-click the certificate and select **Get Info**.
5.	Select **Trust**. Under **When using this certificate**, select _Always Trust_.
The root certificate is now installed and ready to be used.

## Certificate update for Windows

1.	Download a Cloudflare certificate.
2.	Right-click the certificate file.
3.	Select **Open**. If a security warning appears, choose **Open** to proceed.
4.	The **Certificate** window will appear. Select **Install Certificate**.
5.	Now choose a Store Location. If a security warning appears, choose **Yes** to proceed.
6.	On the next screen, select **Browse**.
7.	In the list, choose the _Trusted Root Certification Authorities_ store.
8.	Select **OK**, then select **Finish**.
The root certificate is now installed and ready to be used.

> **Note**:
>- Link to: [Configuration of common Developer CLI tools with Cloudflare WARP](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/faqs/configuration-of-common-developer-cli-tools-with-cloudflare-warp.md)
<br><br>Once you have downloaded the respective certificate, you can configure your Developer CLI tools to trust the Cloudflare Certificate.
