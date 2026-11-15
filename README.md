# Microsoft-365-Administration-Lab-CloudLab-Enterprises

A hands-on Microsoft 365 administration project built in a free Microsoft 365 E5 developer tenant. I set up a fictional company, CloudLab Enterprises, and administered it as its new IT administrator: users and licences, Exchange Online, SharePoint and OneDrive, Teams, Intune, Conditional Access, Defender and Purview.
Contents
Overview
Objectives
Technologies Used
Skills Demonstrated
Environment
Lab Architecture
Project Scope
Repository Structure
Implementation Summary
Configuration Reference
Validation and Testing
Troubleshooting
Security Considerations
Lessons Learned
Future Improvements
Author

Overview
Microsoft 365 appears in almost every IT support, help desk, system administrator and cloud support job description. I wanted to manage it myself rather than only read about it, so I joined the Microsoft 365 Developer Program, which provides a free E5 tenant for learning and testing. It uses the same admin portals as a production tenant, so this is not a simulator.
To give each task a business reason, I created CloudLab Enterprises, a professional services company with five departments and twelve users, and worked as though I had just been hired to run its IT. For each setting I recorded what I changed and why.
Screenshot Placeholder
Insert screenshot here: screenshots/m365-admin-center-home.png
Expected capture: Microsoft 365 admin center home page for the cloudlabent tenant with the admin account signed in.
Why it matters: Shows the real tenant the project was built in.
Capture from: Microsoft 365 admin center, home. Redact the personal account name if it is shown.
Objectives
Build a realistic tenant with departments, users, licences and administrative roles.
Administer Exchange Online: mailboxes, shared mailbox, distribution groups, mail flow rules and email protection.
Structure SharePoint and OneDrive with least-privilege permissions and restricted external sharing.
Govern Teams creation and configure messaging and meeting policies.
Manage Windows devices with Intune and tie compliance to Conditional Access.
Use Purview and Defender for auditing, data loss prevention, sensitivity labels and threat protection.
Document the decisions, tests and the mistakes made along the way.

Technologies Used
Area
Technology
Tenant
Microsoft 365 Developer Program, E5 developer tenant (Instant Sandbox)
Administration
Microsoft 365 admin center
Email
Exchange Online, Exchange admin center
Collaboration
SharePoint Online, OneDrive for Business, Microsoft Teams, Teams admin center
Identity and access
Microsoft Entra ID, Conditional Access
Endpoint management
Microsoft Intune, Windows Autopilot
Threat protection
Microsoft Defender for Office 365 (Safe Attachments, Safe Links, anti-phishing, anti-spam)
Compliance
Microsoft Purview (Audit, DLP, sensitivity labels), Microsoft Secure Score
Skills Demonstrated
Skill
Where it appears
Tenant setup, custom domain and DNS records
Tenant setup
Licensing, mailbox and shared mailbox administration
Exchange Online
Mail flow rules and email security policies
Exchange Online
Site, library and permission design, sharing policy
SharePoint and OneDrive
Teams governance, messaging and meeting policy
Microsoft Teams
Enrolment, configuration profiles, compliance, app deployment, remote actions
Intune
Conditional Access with report-only mode and break-glass accounts
Intune, Troubleshooting
Audit search, DLP, sensitivity labels, Secure Score, Defender
Security and compliance
Troubleshooting from evidence
Troubleshooting
Environment
Item
Detail
Program
Microsoft 365 Developer Program (free), Instant Sandbox
Licences
Microsoft 365 E5, 25 available, 12 assigned
Tenant domain
cloudlabent.onmicrosoft.com
Custom domain
Added and verified, status Healthy (name not recorded in this repository)
Company
CloudLab Enterprises, professional services
Departments
IT, Finance, Human Resources, Sales, Management
Users
12
Administrative roles
Global Administrator, IT Administrator, Exchange Administrator
This is a developer sandbox, not a production tenant. No real company or customer data is involved.
Lab Architecture
flowchart TB
    ENTRA["Microsoft Entra ID<br/>users, groups, Conditional Access"]
    EXO["Exchange Online<br/>mailboxes, mail flow rules"]
    SPO["SharePoint Online and OneDrive<br/>sites, libraries, sharing policy"]
    TEAMS["Microsoft Teams<br/>teams, channels, policies"]
    INTUNE["Microsoft Intune<br/>enrolment, profiles, compliance"]
    DEF["Microsoft Defender<br/>Safe Links, Safe Attachments, anti-phishing"]
    PUR["Microsoft Purview<br/>audit, DLP, sensitivity labels"]
    ENTRA --- EXO
    ENTRA --- SPO
    ENTRA --- TEAMS
    ENTRA --- INTUNE
    TEAMS -- "files stored in" --> SPO
    INTUNE -- "device compliance" --> ENTRA
    DEF -- "protects" --> EXO
    DEF -- "protects" --> TEAMS
    PUR -- "audits and protects data in" --> EXO
    PUR -- "audits and protects data in" --> SPO
    PUR -- "audits and protects data in" --> TEAMS
files stored in

device compliance

protects

protects

audits and protects data in

audits and protects data in

audits and protects data in

Microsoft Entra ID
users, groups, Conditional Access

Exchange Online
mailboxes, mail flow rules

SharePoint Online and OneDrive
sites, libraries, sharing policy

Microsoft Teams
teams, channels, policies

Microsoft Intune
enrolment, profiles, compliance

Microsoft Defender
Safe Links, Safe Attachments, anti-phishing

Microsoft Purview
audit, DLP, sensitivity labels
