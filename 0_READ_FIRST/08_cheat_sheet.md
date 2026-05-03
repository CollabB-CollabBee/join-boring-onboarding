# **08\_cheat\_sheet.md**

## **Contributor Cheat Sheet (Quick Reference)**

This cheat sheet summarizes the most important rules from the Stage 0 onboarding documents.  
 It is designed for fast lookup during development, review, and PR preparation.

---

# **1\. Git Workflow (Critical)**

### **Branch Naming**

feat/\<name\>/\<short-description\>  
fix/\<name\>/\<short-description\>  
chore/\<name\>/\<short-description\>  
assignment/\<name\>/\<task\>

### **Workflow**

Issue → Feature Branch → Commit → PR → Review → Merge

### **Rules**

* No direct commits to `main`  
* Every PR must reference an issue  
* Commit messages must follow:

\<type\>: \<short description\>  
Refs: \#\<issue-number\>

Examples:

feat: add conflict score normalization  
Refs: \#42

---

# **2\. File Header Template (Required)**

Every file must begin with:

/\*\*  
 \* File: \<filename\>  
 \* Author: @\<github-username\>  
 \* Created: YYYY-MM-DD  
 \* Last Modified: YYYY-MM-DD  
 \* Description: \<short description\>  
 \*  
 \* Project: \<project-name\>  
 \* Module: \<module-name\>  
 \*  
 \* Notes:  
 \* \- Add inherited code notes here if applicable.  
 \*/

### **Inherited Code Notes Example**

Notes:  
\- Inherited from /prototypes/conflict-score-v1.js (2026-04-20).  
\- Original logic by @student123; reviewed and refactored for security compliance.

---

# **3\. Coding Standards (Summary)**

### **Naming**

* variables: `camelCase`  
* functions: `camelCase`  
* classes: `PascalCase`  
* constants: `UPPER_SNAKE_CASE`  
* files: `kebab-case.js`

### **Structure**

* one module per file  
* keep functions short and focused  
* avoid deep nesting  
* avoid magic numbers  
* use early returns

### **Comments**

* explain *why*, not *what*  
* keep comments short  
* update comments when code changes

---

# **4\. Security & Privacy (Critical)**

### **Never allow:**

* `eval()`  
* dynamic imports from user input  
* unvalidated external data  
* logging sensitive values  
* silent catch blocks  
* exposing internal logic in error messages

### **Always:**

* validate all inputs  
* sanitize external data  
* handle errors explicitly  
* avoid storing unnecessary data  
* run the LM Studio security review prompt

---

# **5\. LM Studio Security Review Prompt (Copy & Paste)**

Paste this into LM Studio before submitting a PR:

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

---

# **6\. PR Checklist (Before Submitting)**

* \[ \] Issue exists and is referenced  
* \[ \] Branch follows naming rules  
* \[ \] File header added and correct  
* \[ \] Inherited code documented  
* \[ \] LM Studio security review completed  
* \[ \] No unsafe patterns  
* \[ \] Code follows standards  
* \[ \] Acceptance criteria met  
* \[ \] PR description is complete

---

# **7\. Prototype Rules (Quick)**

* All AI‑generated code starts in `/prototypes`  
* Never commit AI code directly to `/src`  
* Prototype → Issue → Rewrite → PR  
* Document migration in file header

---

# **8\. Useful Git Commands**

git checkout \-b feat/name/task  
git status  
git add .  
git commit \-m "feat: message"  
git push \-u origin \<branch\>  
git pull  
git merge  
git rebase main

---

# **9\. Vocabulary (Quick Glossary)**

* **REQ** — Requirements  
* **SDD** — System Design Document  
* **AC** — Acceptance Criteria  
* **Prototype** — Experimental code, not production  
* **Module** — A functional unit of the system  
* **Traceability** — Ability to track every change to a requirement

---

# **10\. Final Reminder**

This cheat sheet is a shortcut —  
 the **full rules** live in the other Stage 0 documents.

Security, privacy, and traceability are mandatory.  
 Every contributor is responsible for following them.
