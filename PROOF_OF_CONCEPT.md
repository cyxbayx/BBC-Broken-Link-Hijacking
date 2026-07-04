# Proof of Concept: Broken Link Hijacking on BBC News

## Overview
This document provides a detailed step-by-step walkthrough of how the Broken Link Hijacking vulnerability was discovered and exploited on BBC News website.

---

## Step-by-Step Reproduction

### Step 1: Initial Discovery

**Objective:** Find broken external links on BBC News website

**Process:**
- Visited BBC News website (bbc.com/news)
- Reviewed "Follow us" sections
- Examined social media links in navigation and footer
- Found multiple Instagram links with unclear ownership

**Results:**
- Identified links: `instagram.com/[target-username]/`
- Status: Active links (HTTP 200) but pointing to non-existent accounts

---

### Step 2: Account Status Verification

**Objective:** Determine if Instagram accounts are truly abandoned

**Process:**
- Clicked Instagram link from BBC website
- Navigated to `instagram.com/[target-username]/`
- Observed Instagram response

**Observations:**
Result: "Profile isn't available"
Message: "Sorry, this page isn't available."
Status: Account is inactive or deleted

**Verification:**
- Account was not deleted (would give different message)
- Account appears abandoned (inactive for extended period)
- Conclusion: Account is dormant/inactive

---

### Step 3: Username Availability Check

**Objective:** Test if abandoned username can be re-registered

**Process:**
1. Opened Instagram app
2. Attempted to create new account
3. During account creation, tested username availability
4. Searched for: `[target-username]`

**Result:**
✅ Username is available
Status: "That username is available"
Availability: Can be registered immediately

**Implication:**
- Instagram released the username (account was fully deleted/released)
- No account holds this username currently
- Attacker can register it freely

---

### Step 4: Account Registration

**Objective:** Successfully register the abandoned username

**Process:**
1. Created new Instagram account
2. Entered email address
3. Set password
4. Confirmed phone/email verification
5. Set username: `[target-username]`
6. Completed account setup

**Result:**
✅ Account created successfully
Username: [target-username]
Status: Active and ready to use
Access: Full control over account

**Proof:**
- Account accessible via: `instagram.com/[target-username]/`
- Can post content
- Can edit profile
- Can follow/unfollow accounts
- Can use all Instagram features

---

### Step 5: Verification & Control Demonstration

**Objective:** Confirm the vulnerability by demonstrating control

**Process:**
1. Returned to BBC News website
2. Located the Instagram link
3. Clicked the link
4. Observed where link redirects

**Verification Results:**
Original Link: instagram.com/[target-username]/
Link Status: Before = "Profile isn't available"
Link Status: After = Redirects to newly created account
Account Owner: Researcher (could be attacker)
Profile Control: Full control demonstrated

**Capabilities Demonstrated:**
- ✅ Post content to account
- ✅ Modify profile information
- ✅ Set profile picture
- ✅ Write bio/description
- ✅ Potential to impersonate BBC News
- ✅ Potential to spread misinformation

---

### Step 6: Impact Demonstration

**Objective:** Show what an attacker could do with this account

**Attack Scenario - Misinformation Campaign:**
1. Create profile mimicking BBC News
    - Use similar profile picture
    - Write misleading bio
    - Verify similarity to official account

2. Post misinformation
    - "BBC News: Breaking news alert [FALSE INFORMATION]"
    - Users see link from BBC website
    - Users trust BBC branding

3. Monitor engagement
    - Misinformation spreads
    - Thousands of users engaged
    - Reaches millions through shares

4. Impact
    - Public confusion
    - Erosion of trust
    - Potential panic (depending on content)

---

## Exploitation Timeline

| Time | Action | Result |
|------|--------|--------|
| T+0 min | Found broken link | Identified vulnerability |
| T+3 min | Checked account status | Confirmed abandoned |
| T+5 min | Tested username availability | Confirmed available |
| T+10 min | Registered account | Obtained control |
| T+12 min | Verified control | Confirmed full access |
| T+15 min | Tested capabilities | Demonstrated impact |

**Total Time to Exploitation:** ~15 minutes

---

## Technical Details

### Tools Used
- Web browser (Chrome/Firefox)
- Instagram web interface
- Standard internet connection
- No special tools or software

### Skills Required
- Basic web navigation
- Understanding of social media accounts
- Pattern recognition (spotting broken links)

### Barriers to Exploitation
- ❌ None (no technical barriers)
- ❌ No authentication required
- ❌ No special permissions needed
- ✓ Must notice broken link first
- ✓ Must guess username is available

---

## Remediation Verification

### Post-Remediation Status

**After BBC fixed the vulnerability:**
Original Issue: Broken Instagram link
Current Status: Link points to official BBC News account
Verification: ✅ Blue checkmark present
Account Owner: BBC officially confirmed
Security: ✅ Account secured with 2FA
Profile: ✅ Properly branded as official BBC News

**Verification Steps:**
1. ✅ Visited BBC website
2. ✅ Clicked Instagram link
3. ✅ Reached official BBC News account
4. ✅ Verified blue checkmark
5. ✅ Confirmed official status

---

## Lessons from This POC

### What Made This Vulnerable
1. **Broken link remained undetected** - No regular audit process
2. **Username was released** - Insufficient pre-registration strategy
3. **No verification system** - Users couldn't easily verify official status
4. **High-trust environment** - Users implicitly trust BBC website links

### What Prevented Larger Impact
1. **Responsible disclosure** - Researcher reported to BBC
2. **Quick response** - BBC fixed quickly
3. **Blue checkmark system** - Instagram verification provides safety net
4. **Misinformation detection** - Users can report fake accounts

---

## Conclusion

This proof of concept demonstrates that Broken Link Hijacking, despite being simple to exploit, can have significant impact on large media organizations. The vulnerability required minimal technical skill and resources but could have resulted in significant reputational damage if exploited maliciously.

**Time to exploit:** ~15 minutes  
**Technical difficulty:** Very Low  
**Potential impact:** Very High (for media organizations)  
**Likelihood of occurrence:** High (without preventive measures)

---

## References

- [Instagram Account Security](https://www.instagram.com/help/)
- [BBC Backstage Security](https://www.bbc.com/backstage/security-disclosure-policy/)