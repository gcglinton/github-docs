# GitHub Account Management: User Monitoring and Integrity Procedures

## 1. Purpose
This document outlines the procedures for monitoring user accounts, roles, and activities within our GitHub organization. The primary goal is to ensure continuous monitoring of account activities to maintain security, integrity, and compliance with organizational policies.

## 2. Scope
These procedures apply to all users within our GitHub organization, including those with privileged access and external contributors. The focus is on monitoring account usage, managing team memberships and privileges, and responding effectively to incidents.

---

## 3. Monitoring and Integrity Compliance

### 3.1. Monitoring Account Usage and Team Management

GitHub Organization Owners, in collaboration with Repository Owners and Administrators, are responsible for overseeing account usage, particularly in relation to team management and the granting of privileges. Monitoring includes:

- **Team Membership and Privilege Management:** Continuous oversight is maintained on changes to team memberships and the assignment of privileges within the GitHub organization. This includes tracking who is added to or removed from teams and ensuring that privileges are granted appropriately based on the user’s role and responsibilities.

- **Privilege Escalation and Access Review:** Any changes in user privileges, such as granting admin access or modifying code owner permissions, are closely monitored. Notifications of these changes are automatically sent to designated Teams channels, ensuring that all privilege escalations are visible and can be reviewed promptly.

- **Logging and Notifications:** All activities related to team management, including changes in team membership, privilege assignments, and role modifications, are logged and monitored through Teams notifications. This approach ensures a real-time, comprehensive audit trail that can be easily reviewed by the relevant administrators.

- **Integrity Monitoring:** The integrity of team structures and privilege levels is continuously checked to detect and address any unauthorized or unintended modifications. This ensures that the principle of least privilege is upheld and that only authorized personnel have the necessary access.

### 3.2. Incident Response and Remediation

If an incident is detected, the organization admin, in partnership with the repository admin, will work together to initiate the incident management process. This process is escalated through the department's incident management plan to ensure a coordinated and effective response. The focus is on protecting the system's integrity and minimizing impact. After the incident, a detailed analysis is conducted to identify the root cause, and necessary enhancements to access controls and integrity safeguards are implemented. Lessons learned are integrated into ongoing account management practices to strengthen future incident response efforts.

---

## 4. Implementation

### 4.1. GitHub Account Configuration

To ensure the integrity and consistency of user identities, all GitHub accounts involved in the operation of FSDH and within the organization must be associated with a Government of Canada (GC) email address, preferably an SSC email address. This requirement ensures that all activities can be traced back to a verified organizational email account, reducing the risk of untrusted users and maintaining a secure chain of trust. While the GitHub identities themselves may not be owned by Shared Services Canada, they must be linked to a recognized GC email address.

**Example:**  
![image](https://github.com/user-attachments/assets/308169f0-62dd-4088-94d0-5b9127b9dd0a)

When inviting users to GitHub teams, the GC email address must be used.
![image](https://github.com/user-attachments/assets/a63c61a1-480b-441b-a7c2-88f33e1601f5)

This approach is similar to magic link authentication, where the email link serves as a method of verifying and granting access.

### 4.2. Setting Up GitHub Account Monitoring
![image](https://github.com/user-attachments/assets/d765b565-8c25-407f-a4ae-18f37a231b6b)

Webhooks are configured within GitHub to send notifications whenever specific events occur, such as changes in repository membership or branch settings. These webhooks trigger an HTTP POST request that includes detailed information about the event in JSON format.

### 4.3. JSON Request Structure

Here are parts of the webhook JSON payload with the event details highlighted:

![image](https://github.com/user-attachments/assets/8a389c94-71db-4b4f-827f-833e9fda305f)

![image](https://github.com/user-attachments/assets/e801499c-480d-4ebe-8043-08a3f027b434)

The JSON request sent by the webhook contains all relevant details about the event, including the type of change, the user involved, and the repository affected. This data is structured to be easily parsed and processed by the receiving service.

### 4.4. Teams Notifications

![image](https://github.com/user-attachments/assets/686a2206-b59c-4b4c-9eec-61fcc571573f)


Once the webhook sends the JSON request, it is received by an FSDH notification service that processes the data and sends a formatted notification to a designated Microsoft Teams channel. These notifications provide real-time alerts to GitHub Organization Owners and Repository Administrators, ensuring they are promptly informed of any significant changes.

---

## 5. Documentation and Continuous Improvement

All procedures related to user monitoring, integrity checks, logging, alerting, and incident response are thoroughly documented and made accessible to relevant stakeholders. Feedback from monitoring activities, incident responses, and regular audits is used to refine and enhance monitoring processes, ensuring the ongoing integrity of the codebase. Regular training sessions are conducted for GitHub Organization Owners and Repository Administrators to keep them informed of the latest monitoring and integrity procedures and best practices.

