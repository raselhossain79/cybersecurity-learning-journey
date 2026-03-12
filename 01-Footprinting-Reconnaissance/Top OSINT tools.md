# 🔍 OSINT Tools

> A collection of Open Source Intelligence (OSINT) tools explored during internship. This README covers each tool's purpose, installation, and basic usage.

---

## 📋 Table of Contents

- [Holehe](#-holehe)
- [Sherlock](#-sherlock)
- [Maltego + Social Links CE](#-maltego--social-links-ce)
- [SpiderFoot](#-spiderfoot)
- [Have I Been Pwned](#-have-i-been-pwned)

---

## 📧 Holehe

### What it does
Checks if an email address is registered on major platforms (Twitter, Instagram, GitHub, etc.) without sending any email to the target. Useful for account discovery in OSINT investigations.

### Installation
```bash
pip3 install holehe --break-system-packages
```

### How to Use
```bash
# Basic usage
holehe target@email.com

# Save output to a file
holehe target@email.com > results.txt
```

**Sample Output:**
```
[+] twitter.com        - Email registered
[+] instagram.com      - Email registered
[-] github.com         - Email not registered
```

---

## 👤 Sherlock

### What it does
Searches for a username across 300+ social media platforms simultaneously. Useful for tracking a person's online presence across the internet.

### Installation
```bash
sudo apt install sherlock
```

**Alternative (via pip):**
```bash
pip3 install sherlock-project --break-system-packages
```

### How to Use
```bash
# Search for a username
sherlock username

# Search multiple usernames
sherlock user1 user2 user3

# Save results to a file
sherlock username --output results.txt

# Search with timeout settings
sherlock username --timeout 10
```

**Sample Output:**
```
[+] Facebook: https://www.facebook.com/username
[+] Twitter: https://twitter.com/username
[-] Snapchat: Not Found
```

---

## 🕸️ Maltego + Social Links CE

### What it does
Maltego is an advanced link analysis and data correlation platform. It visually maps relationships between people, domains, emails, companies, and more. **Social Links CE** extends it with social media intelligence transforms.

### Installation

#### Maltego
Available in Kali Linux by default:
```bash
# Search from Kali applications menu → Maltego
# Or launch from terminal:
maltego
```
> On first launch, create a free account at [maltego.com](https://www.maltego.com) and log in.

#### Social Links CE (Step-by-Step)

1. **Open Maltego**
2. **Go to Transform Hub**
   - Click on **Maltego Data Hub** → Search
3. **Search for:** `Social Links`
4. **Install Social Links CE**
   - Select **Social Links CE**
   - Click **Install** → Accept license → **Restart Maltego**
5. After restart, Social Links transforms will be available in the transform menu

### How to Use
1. Create a **New Graph**
2. Drag an **Entity** onto the canvas (e.g., Email Address, Person, Domain)
3. Enter the target value
4. Right-click the entity → **Run Transforms**
5. Select relevant Social Links transforms
6. Maltego will map out connections visually

---

## 🕷️ SpiderFoot

### What it does
SpiderFoot is an automated OSINT reconnaissance tool that collects intelligence about a target (IP, domain, email, username) from 200+ data sources automatically. It provides a web-based GUI for easy use.

### Installation
```bash
sudo apt install spiderfoot
```

### How to Use

**Step 1 — Start the web server:**
```bash
spiderfoot -l 127.0.0.1:5001
```

**Step 2 — Open in browser:**
```
http://127.0.0.1:5001
```

**Step 3 — Create a new scan:**
- Click **"New Scan"**
- Enter a **Scan Name**
- Enter the **Target** (domain, IP, email, username, etc.)
- Choose **Scan Type:**
  - `All` — Full scan (slow but thorough)
  - `Footprint` — Basic footprinting
  - `Investigate` — Targeted investigation
  - `Passive` — No direct contact with target
- Click **Run Scan Now**

**Step 4 — View Results:**
- Browse by module or data type
- Export results as CSV or JSON

---

## 🔑 Have I Been Pwned

### What it does
Checks if an email address or phone number has appeared in any known public data breaches. Free, no account needed, and completely reliable.

### Installation
No installation required — web-based tool.

### How to Use

**Website:** [https://haveibeenpwned.com](https://haveibeenpwned.com)

1. Go to the website
2. Enter an email address or phone number
3. View the full list of breaches where it appeared, including:
   - Breach name and date
   - What data was exposed (passwords, usernames, etc.)

**API Usage (free, no key needed for basic):**
```bash
curl https://haveibeenpwned.com/api/v3/breachedaccount/target@email.com
```

---

## ⚠️ Legal & Ethical Disclaimer

> All tools listed in this repository are for **educational purposes** and **authorized security testing only**.
>
> - ✅ Use only on systems/targets you **own** or have **written permission** to test
> - ❌ Unauthorized use may violate laws including the Computer Fraud and Abuse Act (CFAA) and similar legislation
> - 🔒 Always follow responsible disclosure practices

---

## 📌 Quick Reference Summary

| Tool | Type | Target | Free? |
|------|------|--------|-------|
| Holehe | CLI Tool | Email | ✅ 100% Free |
| Sherlock | CLI Tool | Username | ✅ 100% Free |
| Maltego + Social Links CE | GUI Platform | Multiple | ✅ Free CE Version |
| SpiderFoot | Web GUI Tool | Domain/IP/Email | ✅ 100% Free |
| Have I Been Pwned | Web | Email/Phone | ✅ 100% Free |

---

*Notes maintained from internship OSINT training sessions.*
