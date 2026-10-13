# LetsDefend-Phishing-Email-Analysis-Suspicious-Task-Scheduler

## Phishing Email Analysis

### Practice with SOC Alert

### SOC140 - Phishing Mail Detected - Suspicious Task Scheduler

---

<img width="1916" height="599" alt="image" src="https://github.com/user-attachments/assets/fe25d118-2f45-4e6c-909d-bf1f3ba10c9e" />
Here is My assigned Ticket, seating in my Investigation Channel; ready to be investigated

---

* Click Details to view more information about the Ticket.

<img width="1892" height="701" alt="image" src="https://github.com/user-attachments/assets/5556db97-4989-45a2-9911-ae709b0c3e46" />

* Click >> Create Ticket to Create ticket for EventID: 82

<img width="1913" height="571" alt="image" src="https://github.com/user-attachments/assets/824e494d-99d1-44f9-b621-615eecd57be2" />

* Click the blue Continue button to create a ticket

* Click OK when the window pops up “Ticket Created” indicating my “The ticket has been created successfully.”

<img width="1912" height="652" alt="image" src="https://github.com/user-attachments/assets/832e86fd-d77f-4f50-8737-2eae9d9537db" />
<img width="721" height="485" alt="image" src="https://github.com/user-attachments/assets/138a9431-f797-4051-a200-58e548297bcd" />

---

Play Book Opens
(Which is used to begin the guided incident response investigation for this specific SOC140 - Phishing Mail Detected - Suspicious Task Scheduler alert.)

<img width="1904" height="593" alt="image" src="https://github.com/user-attachments/assets/d4819662-4915-4867-9eb4-34834ff20e7b" />

This screen highlights a critical security alert:

• Incident Name: SOC140 - Phishing Mail Detected - Suspicious Task Scheduler

• Incident Type: Exchange

• Created Date: 2026-10-13 11:54:52

The dashboard indicates that I am currently navigating within the Case Management section (highlighted on the left panel).

* Click blue **Start Playbook!** button.

---

<img width="904" height="475" alt="image" src="https://github.com/user-attachments/assets/5000e88e-9d6a-4c12-843c-77fd71aba053" />
<img width="1180" height="419" alt="image" src="https://github.com/user-attachments/assets/af44afb7-7494-4966-8a02-2559e73f3361" />


* When was it sent:                    21st March, 2021  12:26:57 PM

* What is the email's SMTP address:    189.162.189.159

* What is the sender address:          aaronluo@cmail.carleton.ca

* What is the recipient address:       mark@letsdefend.io

* Click Email Security
* Type Sender address ```189.162.189.159``` filter, to view the email details.

<img width="1893" height="618" alt="image" src="https://github.com/user-attachments/assets/44eeed4b-7240-42f0-b891-2ec242cd99a9" />
<img width="1908" height="713" alt="image" src="https://github.com/user-attachments/assets/fb12681e-2425-431e-a117-30b800da77f0" />

* Is the mail content suspicious: **Yes**

* Are there any attachment: **Yes**

File Name: 72c812cf21909a48eb9cceb9e04b865d

Password: infected

---

* Click **Yes**

* <img width="985" height="460" alt="image" src="https://github.com/user-attachments/assets/4a5dc814-f8f8-457f-a8d4-7fd83ab9a1aa" />

---

<img width="855" height="510" alt="image" src="https://github.com/user-attachments/assets/a455171f-cf2a-4608-88b1-608310fabd4c" />
<img width="1842" height="837" alt="image" src="https://github.com/user-attachments/assets/c87a6ca4-3426-43a7-8e4f-d50766bd5e11" />

Based on the threat intelligence Analysis, the file is Malicious. 
* Click Malicious button.

### Summary of the Evidence

• High Detection Rate: 30 out of 62 security vendors flagged the PDF file (Material.pdf) as malicious.

• Threat Classification: It is labeled explicitly under the threat categories of ```trojan, downloader,``` and ```phishing```, with specific classifications like ```Trojan/PDF.Generic``` and ```Trojan[downloader]:PDF/Phish.Gen```.

• Behavioral Red Flags: The file exhibits several highly suspicious behaviors, including direct-cpu-clock-access, detect-debug-environment, long-sleeps, and intentional text obfuscation meant to bypass automated security scanners.

• Contextual Phishing Lure: Code insights show the PDF masquerades as a high-value purchase order designed to act as a Business Email Compromise (BEC) or phishing lure.

---

* Clicked Not Delivered

<img width="985" height="319" alt="image" src="https://github.com/user-attachments/assets/183ebbdf-0291-4c37-b94b-be4e7716fd0c" />

* Device Action: **Blocked**
<img width="1118" height="587" alt="image" src="https://github.com/user-attachments/assets/a14398ef-0ddc-4429-87cc-1454f3658ab4" />

---

### Let's Add Artifacts

• Artifact 1 (Malicious File MD5 / Hash)
	
	• Value: 39fb27c32221134a423760c5d1f58bca4cbbcc87c891c79e20b0a22b63608eb4
	
	• Type: Select Hash (or SHA256) from the dropdown.
	
	• Comment: Malicious attachment (Material.pdf) associated with Phishing/BEC lure.

• Artifact 2 (Attacker IP Address)
	
	• Value: 189.162.189.159
	
	• Type: Select IP (or IPv4 Address) from the dropdown.
	
	• Comment: Source SMTP IP address used to send the phishing email.

• Artifact 3 (Sender Email Address)
	
	• Value: aaronluo@cmail.carleton.ca
	
	• Type: Select Email (or Mail) from the dropdown.
	
	• Comment: Compromised or malicious sender address.

<img width="873" height="533" alt="image" src="https://github.com/user-attachments/assets/a769374d-1754-426b-b383-4ba9a61f96e2" />

---

### Analyst Note:

```
On investigation of Alert SOC172, a phishing email detection was verified. The email was sent from the external address aaronluo@cmail.carleton.ca via the source IP 189.162.189.159, targeting the internal recipient mark@letsdefend.io. The email contained a malicious PDF attachment masquerading as a purchase order.

Investigation & Analysis

• Attachment Verification: The attached file, Material.pdf, was analyzed using sandbox technology and threat intelligence databases.
• Malicious Verdict: The file returned a high detection rate of 30/62 security vendors, identifying it as a Trojan Downloader / Phishing Lure designed for Business Email Compromise (BEC).
• Behavioral Red Flags: Sandbox analysis confirmed evasion techniques, including long-sleep timers, execution environment debugging, and text obfuscation to bypass automated detection gateways.


Impact Assessment & Mitigations

• Delivery Status: According to the email gateway logs, the initial Device Action was marked as Blocked.
• Host Telemetry: Endpoint detection logs confirm that the file did not execute on the destination host, resulting in a successful containment with no indicators of active compromise on the internal network.

Indicators of Compromise (IoCs)

• Sender Address: aaronluo@cmail.carleton.ca
• Source IP: 189.162.189.159
• File Name: Material.pdf
• File Hash (SHA256): 39fb27c32221134a423760c5d1f58bca4cbbcc87c891c79e20b0a22b63608eb4

Conclusion

The alert has been verified as a True Positive. Due to automated blocking at the gateway level, no further remediation or device isolation is required for the recipient host. The case is recommended for closure.
```

<img width="996" height="481" alt="image" src="https://github.com/user-attachments/assets/10bea163-def3-41e6-8dfa-623ee04cb20c" />

---

### Click Confirm & Close

* Select **True Positive**

* To officially submit and close out this case (Ticket)

<img width="976" height="408" alt="image" src="https://github.com/user-attachments/assets/45ee483d-d71a-4d69-a390-1bed58475073" />

---

### Final Result

<img width="1899" height="830" alt="image" src="https://github.com/user-attachments/assets/85af7ebd-bb1c-4dc6-a994-72db052e9b57" />

---
