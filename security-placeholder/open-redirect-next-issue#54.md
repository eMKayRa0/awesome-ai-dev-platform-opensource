# 📎 Placeholder PR for Issue: Open Redirect via `next` Parameter - issue#54

This pull request serves as a **placeholder** for the reported **Open Redirect** vulnerability affecting the login endpoint:

### 🔍 Vulnerability Summary

- **Type:** Open Redirect
- **Severity:** Medium
- **CVSS Score:** 6.1 (AV:N/AC:L/PR:N/UI:R/S:U/C:L/I:L/A:N)
- **Endpoint Affected:** `/user/login/?next=`
- **Report URL:** https://app.aixblock.io/user/login/?next=https://evil.com

### 🐞 Description

The application fails to properly validate the `next` parameter on the login endpoint. This allows attackers to redirect users to malicious sites after login, potentially leading to:

- Credential theft
- Token/session hijacking
- Phishing attacks using a trusted domain

---

### ⚠️ Proof of Concept

- **PoC URL:**

https://app.aixblock.io/user/login/?next=https://evil.com


- **Use Case:**
```html
<a href="https://app.aixblock.io/user/login/?next=https://evil.com">Click here to login and claim your credits</a>

✅ Recommendations

    Reject any next values that start with http://, https://, or //.

    Allow only internal paths like /dashboard, /home, etc.

    Whitelist safe endpoints

    Optionally, show redirect confirmation or interstitial pages

🔐 Submitted By

This PR is part of the responsible disclosure process from a bug bounty hunter and submitted per contribution guidelines to attach a valid PR to the issue.

No code fix is included. Please assign a developer to address this issue accordingly.


---

## 🛠️ Pull Request Title:

Placeholder PR for Open Redirect on Login Endpoint (next param)


---

## 📝 Pull Request Description:
```markdown
This pull request is a **placeholder PR** for the Open Redirect vulnerability reported on the `/user/login/?next=` endpoint.

📌 **Issue Summary**: An attacker can redirect users to external domains like `evil.com` by abusing the `next` parameter on the login page.

📎 Reported Vulnerability: [Open Redirect via `next` Parameter](https://github.com/AIxBlock-2023/awesome-ai-dev-platform-opensource/issues/54)

As a **security researcher**, I am submitting this placeholder PR in line with project contribution rules.

This does **not include a code fix**, but serves to properly link the issue with a PR.

Thanks for your review.
