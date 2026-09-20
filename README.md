🛡️ Enterprise Active Directory & PKI (AD CS) Lab

A comprehensive project deploying and configuring an Active Directory Domain Services (AD DS) environment along with a fully operational, automated Public Key Infrastructure (Active Directory Certificate Services - AD CS) in a virtualized environment.

---

🏗️ Environment Architecture
* Domain: `lab.local`
* Domain Controller (`DC01`): Windows Server 2022 (Roles: AD DS, DNS, Enterprise Root CA).
* Workstation (`WS01`): Client system joined to the `lab.local` domain.

---

🚀 Scope of Work Implemented

1. Active Directory Deployment (AD DS)
* Promoted server `DC01` as a Domain Controller for a new forest (`lab.local`).
* Configured core network DNS name resolution and directory object management.
* Successfully joined the `WS01` workstation to the domain.

2. Certificate Authority Setup (AD CS / PKI)
* Installed and post-configured the Enterprise Root CA role on the Domain Controller.
* Resolved post-installation permission hurdles and verified healthy service status (`certsrv.msc`).

3. Template Management & Certificate Enrollment
* Configured security permissions for the Computer certificate template using the template management console (`certtmpl.msc`).
* Granted `Enroll` and `Read` permissions for domain computers.
* Successfully issued, installed, and verified the computer certificate on workstation `WS01`.

4. Automation via Autoenrollment (GPO)
* Extended the computer template configuration to enable the **Autoenroll** permission.
* Configured Group Policy Object (GPO) settings via `gpmc.msc` (Certificate Services Client - Auto-Enrollment) within the Default Domain Policy.
* Implemented automatic certificate provisioning, updates, and renewals for domain workstations without user intervention.

---

🛠️ Key Verification Procedures

Verify Certificate Authority Health (`DC01`):
```cmd
certsrv.msc
