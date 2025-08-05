# Case Study:  Driving Adoption and Governance for Delinea Secret Server

## Overview:
</br>

<img align="left" alt="Portfolio Logo" width="400px" src="https://imgur.com/XBXvohW.jpg" />
</br>

- **Position**:  Information Security Analyst, Subject Matter Expert (SME)  
- **Timeframe**:  6 months
- **Objective**:  Increase adoption of Delinea Secret Server across IT operations and ensure secure, policy-aligned management of privileged credentials.
</br>
</br>
</br>


## Background
- **Context**:  Delinea (formerly Thycotic) Secret Server had been deployed for nearly two years prior to my involvement, but enterprise adoption remained extremely low.  Many teams continued storing credentials in unapproved tools or unmanaged formats (e.g., shared Excel files, KeePass, or personal storage).
- **Stakeholders**:  Information Security Office, Security Engineering & Architecture Team, Infrastructure & App Teams, Compliance Team, Desktop Support, Risk & Policy Governance

## Problem Statement
- Despite the existence of a licensed PAM solution, no formal onboarding process or policy enforcement had been developed.  This left privileged credentials scattered, unmanaged, and out of compliance with security best practices.  Additionally, multiple tools (Tanium, CrowdStrike, AD) provided conflicting privileged account inventories, further complicating efforts to secure access.

## Approach
- **Research and Analysis**:  Reviewed privileged account data from Tanium, CrowdStrike, and Active Directory to understand the scale of unmanaged credentials.  Tanium was selected as the source of truth due to its millisecond-level endpoint telemetry and active client presence across the environment.
- **Methodology**:  Worked with Security Champions to establish a campaign to integrate Delinea into daily IT operations, developed governance frameworks, and built self-service onboarding tools to reduce user friction.
- **Tools and Technologies**:
    - Delinea Secret Server (PAM)
    - Tanium (account discovery)
    - Active Directory, CrowdStrike (reference sources)
    - SharePoint (onboarding hub)
    - ServiceNow (request automation)
    - PowerShell (automation)
    - PolicyTech (policy enforcement)

## Implementation

<img align="right" alt="PKI2" width="400px" src="https://imgur.com/nKe47Id.jpeg" />
  
**Steps Taken**:
1.	Privileged Account Source of Truth:  Compared AD, CrowdStrike, and Tanium results.  Chose Tanium due to active endpoint telemetry and near real-time reporting.  Standardized on Tanium for ongoing account discovery validation.

2.	Governance and Policy Enforcement:  Coordinated with Director of Security and Policy Governance Team.  Updated secrets management policies in PolicyTech to require Delinea usage for NetIDs, service accounts, and shared access credentials.  Formalized privileged account lifecycles, access requests, and audits.

3.	Onboarding & Support Hub:  Built a SharePoint site with the following features:
      - Delinea onboarding request form (ServiceNow integration)
      - Video tutorials and walkthroughs
      - System update announcements and scheduled downtime notices
      - Survey forms for user experience feedback
      - KB links and internal documentation
      - Booking system for lunch-and-learn sessions

4.	Knowledge Base & Training:  Authored and published end-user KBs and internal runbooks.  Topics included secret creation, folder permissions, API usage, and platform best practices.  Demonstrated Delinea capabilities in team meetings and security roadshows.

5.	Technical Support & Integration:  Resolved firewall issues between Delinea vault and segmented infrastructure.  Filed and tracked vendor support tickets to fix platform bugs.  Led efforts to integrate mRemoteNG with Delinea for credential injection.  Migrated credentials from unsupported vaults and manual storage systems.  Developed secret templates and permission tiers aligned to departmental needs.


**Challenges Faced**:  The broad wildcard domain (*.s3.amazonaws.com) requested by the vendor posed a significant security risk, allowing unrestricted access to a wide range of AWS services.  Additionally, Zscaler's role as a man-in-the-middle disrupted the SSL handshake by interrupting the certificate pinning process, complicating the connection.  Coordinating with the vendor to provide more specific domains was critical.  Implementing an SSL bypass for specific domains was suggested by Zscaler's documentation, meaning there would be no deep packet inspection of traffic to its domains. Vendor and website validation was an imperative, along with assuring our EDR's and firewalls were in place as a contigency.   

## Results
**Outcomes**:  Successfully implemented SSL bypass for the vendor's application, ensuring secure and seamless connections while maintaining security posture.
- Vault usage increased over 400% within 6 months.
- More than 60% of technical teams onboarded with their own team folders and credential workflows compared with less than 10% before campaign.
- Compliance risk reduced by eliminating unmanaged vaults.
- Delinea became the standard and enforced tool for secrets management across departments.

**Impact**:  Enhanced the organization's security posture by eliminating the need for an SSL bypass for millions of sites.
- Secure access workflows were normalized and repeatable.
- Secrets were now auditable, owned, and managed with lifecycle controls.
- Departmental silos were broken down by a centralized, transparent secrets platform.

## Lessons Learned
- **Championing Governance is Critical:** Even with a deployed tool, adoption doesn’t happen unless policies back it and leadership drives the message.
- **Simplified Onboarding Wins:** A central, clean, and user-friendly support hub made it easy for teams to self-onboard without security team handholding.
- **Choose One Source of Truth:** Reconciling conflicting data sources can delay implementation. Aligning on Tanium early allowed consistent reporting and reduced audit noise.
- **Train & Document Everything:** Providing runbooks and videos reduced support tickets, empowered teams, and ensured long-term adoption.

## Conclusion
This case study highlights the importance of not just deploying a security tool, but operationalizing it. Through governance, cross-team collaboration, and focused enablement, I transformed Delinea Secret Server from shelfware into a foundational security tool — reducing risk, increasing adoption, and improving our enterprise security posture.
