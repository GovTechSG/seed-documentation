# Split tunnel allowlisting

With split tunnel allowlisting, GCC 2.0 Tenants can connect to their project system management tools and applications hosted on their project VPNs while still being connected to the Cloudflare WARP.

If agencies intend to allow their project VPNs to be allowed, make sure your request complies with the following are the technical and evaluation criteria:

> **Note**: The approval of split tunnel allowlisting requests is **including but not limited** to the following criteria.

## Technical criteria

Your project VPNs should fulfil the following technical criteria:

- It should not route all traffic (0.0.0.0/0) to the VPN gateway; instead, it should only route private RFC1918 CIDR ranges (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16) and CGNAT RFC 6598 IP ranges (100.64.0.0/10).
- It should not route all DNS queries to the VPN DNS server; instead, it should only route project system DNS domains.

## Evaluation criteria

To evaluate a split tunnel allowlisting request, we need the following from the requester, and they have to be acknowledged and approved by the system’s Agency Chief Information Security Officer (ACISO).

- Evidence that risk assessment and acceptance for the VPN (which you request to be allowed) has been conducted, approved and supported from the system's ACISO or above.
- Acknowledgement from the system’s ACISO or above, that their agency takes the responsibility of allowing concurrent access to the VPN IP and their data stored on GCC 2.0/SGTS applications.
- Acknowledgement from the system’s ACISO or above that GovTech is not responsible for incidents to the requesting agency’s data or systems on GCC 2.0/SGTS applications that may occur as a result of allowing the split tunnel request.

## Request for split tunnel allowlisting

> **Important**: To reduce or prevent harmful security attacks, we strongly encourage agencies to avoid requesting for split tunnel allowlisting.


- [Create a support request to request](https://go.gov.sg/seed-techpass-support) to add the required VPN to the allowlist.

- We will assess your split tunnel allowlisting requests on a case-by-case basis to ensure that the request does not compromise the security of GCC 2.0 or any SGTS applications.

- As part of our security review process, we will periodically review the allowed split tunnel entries to check if they are still necessary.

- To know more about, how the WARP client handles your DNS requests, see [Cloudflare Docs](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/configure-warp/route-traffic/#how-the-warp-client-handles-dns-requests).

> **Note**:<br>
>- We will review the allowed split tunnel entries by **October 2023** to decide whether to retain the allowlisting or not.
>
> **Pilot projects for tools and applications behind Cloudflare Zero Trust**
>
>- We welcome pilot projects to put their project system management tools and applications behind Cloudflare Zero Trust. For more information, contact *ask_codex@tech.gov.sg*.
>
>
>- We strongly encourage GCC 2.0 tenants to use CSP native remote administrative tools to perform remote administration or access their databases instead of using their internet devices to connect directly to workloads or databases through Project VPNs.
