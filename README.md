# N0aziXss CerberusX 🍓
# N0aziXss CerberusX Tool 🔍 

## 🌟 Introduction
**N0aziXss CerberusX** is an ethical XSS scanner designed for security professionals to detect vulnerabilities in web applications.  

## Features ✨
- ✅ Multi-Type XSS Detection (Reflected, Stored, DOM-Based)
- 🕷️ Auto-Crawling for URL discovery
- 🔄 Advanced Payloads with WAF bypass techniques
- 📊 JSON Logging with rotation
- ⚡ Fast Scanning with concurrent requests

```bash
git clone https://github.com/NazaninNazari/CerberusX.git 
cd CerberusX-tools  
pip install -r requirements.txt

# install dependencies
pip install -r requirements.txt

# run the scanner
python cerberusX.py

# Usage Example:
1.basic command
```bash
python cerberusX.py -t https://example.com

2.advanced command with all features
```bash
python cerberusX.py -t https://example.com \
    --advanced \
    --strict-ssl \
    --proxy http://localhost:8080 \
    --delay 0.5 \
    --max-pages 100

3.maximum pages to crawl
```bash
python cerberusX.py -t https://example.com --max-pages 100

4.specific path only
```bash
python cerberusX.py -t https://example.com/api/v1 \
    --no-crawl

5.output control
```bash
# Proxy server 
python cerberusX.py -t https://example.com --proxy http://proxy.example.com:8080

# Enable advanced methods (PUT, DELETE)
python cerberusX.py -t https://example.com --advanced

# Delay between requests (seconds)
python cerberusX.py -t https://example.com --delay 0.5

# Sample Output
♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*
🍓 Professional XSS Scanner - Ethical Use Only 🍓
⚠️ Warning: Always get proper authorization before scanning
♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*♦*

[+] Target: https://example.com
[+] Scan started at: 2023-11-15 14:30:45
[+] Using 15 threads
[+] Strict SSL: Disabled
[+] Advanced mode: Enabled

[Phase 1] Crawling website...
• Found: https://example.com/
• Found: https://example.com/login
• Found: https://example.com/search
• Found: https://example.com/contact
[✓] Crawled 12 pages in 8.2 seconds

[Phase 2] Checking subdomains...
• Found: admin.example.com
• Found: api.example.com
[✓] Discovered 3 subdomains

[Phase 3] Scanning for XSS vulnerabilities...
• Testing: https://example.com/search?q=<payload>
• Testing: https://example.com/login?username=<payload>
• Testing: https://admin.example.com/dashboard?id=<payload>

[!] Vulnerabilities Found:
1. [Reflected XSS] GET https://example.com/search?q=<svg/onload=alert(1)>
   • Payload: <svg/onload=alert(1)>
   • Confidence: High
   • Parameters: q
   • Response Code: 200

2. [DOM-Based XSS] GET https://example.com/dashboard#javascript:alert(1)
   • Payload: javascript:alert(1)
   • Source: location.hash
   • Confidence: Medium

3. [Stored XSS] POST https://example.com/comments
   • Payload: <img src=x onerror=alert(1)>
   • Stored in: Database
   • Confidence: High

[✓] Scan completed in 1 minute 22 seconds
[+] Total vulnerabilities found: 3
[+] Results saved to: scan_results_20231115_143207.json