# **07\_audit\_traceability.md**

## **Audit & Traceability Requirements (Stage 0 — Mandatory)**

This document defines the audit and traceability rules that apply to all contributors and reviewers across all repositories.

These rules ensure that every change in the codebase can be traced to:

* a person  
* a date  
* a purpose  
* a requirement  
* a documented decision

This is essential for:

* grant compliance  
* ethical accountability  
* long‑term maintainability  
* security reviews  
* onboarding clarity

Audit traceability is not optional.

# **1\. Core Principles**

### **1.1 Every change must be traceable**

A reviewer must always be able to answer:

* **Who** made this change?  
* **When** was it made?  
* **Why** was it made?  
* **What requirement or issue does it relate to?**  
* **What was the previous version?**

### **1.2 Git is the authoritative source of truth**

The file header provides human‑readable context.

Git provides the full historical record.

Both are required.

### **1.3 No “floating” code**

No file, function, or module may exist without:

* a linked issue  
* a PR  
* a file header  
* a reviewer  
* a documented purpose

# **2\. Required Traceability Elements**

Every contribution must include:

### **2.1 Issue → PR → Commit Chain**

All work must follow this chain:

Code  
Issue → Feature Branch → Pull Request → Review → Merge

Direct commits to `main` are prohibited.

### **2.2 Issue Requirements**

Every issue must include:

* purpose  
* acceptance criteria  
* scope  
* non‑scope  
* links to related documents (REQ, SDD, prototypes)

### **2.3 PR Requirements**

Every PR must include:

* the issue number  
* a summary of changes  
* screenshots or logs if relevant  
* a checklist confirming standards compliance  
* confirmation that the LM Studio review was performed (if code was added or changed)

### **2.4 Commit Message Requirements**

Commit messages must follow:

Code  
\<type\>: \<short description\>

Refs: \#\<issue-number\>

Examples:

Code  
feat: add conflict score normalization  
Refs: \#42

Code  
fix: sanitize user input in parser  
Refs: \#17

# **3\. File Header Requirements**

All files must include the mandatory file header defined in

**05\_file\_header\_policy.md**.

The header ensures:

* author accountability  
* creation date  
* last modified date  
* module classification  
* inherited code notes  
* reviewer visibility

### **3.1 Inherited Code Notes**

When modifying inherited code, contributors must document:

Code  
Notes:  
\- Inherited from \<path\> on \<date\>.  
\- Original logic by \<user\>; reviewed and refactored for security compliance.

This is required for audit transparency.

# **4\. Requirements Mapping (REQ → SDD → Code)**

### **4.1 Requirements (REQ)**

High‑level functional and non‑functional requirements.

### **4.2 System Design Documents (SDD)**

Technical interpretation of requirements.

### **4.3 Code Implementation**

Actual logic that fulfills the requirement.

Every code file must be traceable back to:

Code  
REQ → SDD → Issue → PR → File Header → Code

This chain must never be broken.

# **5\. Prototype Traceability**

Prototypes are allowed, but they must be traceable.

### **5.1 All prototypes must live in `/prototypes`**

No exceptions.

### **5.2 Prototype → Issue → Rewrite**

When a prototype becomes real code:

* create an issue  
* rewrite the logic  
* document the migration in the file header  
* delete or archive the prototype

### **5.3 AI‑Generated Code**

AI‑generated code must be:

* placed in `/prototypes`  
* reviewed  
* rewritten if unsafe  
* documented in the file header

# **6\. Reviewer Responsibilities**

Reviewers must verify:

* the issue → PR → commit chain exists  
* the file header is complete  
* inherited code is documented  
* the LM Studio security review was performed  
* no floating code exists  
* the PR matches the acceptance criteria  
* the code matches the SDD/REQ references

Reviewers are responsible for enforcing traceability.

# **7\. Contributor Responsibilities**

Contributors must:

* follow the Git workflow  
* include issue references  
* update file headers  
* document inherited code  
* run the LM Studio security review  
* follow coding standards  
* avoid unsafe patterns  
* ensure every change has a purpose

# **8\. Audit Checklist (Quick Reference)**

Before approving a PR, reviewers must confirm:

* \[ \] Issue exists and is complete  
* \[ \] PR references the issue  
* \[ \] Commit messages reference the issue  
* \[ \] File header is present and correct  
* \[ \] Inherited code is documented  
* \[ \] LM Studio security review performed  
* \[ \] No unsafe patterns  
* \[ \] No floating code  
* \[ \] Code matches SDD/REQ  
* \[ \] All acceptance criteria met

# **9\. Final Notes**

This document is the **single source of truth** for audit and traceability requirements.

All repositories must follow these rules.

Traceability protects:

* contributors  
* reviewers  
* the project  
* the mission  
* future grants  
* ethical accountability

We are working towards this standard; the repos contain legacy code from the early stages. New repos must adhere to these standards.
