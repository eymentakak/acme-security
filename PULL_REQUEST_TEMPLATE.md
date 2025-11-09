## 📋 Submission Information

**Name:** Yusuf Eymen Takak
**Email:** takak.eymen@gmail.com  
**LinkedIn:** [Click Here!](https://www.linkedin.com/in/eymentakak/)
**Submission Date:** 09.11.2025

---

## ✅ Deliverables Checklist

Please confirm you've included all required items:

- [x] **Report** (PDF, max 5 pages)
  - [x] Section 1: Incident Analysis
  - [x] Section 2: Architecture Review
  - [x] Section 3: Response & Remediation
  
- [x] **Video Presentation** (10-15 minutes)
  - [x] Link provided in `video_link.md`
  - [x] Video is accessible (tested in incognito)
  - [x] Duration is within guidelines

- [x] **File Structure**
```
  submissions/firstname-lastname/
  ├── report.pdf
  ├── video_link.md
  └── notes.md (optional)
```

---

## 📊 Self-Assessment

**Time spent on this lab:** Approximately 11 hours

**Tools used:**
- Log analysis: 2
- Diagrams: 6
- Video recording: 3

**Confidence level:**
- [ ] Very confident in my analysis
- [ ] Confident but some uncertainties
- [x] Attempted my best with available knowledge

---

## 🎯 Brief Summary (2-3 sentences)

_Briefly describe your approach and key findings:_

[Write here]

---

## 🔍 Key Findings Highlight

**Main attack vectors identified:**
1. Phishing Campaign
2. SQL Injection with WAF Bypass
3. Broken Object Level Authorization (BOLA)

**Most critical vulnerability:**
Broken Object Level Authorization (BOLA)

**Top recommendation:**
deploy a centralized Authorization Service enforcing strict ownership verification across all API endpoints
MFA

---

## 💭 Challenges & Learnings

**What was most challenging?**
The most challenging aspect was creating the video presentation to effectively communicate technical findings. However, the most time-consuming technical challenge was establishing accurate time correlations across different log sources. I spent considerable effort trying to determine the correct timezone mappings - assuming web and email logs were in UTC+3, API logs in UTC, and WAF using source timestamps. Despite multiple attempts to validate these assumptions by correlating web-to-API and API-to-WAF events, the insufficient log details and sparse data made it impossible to definitively establish the attack timeline with confidence.

**What did you learn?**
I significantly improved my skills in Splunk dashboard development and learned the critical importance of timestamp standardization across distributed systems. The timezone correlation challenge taught me that proper logging standards and consistent time formatting are essential prerequisites for effective security analysis - a lesson that will influence how I approach log management in future security implementations.

**What would you do differently?**
If I were to repeat this lab, I would start by creating a comprehensive timeline mapping document from the beginning, documenting all timestamp observations and timezone assumptions as I encountered each log source. I would also prioritize establishing time correlations earlier in the investigation process rather than treating it as a secondary concern. Additionally, I would spend more time upfront understanding the logging architecture and timezone configurations before diving into the security analysis.

---

## 📝 Additional Notes _(optional)_

Any context, assumptions, or additional information you'd like evaluators to know:

Timezone Correlation Challenges: I invested significant effort attempting to establish accurate time correlations across log sources. My working hypothesis was that web and email logs used UTC+3 (local timezone), API logs used UTC, and WAF logs used source timestamps from incoming requests. However, due to insufficient contextual information in the logs and sparse data points, I was unable to definitively validate these assumptions through cross-referencing events across systems. This limitation may have affected the precision of my attack timeline reconstruction, though the overall attack chain and findings remain valid.

---

## ⚖️ Declaration

I declare that:
- [x] This work is entirely my own
- [x] I have not copied from other submissions or answer keys
- [x] I have not modified the provided log files
- [x] All sources and tools are properly attributed
- [x] I understand plagiarism results in disqualification

**Signature:** Yusuf Eymen Takak
**Date:** 09.11.2025

---

## 🚀 Ready for Review

By submitting this PR, I confirm that my work is complete and ready for evaluation.

---

_Thank you for your submission! Our team will review it within 1 week._
