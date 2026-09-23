# Windows-Event-Log-Investigation
Windows failed login investigation using Event Viewer and Security Event ID 4625 to analyze authentication failures, source information and suspicious login patterns. 

<h2>Environemnt</h2>
<p align="center">
OS: Windows 10 (VirtualBox VM)
<p align="center">
Tool: Event Viewer (eventvwr.msc)
<p align="center">
Log Source: Security Log

<h2>Program Walk-Through</h2>
<p align="center">
Launch Event Viewer:
<br/>
Open Event Viewer to begin searching for failed logon events.
<br/>
<img width="450" height="244" alt="eventvwr msc " src="https://github.com/user-attachments/assets/afe18348-ddb6-4405-b21b-3080cd5fa73f" />
<p align="center">
Filter Current Log 4625
<br/>
Filtering the Security log by Event ID 4625 to isolate failed logon attempts.
<br/>
<img width="548" height="554" alt="Code 4625 to Filter Failed Logins" src="https://github.com/user-attachments/assets/170f902a-3bab-44cd-8005-4dea7354c022" />

<p align="center">
Filtered 4625 Results
<br/>
Filtered Security log shows 6 failed logon events. 
<br/>
<img width="1016" height="765" alt="4625 Failed Results" src="https://github.com/user-attachments/assets/1e0a531b-45f8-4b84-bf99-1bafcc7b3e54" />

<p align="center">
Failed Logon Details 
<br/>
Detailed view of Event 4625 showing the targeted account, failure reason, and confirmation of failed logon attempt.
<br/>
<img width="624" height="713" alt="Information of a Failed 4625" src="https://github.com/user-attachments/assets/2e51e352-f42f-423a-8d80-a053b4cdbf3c" />

<h2>Findings</h2>
Event ID 4625 identified a failed login attempt for the account "vboxuser." The reason for failure was an unknown username or bad password. The source address was 127.0.0.1 (loopback IP) indicating the failure originated within the local system. Based on this one event, there is no evidence of an external login attempt. Additional 4625 events need to be reviewed to determine if this event is an isolated or a repeated pattern.
