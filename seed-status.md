# SEED service status

This page provides the following Information:
- [Scheduled maintenance](#scheduled-maintenance)
- [Ongoing incidents](#ongoing-incidents)
- [Previous incidents](#previous-incidents)

## Scheduled maintenance

None

## Ongoing incidents

None

## Previous incidents

| Date | 18 December 2022 |
| ------------- |:-------------|
| **Issue summary** | On 18 December 2022 at 12:00 SGT, the SEED team received incident requests for login failures. <br><br>This was caused by an integration issue between Cloudflare and Tanium. Users experienced this issue during non-business hours. The issue was resolved at 13:15 SGT. <br>*Posted on: 18 December 2022, 13:50 SGT*



| Date | 21 October 2022 |
| ------------- |:-------------|
|**Issue summary** | Users encountered intermittent HTTP request failures and may have received error code 409 or CORS Blocked messages on their HTTP clients while using Cloudflare WARP Gateway. This issue has been resolved by Cloudflare WARP.<br><br>**Issue start time**: 20 October 2022, 19:45 SGT<br>**Issue end time**: 21 October 2022, 05:34 SGT<br><br>**Impact:**<br> Users may have been unable to access Internet sites intermittently with Cloudflare WARP turned on.<br>*Posted on: 21 October 2022, 09:50 SGT* |

| Date | 20 September 2022 |
| ------------- |:-------------|
| **Issue summary** | **Identified**:<br>With the availability of Cloudflare 2022.8.861.0, we identified an issue on 13 September 2022.<br>Generally, when SEED users connect to a VPN with Cloudflare WARP active, WARP gets disabled and re-enabled. If users disable WARP before connecting to the VPN, WARP gets re-enabled.<br>Users experience issues while connecting to the VPN if it is not on the allowlist.<br><br>**Impact:**<br>Users cannot connect to the VPN if it is not on the allowlist.<br><br>**Action recommended:**<br>While we have raised an issue with Cloudflare to resolve this, if you are impacted, we suggest you uninstall WARP and wait for Microsoft Intune to push down the earlier version of WARP.<br><br>**Updates**<br>**Fix**:<br>Newer version of Cloudflare WARP client will be installed on your GMD to resolve this issue. For more information, refer to [announcement](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/announcements) posted on 21 October 2022.<br>*Posted on: 21 October 2022, 11:11 SGT*<br><br>**Resolved**:<br> This issue is resolved now.<br>*Posted on: 21 October 2022, 16:45 SGT*|

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
