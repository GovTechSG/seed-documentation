# SonarQube

SonarQube is an automatic code review tool to detect bugs, vulnerabilities, and code smell. We support two versions of SonarQube:
- Sonarqube Community Edition
- Sonarqube Developer Edition

By default, SonarQube Community edition is available with all the tier subscription (except for Starter tier). If you need the Developer edition, you must buy the [add-on of additional languages](https://www.developer.tech.gov.sg/products/categories/devops/ship-hats/subscription.html). With the additional languages add-on purchased, as the Subscription Administrator (SA) or Project Administrator (PA), you will have the flexibility to create SonarQube applications from both the Community and Developer editions.

|**Subscription Package**|**Add-ons**|**SonarQube Instance**|
|---|---|---|  
|Starter|None|None|
|Starter|Basic languages|Community|
|Starter|Basic languages + Additional languages|Developer + Community|
|All other Packages except Starter|None|Community|
|All other Packages except Starter|Additional languages|Developer + Community|

As an SA, after you have bought the Additional languages add-on, you cannot remove the add-on if your subscription still has SonarQube applications in the Developer edition. You will need to remove all the SonarQube applications in the Developer edition before you can downgrade and remove the add-on. 
<!--
**Topics**  

- [Set up Community Edition](sonarqube-set-up-community-edition)
- [Set up Developer Edition](sonarqube-set-up-developer-edition)
- [Self Help Guide](sonarqube-self-help-guide)


## Access
### To log in to SonarQube: 

1. Go to [SonarQube](https://sonar.hats.stack.gov.sg/sonar).
1. Click **Log in with SAML**.

    ![sonarqube](sonarqube-tp.png)

    If you have not logged into your TechPass, you will be prompted to sign in. For more details, refer to the [TechPass user guide](https://docs.developer.tech.gov.sg/docs/techpass-user-guide/#/) if you are logging in to TechPass for the first time.
1. Authenticate and approve your TechPass login using your Microsoft authenticator app with your SG Govt M365 profile. 
1. After you have authenticated, you will be redirected to your SonarQube dashboard.


## FAQs

<details>
  <summary>What are the 15 supported languages?</summary><br>

Java, JavaScript, C#, TypeScript, Kotlin, Ruby, Go, Scala, Flex, Python, PHP, HTML, CSS, XML, VB.NET.
Do take note that there is no restriction of lines of code and number of applications.

  </details>

 <details>
  <summary>Based on SonarQube’s add-ons, what are the 7 others supported languages?</summary><br>

C, C++, Obj-C, Swift, ABAP, T-SQL, PL/SQL are supported. Public officers can refer to the <a href="https://sgdcs.sgnet.gov.sg/sites/IDA-GoSync/gdspdd-ai/ship/_layouts/15/start.aspx#/SitePages/Pricing.aspx">pricing</a> for the add-ons.

  </details>

 <details>
  <summary>Are COTS (commercial off-the-shelf) products supported on SonarQube?</summary><br>

Yes. SonarQube can scan for any customisation that the COTS product supports.
Example: Configuration files in XML or Javascript/ Java or plugins written in Java or Python.
  </details>

-->