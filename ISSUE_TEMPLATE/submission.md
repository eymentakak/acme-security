---
name: Lab Submission
about: Submit your security incident lab analysis
title: '[SUBMISSION] Yusuf Eymen Takak - Security Incident Lab'
labels: submission
assignees: ''
---

## 👤 Candidate Information

**Full Name: Yusuf Eymen Takak** 
**Email: takak.eymen@gmail.com** 
**LinkedIn:[Click Here!](https://www.linkedin.com/in/eymentakak/)**
**Location: Istanbul**
**Submission Date: 09.11.2025** 

---

## 📎 Submission Files

**Option A: Attached Files**
- Report PDF: [GitHub Upload](https://github.com/eymentakak/acme-security/blob/main/submissions/Yusuf_Eymen_Takak/Yusuf-Eymen_Takak_Report.pdf)
- Video link: [Youtube](https://www.youtube.com/watch?v=AG530fxgmhc)

**Option B: External Links**
- Report: [Dropbox](https://www.dropbox.com/scl/fi/gemzsgaa05ozste1q03dp/Yusuf-Eymen_Takak_Report.pdf?rlkey=3ttgh6a6w1tdw5l0xhjebnint&st=ffofcjb8&dl=0)
- Video: [Vimeo](https://vimeo.com/1135094202?share=copy&fl=sv&fe=ci)

---

## ⏱️ Time Tracking

**Total time spent:** 11 hours

**Breakdown:**
- Log analysis: 2 hours
- Architecture design: 3 hours
- Report writing: 3 hours
- Video creation: 3 hours

---

## 🎯 Summary

### Attack Vectors Identified
1. **Phishing Campaign** - Spoofed emails from security@acme-finance.com targeting 6 employees, 50% click-through rate (user1, user3, user5)
2. **SQL Injection with WAF Bypass** - MySQL comment obfuscation (/*!50000OR*/ 1=1--) bypassing WAF rule 981001, resulting in 156KB data exfiltration
3. **Broken Object Level Authorization (BOLA)** - JWT token jwt_token_1523_stolen used to enumerate 16 unauthorized portfolios (accounts 1524-1538) within 42 seconds

### Key Findings
- **Coordinated multi-phase attack** from IP 203.0.113.45 spanning phishing → credential theft → API exploitation → data exfiltration in under 25 minutes
- **Known vulnerabilities left unaddressed**: API documentation explicitly noted "may not verify account ownership" yet authorization logic never implemented
- **Defense-in-depth failures**: WAF in detect-only mode for critical rules (981001, 942100), no rate limiting despite documentation claims, absent SIEM correlation across attack chain
- **Regulatory compliance breach**: 16 customers' PII and financial data exposed, triggering mandatory GDPR Article 33/34, KVKK Article 12, BDDK, and PCI-DSS Requirement 12.10.1 notifications within 72 hours
- **Root cause**: String concatenation in SQL queries, missing object-level authorization middleware, insufficient security awareness training (50% phishing success vs. <5% industry standard)

### Top 3 Recommendations
1. **Immediate (0-24h)**: Block attacker IP 203.0.113.0/24, revoke all JWT tokens, switch WAF rules 981001 and 942100 to blocking mode, suspend compromised accounts with mandatory MFA enrollment, preserve forensic evidence in WORM storage
2. **Short-term (1-2 weeks)**: Deploy centralized Authorization Service enforcing `if account.owner_id != jwt.user_id: return 403`, refactor all SQL to parameterized queries via SQLAlchemy ORM, implement API rate limiting (60 req/min standard, 10 req/min auth, sequential access pattern detection), conduct mandatory phishing awareness training targeting <5% click rate
3. **Long-term (1-3 months)**: Deploy SIEM platform (Splunk/ELK) with 5 critical correlation rules (phishing-to-auth within 30min, SQLi alert + large export, >10 account IDs within 5min), implement UEBA for behavioral anomaly detection, upgrade to NGWAF with ML-based detection and virtual patching, enable PostgreSQL row-level security with audit logging, deploy DMARC p=reject for email domain spoofing prevention

---

## 🛠️ Tools Used

**Analysis:**
- Splunk

**Diagrams:**
- Canva

**Video:**
- OBS

**Other:**
- 

---

## ✅ Checklist

Please confirm:

- [x] Report is max 5 pages
- [x] Video is 10-15 minutes
- [x] All log files were analyzed
- [x] Timeline is timezone-corrected
- [x] Framework mappings included (ISO 27001, NIST, OWASP)
- [x] Architecture diagram included
- [x] Video link is tested and working
- [x] No plagiarism / proper attribution
- [x] Original work, not AI-generated

---

## 💬 Optional Feedback

**What did you think of this lab?**
The lab was relatively easy to complete, but I noticed several inconsistencies that need to be addressed.

**Any suggestions for improvement?**
Timezone Inconsistencies: There are significant inconsistencies in the timezone standards across different lab materials. The test documentation uses PST format while the API PDF uses UTC format, yet the logs are expected to match. This creates confusion and makes it difficult to verify results accurately.
Insufficient Log Details: The log entries lack critical information that would be necessary in real-world scenarios:

When user email addresses are mentioned, their corresponding user IDs are not included
Source and destination IP addresses are missing
Other important network/security details are not captured

**Would you recommend this to others?**
- [ ] Yes
- [ ] No
- [x] Maybe

---

## 📧 Contact Preference

**Preferred contact method:**
- [x] Email
- [x] LinkedIn
- [ ] GitHub

**Best time to reach you: 7/24 :)**


---

## ⚖️ Declaration

I declare that this submission is my original work and I have followed all guidelines.

**Name: Yusuf Eymen Takak** 
**Date: 09.11.2025 ** 

---
