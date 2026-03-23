# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.

## DESIGN STEPS:
### Step 1:
Launch Wireshark and start capturing traffic on the appropriate network interface.

### Step 2:
Use filters like http, dns, or tcp.port == 80 to monitor web browser artifacts such as visited URLs, cookies, and user-agent strings.

### Step 3:
Apply filters like smtp, pop, or imap to locate and analyze email header details (e.g., sender, receiver, subject) from email communications.

## PROGRAM:
Wireshark Web and Email Traffic Filtering Steps

## OUTPUT:
**A. Capturing Traffic in Wireshark**

1. Open Wireshark and start capturing on the active interface (Wi-
Fi/Ethernet).

2. Perform activities like opening a website or sending an email through a
client (e.g., Gmail via browser or Thunderbird).
3. Stop the capture once done.

![image](https://github.com/user-attachments/assets/04f9e42a-15ca-4cc2-a81c-97b889bb176b)

**Analyze DNS Queries:**
o Filter: dns

o Reveal domains the browser tried to resolve.

![image](https://github.com/user-attachments/assets/eb10207d-d377-448d-beef-9985f73ae7ff)

**Email Header Analysis**

1. Apply relevant filters:
2. 
o For POP3: tcp.port == 110

o For SMTP: tcp.port == 25 or 587

o For IMAP: tcp.port == 143 or 993

4. Locate email data:
5. 
o Look for SMTP packets to see sender/receiver email addresses.

o Use "Follow TCP Stream" to view the full email headers and body if unencrypted.

**Extract Email Header Fields:**

o Analyze From, To, Subject, Date, Message-ID, and relay servers used in sending the email.

![Screenshot 2025-04-21 223935](https://github.com/user-attachments/assets/0bd101fe-2793-4eb1-b064-3ccaffd3ee3d)

![Screenshot 2025-04-21 224213](https://github.com/user-attachments/assets/37843833-560e-4dfa-ad86-8f3a4d0f53b2)

![Screenshot 2025-04-21 224344](https://github.com/user-attachments/assets/32698667-c3a1-4720-a813-56f94cf3da69)

## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark
