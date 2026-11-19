# Ticket #002: Active Directory Offboarding Verification and Account Investigation

**Environment:** SysDesks IT Support Simulation  
**Category:** Identity and Access Management (IAM) / Active Directory  
**Status:** Investigation Completed — Further Audit Review Required

## 1. Issue

Fatima, an employee in the Customer Success department, submitted a support ticket requesting the deletion of Rosa Malone's Active Directory account because Rosa had reportedly left the company.

The request raised a potential security concern because former employees may retain unauthorized access to company resources if their accounts remain active.

Before making changes, I needed to verify the offboarding request and determine the account's current status.

<img width="1229" height="248" alt="Ticket#2 problem" src="https://github.com/user-attachments/assets/799c4417-a31b-4df6-a487-06072c065b7d" />

## 2. Investigation

I began by contacting the relevant personnel to verify whether Rosa Malone's departure and account removal had been authorized.

I contacted:

- **Customer Success Manager:** Could not confirm the offboarding authorization.
- **Customer Success Specialist / Ticket Requester:** Could not confirm whether the offboarding process had been approved.
- **Human Resources Representative:** Was unable to verify the departure because the employee was outside their area of responsibility.

After these conversations, I investigated Rosa Malone's account in Active Directory.

I searched the Customer Success organizational folder and performed a broader search across the entire Active Directory domain.

Both searches returned no matching account.

## 3. Root Cause

The requested Active Directory account could not be located.

This suggested that the account might already have been removed, but the investigation could not establish when the account disappeared or who performed the action.

The original account status and reason for its absence remained unverified.

## 4. Resolution

After confirming that Rosa Malone's account could not be found, I determined that no account deletion could be performed using the available directory interface.

I did not disable, modify, or delete any accounts.

The ticket requester subsequently asked who had removed the account.

I explained that identifying the responsible account would require reviewing the appropriate security audit logs.

The SysDesks simulation did not provide access to these logs, so I communicated the investigation's limitations and identified the need for further review by an authorized administrator or security team.

## 5. Verification

I confirmed the following:

- Rosa Malone's account did not appear in the Customer Success folder.
- A domain-wide Active Directory search returned no matching account.
- The contacted personnel could not confirm the offboarding authorization.
- Security audit logs were unavailable through the simulation's interface.
- No account modifications were performed during my investigation.

The account's deletion history and any remaining access to other company systems could not be verified.

**Final disposition:** Investigation completed within available permissions. Further audit review would be required to determine who removed the account.
<img width="1692" height="557" alt="Screenshot 2026-11-19 040806" src="https://github.com/user-attachments/assets/ad88f502-6b33-4c9c-8e55-5f1636a3cc36" />



## 6. Key Takeaway

This simulation demonstrated that identity and access management requires more than creating, disabling, or deleting user accounts.

I learned the importance of verifying authorization before making security-sensitive changes, communicating with relevant departments, and documenting investigative findings.

I also learned that Windows Security Event ID **4726** can help identify account deletion activity when appropriate auditing is enabled and the necessary logs are accessible.

Most importantly, I reinforced the principle that technicians should recognize the limits of their access and escalate unresolved security questions rather than make assumptions or unauthorized changes.
