# Azure-Cloud-Security-Labs
# Lab 1: Corporate User Lifecycle & Access Control Management (Microsoft Entra ID)

## 🏢 Real-World Scenario
In this lab, I simulated a real-world enterprise scenario working as an **Identity & Access Management (IAM) Administrator** at an organization. 
* **The Situation:** A new employee, **Sara Ahmed**, has joined the company as a Cloud Support Engineer. 
* **The Business Challenge:** As per corporate security compliance, new hires cannot be granted administrative privileges straight away. We must follow the **Principle of Least Privilege** (giving only the minimum necessary access).
* **The Objective:** Provision a secure corporate identity, organize the user into a role-based security group, and assign granular, read-only cloud visibility permissions to the team rather than individual accounts.

---

## 🛠️ Step-by-Step Implementation

### Step 1: User Provisioning
Created a dedicated corporate identity in Microsoft Entra ID for the new employee.
* **User Principal Name (UPN):** `sara.ahmed@<your-domain>.onmicrosoft.com`
* **Display Name:** `Sara Ahmed`
* **Action:** Created user via Azure Portal -> Microsoft Entra ID -> Users -> New User.

### Step 2: Role-Based Group Management
Instead of managing permissions individually, implemented security groups for scalable access control.
* **Group Type:** Security Group
* **Group Name:** `Cloud-Support-Team`
* **Member Added:** `Sara Ahmed`
* **Action:** Configured via Microsoft Entra ID -> Groups -> New Group.

### Step 3: Granular Access Control (RBAC Assignment)
Assigned restricted visibility permissions to the security group at the Azure Subscription level.
* **Role Assigned:** `Reader` (Allows viewing of cloud resources without modification rights).
* **Target Scope:** Azure Subscription IAM (Identity and Access Management).
* **Action:** Subscriptions -> Access Control (IAM) -> Add role assignment -> Selected `Reader` role -> Assigned to `Cloud-Support-Team`.

---

## 🔒 Security Best Practices Implemented
1. **Principle of Least Privilege (PoLP):** Granted the `Reader` role instead of Owner or Contributor to prevent accidental infrastructure changes.
2. **Group-Based Access Control (GBAC):** Utilized Security Groups instead of direct user assignment, making offboarding and scaling seamless.
3. **Audit Readiness:** Every user identity is tracked uniquely via Microsoft Entra ID for proper logging and accountability.

---

<img width="1365" height="682" alt="Screenshot 2026-10-13 112126" src="https://github.com/user-attachments/assets/689c8294-325c-4b27-9bb7-38efc7fbf8cc" />
<img width="1365" height="675" alt="Screenshot 2026-10-13 112227" src="https://github.com/user-attachments/assets/301c3205-2c5e-48c7-bcc2-a4f8b1d6446e" />
<img width="1365" height="679" alt="Screenshot 2026-10-13 112242" src="https://github.com/user-attachments/assets/22954322-1b03-44f8-9cbb-8af2f93e7b2f" />
<img width="1365" height="673" alt="Screenshot 2026-10-13 112304" src="https://github.com/user-attachments/assets/2fb288c8-5940-4c4a-beaf-ec48637b2e82" />

# Lab 2: Enforcing Multi-Factor Authentication (MFA) & Access Security (Microsoft Entra ID)

## 🏢 Real-World Scenario
In this lab, I acted as a Cybersecurity Administrator to mitigate credential theft and unauthorized access risks at the organization. 
* **The Security Threat:** Standard username/password authentication is vulnerable to phishing and brute-force attacks.
* **The Objective:** Implement Multi-Factor Authentication (MFA) across the cloud directory to enforce a zero-trust security posture and comply with modern identity protection standards.

---

## 🛠️ Implementation Steps
1. **Accessed Microsoft Entra ID Tenant:** Navigated to the directory overview via Azure Portal.
2. **Evaluated Security Settings:** Inspected identity protection configurations and security defaults.
3. **Enforced MFA (Security Defaults / Conditional Access):** 
   - Enabled **Security Defaults** to mandate Microsoft Authenticator app verification for all administrative and standard user accounts.
   - Configured baseline rules ensuring secondary verification challenges on non-standard login attempts.

---

## 🔒 Security Best Practices Implemented
* **Zero Trust Model:** Shifted from "trust but verify" to "never trust, always verify" by mandating multi-factor proof of identity.
* **Mitigating Credential Theft:** Minimized the impact of leaked or compromised passwords through second-factor validation (MFA).

  <img width="1365" height="679" alt="Screenshot 2026-10-13 113318" src="https://github.com/user-attachments/assets/164bd82c-6a73-40ae-882f-409b0ac37e0d" />

# Lab 3: Security Monitoring & Audit Logging in Microsoft Entra ID

## 🏢 Real-World Scenario
In this lab, I acted as a Security Operations Center (SOC) Analyst to investigate user authentication activities and administrative actions. 
* **The Security Need:** Monitoring access patterns to detect potential brute-force attacks, unauthorized sign-in attempts, and tracking administrative changes within the cloud directory.
* **The Objective:** Utilize Microsoft Entra ID monitoring tools (Sign-in logs and Audit logs) to review authentication statuses, IP origins, and tenant configuration changes.

---

## 🛠️ Implementation Steps
1. **Accessed Sign-In Logs:** Navigated to Microsoft Entra ID -> Monitoring -> Sign-in logs to track user authentication events.
2. **Analyzed Authentication Details:** Inspected individual sign-in sessions for success/failure status, client app usage, and geographical location data.
3. **Reviewed Audit Logs:** Checked administrative action logs (Microsoft Entra ID -> Monitoring -> Audit logs) to verify changes made during previous labs (such as user provisioning and security defaults enforcement).

---

## 🔒 Security Best Practices Implemented
* **Continuous Monitoring:** Regularly reviewing sign-in logs to spot anomalous behaviors or compromised credentials early.
* **Audit Trail Maintenance:** Maintaining immutable logs of administrative actions for compliance and incident forensics.

  <img width="1365" height="679" alt="Screenshot 2026-10-13 113318" src="https://github.com/user-attachments/assets/cad58739-6260-4e76-a67c-a46e1f9714b2" />
<img width="1365" height="675" alt="Screenshot 2026-10-13 115221" src="https://github.com/user-attachments/assets/d936104a-1ac7-4dc2-9e4b-5a1b233bcf0b" />
