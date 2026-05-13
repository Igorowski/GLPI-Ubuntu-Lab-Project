# Account Lockout

## Scenario
User reports being unable to log into their account after multiple failed login attempts.

## User Report
<img width="908" height="245" alt="image" src="https://github.com/user-attachments/assets/0bdd9960-2621-4dcd-b4a2-bdf9288d925a" />

## Ticket Assignment
<img width="1259" height="50" alt="image" src="https://github.com/user-attachments/assets/697226a8-6189-4b5b-bb37-9a2451125208" />


## Environment
- Windows 10 client
- Active Directory domain
- GLPI ticketing environment

## Initial Symptoms
- Verified login failure on affected workstation
- Checked account status in Active Directory Users and Computers (ADUC)
- Confirmed account lockout triggered by security policy

## Technician Actions
1. Reviewed AD account status (locked state confirmed)
2. Performed account unlock in ADUC
3. Forced credential refresh on domain controller
4. Instructed user to retry authentication

## Root Cause
Account lockout policy triggered after repeated failed login attempts.

## Resolution
User account unlocked through Active Directory Users and Computers.
<img width="601" height="139" alt="image" src="https://github.com/user-attachments/assets/d9639377-03fd-401c-99e3-f4f6053fc164" />


## Verification
User successfully logged into workstation using correct credentials.
<img width="612" height="151" alt="image" src="https://github.com/user-attachments/assets/01dff761-7214-4e4e-b918-f97244faeee7" />

## Outcome
- Access restored
- No further issues observed after verification

<img width="622" height="133" alt="image" src="https://github.com/user-attachments/assets/fee8df87-0c84-4bd6-9e29-92b63c974d9e" />
</br>
<img width="275" height="42" alt="image" src="https://github.com/user-attachments/assets/d1079284-7ff9-4733-8e75-5ea3c4107dd3" />


## Skills Demonstrated
- Active Directory administration
- User account management
- Authentication troubleshooting
- IT support workflow
