

# **06\_security\_privacy\_baseline.md**

## **Security & Privacy Baseline (Stage 0 — Mandatory)**

This document defines the **minimum security and privacy requirements** for all contributors across all repositories.  
 These rules apply to:

* new code  
* inherited code  
* refactored code  
* AI‑generated code  
* prototypes  
* production modules

Security is not optional. Privacy is not optional.  
 All contributors must follow this baseline before submitting any Pull Request.

---

# **1\. Core Principles**

### **1.1 Privacy‑First Engineering**

This project operates in a peace‑tech and conflict‑sensitive domain.  
 Therefore:

* No personal data may be stored, logged, or transmitted.  
* No sensitive data may be used in examples or tests.  
* No contributor may introduce logic that exposes internal state or user data.

### **1.2 Security by Default**

All code must be written with the assumption that:

* inputs may be malicious  
* external data cannot be trusted  
* inherited code may contain vulnerabilities  
* AI‑generated code may contain unsafe patterns

### **1.3 Zero‑Trust for AI‑Generated Code**

AI tools (including LM Studio) can produce:

* insecure defaults  
* missing validation  
* silent failure modes  
* unsafe patterns that “look correct”

Therefore:

**All AI‑generated code must start in `/prototypes` and must be manually reviewed before entering `/src`.**

---

# **2\. Mandatory Security Requirements**

### **2.1 Input Validation**

Every function that accepts external input must validate:

* type  
* length  
* allowed characters  
* expected structure

### **2.2 Error Handling**

All code must:

* handle errors explicitly  
* avoid silent catch blocks  
* avoid swallowing exceptions  
* avoid exposing internal logic in error messages

### **2.3 Logging Rules**

Logging must **never** include:

* raw objects  
* user‑provided data  
* sensitive values  
* stack traces in production

### **2.4 No Dangerous Patterns**

The following patterns are prohibited unless explicitly approved:

* `eval()`  
* dynamic imports based on user input  
* unbounded recursion  
* unvalidated JSON parsing  
* insecure random number generation  
* direct access to request bodies without sanitization

### **2.5 No Data Retention Without Purpose**

Data must not be stored unless:

* it is required  
* it has a clear purpose  
* it has a defined retention rule  
* it is documented

---

# **3\. Inherited Code, AI‑Generated Code, and Unsafe Patterns**

### **3.1 Inherited Code Must Be Re‑Evaluated**

Inherited code is **not trusted**.  
 When modifying inherited code, contributors must assume:

* the original logic may be insecure  
* the original author may not have followed current standards  
* the code may violate privacy rules

Inherited code must be reviewed with the same scrutiny as new code.

### **3.2 AI‑Generated Code Is Never Trusted by Default**

All AI‑generated code must:

* start in `/prototypes`  
* be manually reviewed  
* be validated using the LM Studio security prompt  
* be rewritten if unsafe

### **3.3 Mandatory Local Review (LM Studio or Manual)**

Before submitting a PR, contributors must run a local review using:

* LM Studio (preferred)  
* or the manual checklist in this document

The review must check for:

* missing validation  
* unsafe string handling  
* insecure imports  
* missing error handling  
* data leakage  
* unnecessary data retention  
* unsafe defaults

### **3.4 Required Header Notes for Inherited Code**

When modifying inherited code, contributors must document the origin:

Notes:  
\- Inherited from \<path\> on \<date\>.  
\- Original logic by \<user\>; reviewed and refactored for security compliance.

### **3.5 Security Review Is Required for PR Approval**

A PR cannot be approved if:

* inherited code was modified without a security review  
* AI‑generated code was added without validation  
* unsafe patterns remain  
* the contributor skipped the LM Studio review

---

# **4\. Reviewer Responsibilities**

Reviewers must:

* reject PRs with unsafe patterns  
* verify that inherited code was reviewed  
* check that the file header includes Notes when required  
* ensure no sensitive data appears in logs or examples  
* confirm that AI‑generated code was validated

Reviewers are responsible for enforcing this baseline.

---

# **5\. Contributor Responsibilities**

Contributors must:

* follow all rules in this document  
* run the LM Studio security review prompt  
* document inherited code in the header  
* remove unsafe patterns  
* validate all inputs  
* follow the Git workflow

Security is part of the job, not an afterthought.

---

# **6\. LM Studio Security Review Prompt (Copy & Paste)**

Contributors must paste the following prompt into LM Studio before submitting a PR:
```
You are performing a security and privacy review for code that will be used in a conflict-sensitive, privacy-first environment.

Analyze the following code for:  
\- missing input validation  
\- unsafe string handling  
\- insecure imports or dynamic execution  
\- unbounded loops or recursion  
\- missing or unsafe error handling  
\- data leakage (logging sensitive values)  
\- unnecessary data retention  
\- unsafe default configurations  
\- prohibited patterns (eval, dynamic imports, raw logging)  
\- logic that appears correct but is exploitable  
\- privacy violations  
\- any inherited code that may contain outdated or unsafe logic

For each issue:  
1\. Identify the exact line or pattern.  
2\. Explain why it is insecure.  
3\. Provide a safe rewrite.  
4\. Suggest structural improvements if needed.

Assume the contributor may not recognize insecure patterns. Be explicit and strict.
```
Contributors must run this prompt **before every PR**.

---

# **7\. Final Notes**

This baseline is the minimum requirement.  
 Future stages (Upskilling Track → SACS → Tabu) introduce stricter rules.

Security and privacy are not optional.  
 They are foundational to the mission of this project.

