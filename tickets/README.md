
# Ticketing Workflow

This section demonstrates the operational side of the GLPI environment by simulating a real-world IT Service Desk workflow.  
The process covers ticket creation, lifecycle management, user-side issue reporting, and administrator troubleshooting activities.

---

# Ticket Creation

A ticket is created by an end user to report an issue or request technical support.

### Example Scenario
- A user is unable to log into a domain account

### Ticket Submission Process

- Access the GLPI user portal
- Select **"Create Ticket"**

<img width="224" height="120" alt="image" src="https://github.com/user-attachments/assets/4f138a72-51fc-4c2b-a565-83699c687249" />

- Complete the ticket form:
  - Title
  - Description
  - Category
  - Priority level

<img width="1581" height="778" alt="image" src="https://github.com/user-attachments/assets/d76a1d2f-0f91-4016-a570-609969e3afc4" />

The ticket is then submitted to the IT support team for processing.

---

# Ticket Lifecycle

Once the ticket has been created, administrators and technicians can manage it from the GLPI ticket panel.

<img width="1653" height="223" alt="image" src="https://github.com/user-attachments/assets/daf7086b-d356-4c9c-8d78-f88b9ed6cdb5" />

GLPI uses a structured workflow to track the status of support requests:

```text
New → Processing (assigned) → Processing (planned) → Pending → Solved → Closed
````

### Status Overview

#### New

The ticket has been submitted but has not yet been assigned to a technician.

<img width="393" height="287" alt="image" src="https://github.com/user-attachments/assets/daf91dfb-f8b3-4699-b306-07cb5b126133" />

---

#### Processing (assigned)

A technician has been assigned and is actively investigating the issue.

<img width="402" height="58" alt="image" src="https://github.com/user-attachments/assets/40a3fc58-a7d3-4c72-9498-6f0187ad7e60" />

---

#### Processing (planned)

Work has been scheduled for a later time, such as a maintenance window or planned intervention.

<img width="397" height="58" alt="image" src="https://github.com/user-attachments/assets/378c0703-caaa-43dd-952d-8992bb446834" />

---

#### Pending

The ticket is temporarily on hold while waiting for:

* User feedback
* Vendor response
* Additional information
* Required hardware or software

<img width="394" height="60" alt="image" src="https://github.com/user-attachments/assets/54d30cac-ffff-42ee-b9aa-eb911de75dc3" />

---

#### Solved

The technician has resolved the issue and documented the solution.

<img width="440" height="84" alt="image" src="https://github.com/user-attachments/assets/4b7dfc53-e5e7-4792-93a7-557f803c4cc1" />

---

#### Closed

The ticket has been confirmed as resolved and formally closed.

<img width="322" height="65" alt="image" src="https://github.com/user-attachments/assets/480ff736-4245-46b1-a757-0d4096e1af2f" />

---

# User Simulation

This lab simulates a realistic end-user support scenario.

### Example Incident

* A domain user experiences a login failure caused by incorrect credentials or account lockout.

### User Actions

#### Login Attempt

<img width="601" height="510" alt="image" src="https://github.com/user-attachments/assets/3288ff47-4daf-413c-871d-adacadf4ed61" />

---

#### Error Message Received

<img width="686" height="436" alt="image" src="https://github.com/user-attachments/assets/ef207008-f27a-4e15-82cf-aaf4461ef418" />

---

#### Support Ticket Submission

The user submits a support request through another active session or test account.

<img width="578" height="208" alt="image" src="https://github.com/user-attachments/assets/45416ca8-52e2-479e-8482-94bc8de95497" />

This simulates a realistic interaction between an end user and an IT support team.

---

# Admin Workflow

The administrator or technician manages incoming tickets from the GLPI administration interface.

Typical support actions include:

---

### Reviewing Ticket Details

<img width="1133" height="50" alt="image" src="https://github.com/user-attachments/assets/47ee6c58-ceaa-4820-bc5b-e206b6e37be9" />

---

### Assigning Priority

<img width="424" height="275" alt="image" src="https://github.com/user-attachments/assets/bcd4049a-91ff-48a8-9274-cda0394754c5" />

---

### Assigning Technician

<img width="278" height="226" alt="image" src="https://github.com/user-attachments/assets/89892d25-1cc6-45bb-a0cb-9e947cbbf3f2" />

---

### Investigating the Issue

The technician verifies the account status in Active Directory Users and Computers (ADUC).

<img width="409" height="531" alt="image" src="https://github.com/user-attachments/assets/b5325de5-715b-4806-b0e7-0d84eec13f97" />

---

### Providing Resolution Notes

<img width="909" height="201" alt="image" src="https://github.com/user-attachments/assets/cb2d485e-1eca-4415-aab9-dce0e5259868" />

---

### Updating Ticket Status

<img width="565" height="53" alt="image" src="https://github.com/user-attachments/assets/fe8e808a-89ca-41eb-8375-02d639604733" />

---

### Closing the Ticket

The ticket is closed after successful issue resolution and confirmation.

---

# Summary

This workflow demonstrates a complete IT Service Desk cycle using GLPI:

* End-user issue reporting
* Ticket generation and classification
* Structured ticket lifecycle management
* Administrative troubleshooting and resolution
* Active Directory account investigation
* Technician assignment and workflow handling

The environment simulates real-world IT support operations commonly used in enterprise environments.

