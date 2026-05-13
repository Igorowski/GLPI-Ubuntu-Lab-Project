# Password Reset Request

## Overview
This project simulates a real IT support incident handled in a GLPI environment.  
The scenario covers a password reset request in an Active Directory domain environment and demonstrates a full incident lifecycle from user report to resolution and verification.

---

## Scenario
A domain user is unable to access their account and requests a password reset due to repeated login failures and suspected credential issues.

---

## Environment
- Windows 10 client machines  
- Active Directory domain environment  
- Domain Controller (Windows Server)  
- GLPI ITSM ticketing system  

---

## User Report

User reported inability to log in and requested assistance with account access restoration.
<img width="901" height="211" alt="image" src="https://github.com/user-attachments/assets/bd4f876f-4eff-4181-85de-2f595725164e" />

---

## Ticket Assignment
Ticket assigned to IT Support technician for investigation and resolution.
</br>
<img width="472" height="87" alt="image" src="https://github.com/user-attachments/assets/eba1189c-575c-4b1d-b4b5-9712d2507085" />
</br>
<img width="584" height="137" alt="image" src="https://github.com/user-attachments/assets/b7e18e3e-63ba-48b4-8285-b496c834235e" />


---

## Initial Investigation
- Verified authentication failure on affected workstation  
- Checked user account status in Active Directory  
- Confirmed password-related login issue  
- Determined password reset requirement  

---

## Technician Actions
1. Located user account in Active Directory Users and Computers (ADUC)  
2. Initiated password reset procedure  
3. Enforced new password policy compliance  
4. Forced credential synchronization across domain environment  
5. Instructed user to authenticate using new credentials  

<img width="878" height="194" alt="image" src="https://github.com/user-attachments/assets/0b5d994a-8e44-45d5-884a-d23bddf59bfb" />

---

## Root Cause
User was unable to authenticate due to invalid or expired credentials requiring a password reset in Active Directory.

---

## Resolution
Password reset performed successfully via Active Directory Users and Computers (ADUC).  
User credentials updated and synchronized across the domain.

---

## Verification
User successfully logged into the workstation using new credentials after password reset.
<img width="621" height="168" alt="image" src="https://github.com/user-attachments/assets/fb87a472-b4bc-4b52-91ff-6e7dcb5f87a7" />

---

## Outcome
- Access restored successfully  
- Authentication functioning as expected  
- No further issues observed after verification  
<img width="628" height="124" alt="image" src="https://github.com/user-attachments/assets/e09d3615-d45f-44a4-b25e-8a606dec49ee" />


---

## Skills Demonstrated
- Active Directory user account management  
- Password reset procedures in domain environment  
- Authentication troubleshooting  
- ITSM / GLPI incident handling workflow  
- End-user support and verification process  
