# SEED service status

This page provides the following Information:
- [Scheduled maintenance](#scheduled-maintenance)
- [Ongoing incidents](#ongoing-incidents)
- [Previous incidents](#previous-incidents)

## Scheduled maintenance

None

## Ongoing incidents
| Date | 20 September 2022 |
| ------------- |:-------------|
| **Issue summary** | Generally, when SEED users connect to a VPN with Cloudflare WARP active, WARP gets disabled and re-enabled. If users disable WARP before connecting to the VPN,  WARP gets re-enabled. We have identified an issue when Cloudflare gets re-enabled, and users attempt to connect to a VPN that is not on the allowlist. We have raised an issue with Cloudflare to resolve this.<br><br>**Impact:**<br>When WARP gets re-enabled, and if the VPN is not in the allowlist, users will not be able to connect to the VPN.<br><br>**Action recommended:**<br>Uninstall WARP and wait for Microsoft Intune to push down the old version. |

## Previous incidents
| Date | 08 September 2022 |
| ------------- |:-------------|
|**Issue summary** | We identified an issue with Cloudflare Gateway on 08 September 2022, 14:41 SGT, and our users are currently unable to access Microsoft websites to authenticate their logins. We are working with Cloudflare to implement a fix.<br><br>**Impact:**<br>Users will not be able to authenticate their login while accessing SGTS services, including GCC 2.0.<br>*Posted on: 08 September 2022, 16:28 SGT*<br><br>**Updates**:<br><br>**Mitigated**<br> While waiting for a fix from Cloudflare, GovTech implemented a workaround on 08 September 2022, 17:00 SGT mitigating the issue at 17:15 SGT. Users will now be able to access SGTS services.<br>*Posted on: 08 September 2022, 17:22 SGT*<br><br>**Resolved** <br>On September 09 2022, 08:26 SGT Cloudflare confirms that the issue has been resolved. |

| Date| 30 August 2022|
| ------------- |:-------------|
|**Issue summary** | An issue was identified with Cloudflare Access on 30 August 2022, 12:00 SGT. A fix was implemented on 30 August 2022, 12:14 SGT and Cloudflare has resolved the issue at 12:39 SGT.<br><br>**Customer Impact:**<br>Users may not have been able to access the Internet and SGTS services during this time.|

| Date| 21 June 2022|
| ------------- |:-------------|
|**Issue summary** | An issue has been identified with Cloudflare services on 21 June 2022, 14:34 SGT. A fix has been implemented on 21 June 2022, 15:20 SGT and we are monitoring the outcome.<br><br>**Customer Impact:**<br> Users may have observed 500 errors while accessing the Internet and Cloudflare protected SGTS services using Cloudflare WARP.<br>While we monitor the fix, if you are still unable to access the Internet, please turn off WARP to access the Internet and create an [incident support request](raise-an-incident-support-request) with the respective SGTS service or product team.<br>You may also visit the [Cloudflare status page](https://www.Cloudflarestatus.com/) for recent updates on this issue.|

### Cloudflare status

You may also visit the [Cloudflare status page](https://www.Cloudflarestatus.com/) for recent updates on issues with Cloudflare Zero Trust, WARP, Cloudflare Tunnel and Cloudflare Access.
