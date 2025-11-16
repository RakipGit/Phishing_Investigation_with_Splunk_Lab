![Status](https://img.shields.io/badge/status-complete-brightgreen)

## Phishing Investigation with Splunk 🕵️‍♂️
A hands-on lab simulation on TryHackMe platform,analyzing phishing alerts,investigating suspicious emails and determining true or false positives with case reports for each one of them to secure the system environment.

---

## 💡 Project Summary
I completed a phishing investigation using TryHackMe's Phishing Unfolding simulation room.I analyzed phishing alerts using Splunk,determined whether incidents were true or false positives and documented findings in clear case reports.This lab reinforced my skills for identifying,investigating and responding to phishing attacks.

---
## ✅ What I Did
- Reviewed alerts in a SOC simulation dashboard (5 total: 1 high-severity firewall alert,4 medium-severity phishing alerts).  
- Investigated a high sevirity firewall alert to confirm blocked malicious activity and documented my findings.  
- Analyzed phishing emails,checking sender domains,URLs,malicious links and recipient activity via Splunk logs.  
- Classified alerts as True Positive or False Positive based on investigation results.  
- Created case reports with detailed evidence,reasoning my True/False positives and recommended remediation actions.  
- Proposed security procedures such as blocking malicious domains(firewall rules) and educating employees on phishing risks.

---

## 📸 Screenshots

Credits:Cyber Press
![Start](images/more/cyberpress.jpg)


<details>
<summary>🔎 View Full Lab Walkthrough (Screenshots)</summary>

1)SOC Dashboard with the alerts I have to handle.
![Dashboard](images/more/Dashboard.png)

2)Taking ownership of my first alert (firewall) that has the highest sevirty score out of all the alerts.
  This alert indicated that a user attempted to access a specific URL,but the connection was blocked.In most cases,this happens because the firewall already has rules in place to prevent access to known malicious or         suspicious domains.
![Ownership](images/1alert/Alert1.png)

3)I wanted to dive into this alert using Splunk to see if there was any other activity related to that specific URL or the source host.Using this query: index=* 10.20.2.17 OR "http://bit.ly/3sHkX3da12340" ,that basically    shows all the events related to the source IP and the suspicious shortened (bit.ly) URL.
  From the Splunk results I found that the firewall successfully blocked the malicious URL, and the attempt was isolated meaning no other hosts accessed it, and no further suspicious activity was observed.
![Alert1Splunk](images/1alert/Alert1Splunk.png)

4)With this information in my hands I was ready to write my case report:
  The alert is a True positive because the system was at risk but the firewall successfully blocked the malicious URL.Even though no compromise occurred the incident should be documented and reviewed for awareness so the    organization informs the employee that he attempted to access a blocked URL and remind him about the security measures he should follow.
  Lastly,no escalation is required for this alert, as the firewall successfully prevented any compromise, and the incident was contained to a single user attempt.
![Alert1Report](images/1alert/Alert1Report.png)

5)Next,it was time to move on to the phishing alerts. The first one involved an email that was flagged because it contained a external link.
  In this case we can see the sender that looks legitimate as a HR member of THM platform (onboarding@hrconnex.thm) sending the recipient (j.garcia@thetrydaily.thm) an email so he can complete he THM email.
![Alert2](images/2alert/Alert2.png)

6)To investigate, I ran a query in Splunk("j.garcia(@)thetrydaily.thm")to determine how many emails were sent and discovered that two identical emails with the same link were sent within a 15-minute gap.
  Next,I checked whether the recipient clicked on the link.The events show that the recipient did not click the link.
![Alert2Splunk](images/2alert/Alert2Splunk.png)

7)Based on the investigation,both the URL and the sender domain appear legitimate and are not flagged in any threat intelligence sources that I searched online.Therefore,I decided to classify this alert as a False postive.
![Alert2Report](images/2alert/Alert2Report.png)


)Results
![Result1](images/more/Results.png)
![Result2](images/more/Results2.png)



</details>



---

## 🛠️ Tools & Technologies
- Splunk:for log analysis and alert investigation  
- SOC Simulator dashboard for alerts and severity levels
   
---

## 🧠 Insights & Lessons Learned

- Practiced investigating phishing emails in a real-world simulation.  
- Reinforced my knowledge on using Splunk to query for IPs,URLs and other useful events that helped me unsterstand more about my alerts.  
- Gained more experience in classifying alerts as True Positive or False Positive with detailed documenting findings and creating case reports for to help my .  
- Gained a better understanding of proactive defenses:need of blocking malicious domains,educating users and responding quickly to alerts based of coruse on their sevirty level.

---

## 🔒 Copyright Notice
All content and visuals in this repository are original and may not be reused without permission.

---

## 🙋‍♂️ Rakip
Cyber Security Professional

---

