# Section 02 - SOC Team Internals

Notes for alert triage, reporting, operational workflows, and SOC performance tracking.

## Rooms

- [x] SOC L1 Alert Triage
- [ ] SOC L1 Alert Reporting
- [ ] SOC Workbooks and Lookups
- [ ] SOC Metrics and Objectives
- [ ] Introduction to Phishing SOC Simulator Scenario

## Notes

- Add notes for each room as you complete it.

### SOC L1 Alert Triage

#### Learning Objectives

- Familiarise yourself with the concept of an alert.
- Explore alert fields, statuses, and classification.
- Learn how to perform alert triage as an L1 analyst.
- Practice with real alerts and workflows.
- Prepare for the simulator and SAL1 certification.

#### Prerequisites

- Understand common attacks on networks, Windows, and Linux. As an L1 analyst, you should be able to recognize the basic signs of suspicious activity across these environments so you can quickly decide whether an alert is benign, malicious, or needs escalation.
- On networks, focus on patterns such as port scans, brute-force login attempts, unusual outbound traffic, beaconing to external infrastructure, DNS abuse, and unexpected protocol usage between hosts.
- On Windows systems, be familiar with:
	- phishing-delivered malware
	- malicious PowerShell activity
	- suspicious services or scheduled tasks
	- credential dumping attempts
	- privilege escalation
	- lateral movement with remote administration tools
	- persistence through registry or startup changes
- On Linux systems, understand attacks such as:
	- SSH brute forcing
	- abuse of sudo or weak permissions
	- malicious cron jobs
	- web shell deployment
	- unauthorized user creation
	- persistence through startup scripts
	- suspicious command execution tied to crypto mining or remote access
- The goal is not deep incident response at this stage, but enough baseline knowledge to read alerts in context, spot common attacker behaviour, and ask the right escalation questions.
- Know SOC roles and duties, especially those of L1 analysts.

#### Dashboard

You were granted access to the dashboard in the TryHackMe room, and you will need it to complete most of the tasks. Open the attached website in a separate window, familiarise yourself with it, and then move on to the next task.

![TryHackMe SIEM dashboard](images/TryHackMe-SIEM-dashboard.png)