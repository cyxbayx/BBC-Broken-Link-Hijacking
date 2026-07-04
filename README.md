# BBC News - Broken Link Hijacking (BLH) Vulnerability Disclosure

## 🏆 Official Acknowledgment

Listed in **BBC Backstage Security Disclosure Policy Acknowledgments**  
👉 [View on BBC Website](https://www.bbc.com/backstage/security-disclosure-policy/acknowledgements/)

**Researcher:** Bayu Adji Wilarno

---

## 📋 Executive Summary

A **Broken Link Hijacking (BLH)** vulnerability was discovered on BBC News website. The website contained a broken link pointing to an Instagram account that no longer existed, allowing potential impersonation of the media organization's brand.

**Severity:** Low to Medium  
**Status:** ✅ Acknowledged & Remediated  
**Report Date:** [Your date]

---

## 🔍 Vulnerability Details

### Type
Broken Link Hijacking (BLH) / Unclaimed Social Media Asset

### Vulnerability Description
BBC News website contained broken Instagram links in the "Follow us" section. The Instagram usernames these links pointed to were inactive/unavailable. An attacker could:
1. Register the unclaimed Instagram username
2. Create a profile mimicking BBC News
3. Post malicious content under BBC News branding
4. Impersonate the organization

### Discovery Method
- Manual review of external links on BBC News website
- Verification of Instagram account availability
- Proof of concept: Successfully registered the abandoned username

### CVSS Score

**CVSS v3.1: 5.4 (Medium)**

CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:U/C:N/I:H/A:N

**Severity Breakdown:**
- **AV:N** (Network) - Accessible from internet
- **AC:L** (Low Complexity) - No special conditions required
- **PR:N** (No Privileges) - No authentication needed
- **UI:R** (User Interaction Required) - User must click link from BBC website
- **S:U** (Scope Unchanged) - Impact limited to Instagram
- **C:N** (No Confidentiality) - No data disclosure
- **I:H** (High Integrity) - Brand impersonation possible
- **A:N** (No Availability) - Service availability not affected

**Why Medium (Not Higher)?**
- Requires user interaction (clicking the link)
- No sensitive data exposure
- Easy to detect and remediate
- Impact limited to social media reputation
- Users can verify authenticity via blue checkmark

**Why Not Low?**
- High integrity impact (brand impersonation)
- Affects millions of BBC audience
- Potential for large-scale misinformation
- Reputational damage significant for media organization

---

## 🎯 Impact Analysis

### Direct Impact
- **Brand Impersonation:** Malicious actors could impersonate BBC News on Instagram
- **Misinformation Spread:** False news or controversial content under BBC News name
- **Reputation Damage:** Loss of credibility and public trust
- **Loss of Digital Asset:** BBC unable to use preferred username/handle

### Indirect Impact
- **Audience Confusion:** Readers directed to unofficial/malicious accounts
- **Financial Risk:** Cost of reputation management and brand monitoring
- **SEO Impact:** Broken links negatively affect website SEO
- **Security Risk:** Entry point for coordinated disinformation campaigns

### Potential Attack Scenarios

**Scenario 1: Misinformation Campaign**

1. Attacker registers abandoned Instagram username
2. Creates profile mimicking BBC News with similar bio
3. Posts false information (e.g., breaking news that isn't real)
4. BBC website links direct readers to fake account
5. Misinformation spreads to millions before discovery

**Scenario 2: Phishing Campaign**

1. Attacker controls account appearing as BBC News
2. Posts fake "security update" with malicious link
3. Users trust BBC branding
4. Large-scale phishing attack on readers

---

## ✅ Remediation

### Status: RESOLVED ✅
BBC News has successfully addressed this vulnerability:

1. **Account Reclamation:** Officially registered on Instagram
2. **Verification:** Applied for verified status (blue checkmark)
3. **Link Updates:** Updated all broken social media links
4. **Monitoring:** Implemented brand monitoring systems

---

## 📚 Technical Details

### Affected Asset
- **Platform:** BBC News Website (bbc.com/news)
- **Social Media:** Instagram
- **Component:** Social media follow links in navigation/footer
- **Scope:** Multiple BBC News regional accounts

### Vulnerability Chain

1. Broken Instagram link in website
↓
2. Non-existent/inactive Instagram account
↓
3. Username available for registration
↓
4. Attacker registers username
↓
5. Brand impersonation possible
↓
6. Misinformation distribution at scale

### Proof of Concept
- Identified broken Instagram links on BBC website
- Verified account was inactive/abandoned
- Confirmed username was available for registration
- Successfully registered account and demonstrated control
- Verified BBC website link redirected to newly created account

---

## 🛡️ Prevention & Best Practices

### For Media Organizations & Large Platforms

**1. Regular Link Audits**
- Automated link checking tools (weekly)
- Quarterly manual reviews of external links
- Monitor social media platform changes
- Alert system for broken links

**2. Social Media Asset Management**
- Maintain inventory of all official accounts
- Regular verification of account ownership
- Pre-register variations of usernames
- Document account registration dates and owners

**3. Technical Controls**
- Implement automated link validation
- API integration with social platforms
- Broken link detection and alerts
- Link status monitoring dashboard

**4. Brand Protection**
- Brand monitoring services (24/7)
- Trademark registration across platforms
- Clear guidelines for employees
- Public communication of official accounts

**5. Incident Response**
- BLH-specific response procedures
- Cross-team coordination (security, legal, communications)
- Public communication strategy
- Timeline for account recovery

---

## 📖 Lessons Learned

### Key Takeaways
1. **Supply Chain Security:** Third-party services (social media) are critical assets
2. **Preventive Monitoring:** Regular audits catch issues early
3. **Brand Assets Inventory:** Organizations must maintain comprehensive digital asset lists
4. **Quick Response:** Fast remediation prevents escalation
5. **User Communication:** Transparency about official channels builds trust

### Similar Vulnerabilities to Watch For
- Unclaimed subdomains (subdomain takeover)
- Forgotten S3 buckets (cloud storage exposure)
- Abandoned repositories (source code exposure)
- Inactive API endpoints (information disclosure)
- Forgotten DNS records (domain takeover)

---

## 📞 Disclosure Timeline

| Date | Event |
|------|-------|
| [Report Date] | Vulnerability discovered and analyzed |
| [Submit Date] | Report submitted to BBC via responsible disclosure |
| [Response Date] | BBC confirmed receipt and acknowledged vulnerability |
| [Fix Date] | Vulnerability fixed in production |
| [Acknowledge Date] | Listed in BBC Acknowledgments |

---

## 📚 References

- [BBC Backstage Security Disclosure Policy](https://www.bbc.com/backstage/security-disclosure-policy/)
- [OWASP: Social Media Account Hijacking](https://owasp.org/www-community/)
- [CWE-400: Uncontrolled Resource Consumption](https://cwe.mitre.org/data/definitions/400.html)
- [NIST: Social Media Security](https://csrc.nist.gov/)
- [CVSS v3.1 Calculator](https://www.first.org/cvss/calculator/3.1)

---

## 📄 Acknowledgment

Thank you to **BBC Backstage** for their responsible disclosure process and for acknowledging this contribution to their security research program.

---

**About This Repository**

This repository documents a real-world vulnerability disclosure and serves as an educational resource for security researchers and organizations. All vulnerabilities documented here have been responsibly disclosed and remediated.

For questions or clarifications, please refer to the original disclosure at BBC Backstage.

---

## 📊 Repository Stats

- **Vulnerability Type:** Broken Link Hijacking
- **Platform Affected:** BBC News (Social Media)
- **Severity:** Medium (CVSS 5.4)
- **Status:** Remediated
- **Disclosure Method:** Responsible Disclosure
- **Acknowledgment:** ✅ Official BBC Recognition

