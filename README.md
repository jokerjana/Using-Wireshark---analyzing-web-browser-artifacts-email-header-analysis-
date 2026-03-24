
# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information

## SENDING AN EMAIL
<img width="1383" height="433" alt="Screenshot 2026-03-24 112749" src="https://github.com/user-attachments/assets/ef5c99e0-7e09-4de2-9fdb-9d8f0e441718" />

## FILTER FOR DNS
<img width="1836" height="715" alt="Screenshot 2026-03-24 112558" src="https://github.com/user-attachments/assets/b0eb0f7c-1e6c-4e17-94b3-26de0001e964" />

## FILTER FOR HTTP
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c9c1284d-7a7a-48ba-a540-2cd627e1f87d" />

## FILTER FOR TCP 
<img width="1909" height="875" alt="Screenshot 2026-03-24 112722" src="https://github.com/user-attachments/assets/7ef4b28c-f1c1-4cea-9c9b-8668bfead150" />


## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.


