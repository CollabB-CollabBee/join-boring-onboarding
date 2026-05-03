`0_READ_FIRST/02_coding_standards.md`

---

# **02 — Coding Standards (Alpha Version)**

This document defines the minimum coding standards for all contributors.  
These rules apply to **every** repository in the ecosystem (SACS, Tabu, prototypes, onboarding tasks).

The goal is simple:  
**Write code that is clean, readable, consistent, and safe.**

This is the alpha version — it will evolve as the architecture matures.

---

# **1. General Principles**

### **1.1 Clean Code First**
- Code must be readable without explanation  
- No cleverness  
- No unnecessary abstraction  
- No dead code  
- No commented‑out blocks  

### **1.2 Consistency Over Preference**
If a rule exists, follow it.  
If a rule does not exist, follow the existing style in the repo.

### **1.3 Small, Focused Functions**
- One responsibility per function  
- Max 20–30 lines unless justified  
- Avoid deeply nested logic  

### **1.4 Predictable Structure**
Every file should be easy to navigate:
- imports  
- constants  
- functions  
- exports  

---

# **2. Naming Conventions**

### **2.1 Files**
- `kebab-case` for files: `user-profile.js`  
- React components: `PascalCase.jsx`  
- Config files: `lowercase.config.js`

### **2.2 Variables**
- `camelCase` for variables and functions  
- `PascalCase` for classes and components  
- `UPPER_SNAKE_CASE` for constants  

### **2.3 Meaningful Names**
Bad:
```js
let x, data1, temp;
```

Good:
```js
let userId, sessionToken, conflictScore;
```

---

# **3. Folder Structure Rules**

### **3.1 Keep It Flat**
Avoid unnecessary nesting.

### **3.2 Group by Feature, Not by Type**
Prefer:
```
/conflict-mapping
  /api
  /ui
  /logic
```
Over:
```
/components
/api
/utils
```

### **3.3 One Component per Folder (React)**
```
/UserCard
  UserCard.jsx
  UserCard.css
  index.js
```

---

# **4. Git & Commit Standards**

### **4.1 Commit Messages**
Format:
```
type(scope): short description
```

Examples:
- `feat(api): add conflict scoring endpoint`  
- `fix(ui): correct layout shift in dashboard`  
- `refactor(core): simplify role detection logic`  

### **4.2 Commit Discipline**
- Small commits  
- One logical change per commit  
- No “final fix” or “misc changes” commits  

### **4.3 Branch Naming**
```
feature/short-description
fix/bug-description
refactor/module-name
onboarding/stage-x
```

---

# **5. Linting & Formatting (Alpha Rules)**

We do not yet have a full linting config — this is the alpha version.

### **5.1 Formatting Rules**
- 2‑space indentation  
- semicolons required  
- single quotes for strings  
- max line length: 100 chars  
- trailing commas allowed  
- no unused imports  

### **5.2 ESLint (Alpha Baseline)**
We will adopt:
- `eslint:recommended`  
- `plugin:react/recommended` (for React repos)  
- `plugin:security/recommended` (for backend repos)  

### **5.3 Prettier (Alpha Baseline)**
Prettier rules:
```json
{
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "printWidth": 100,
  "trailingComma": "all"
}
```

### **5.4 Required Before PR**
- Run linter  
- Fix all warnings  
- No console logs in production code  

---

# **6. Error Handling**

### **6.1 No Silent Failures**
Every error must be:
- logged  
- thrown  
- or handled explicitly  

### **6.2 Use Guard Clauses**
Bad:
```js
if (user) {
  if (user.role) {
    if (user.role === 'admin') {
      // ...
    }
  }
}
```

Good:
```js
if (!user || !user.role) return;
if (user.role !== 'admin') return;
```

---

# **7. Security Baseline (Alpha)**

### **7.1 No Sensitive Data in Code**
- no tokens  
- no API keys  
- no personal data  

### **7.2 Validate All Inputs**
Especially in SACS and Tabu modules.

### **7.3 Avoid Dangerous Patterns**
- no `eval()`  
- no dynamic imports from user input  
- no raw SQL strings  

---

# **8. Documentation Requirements**

### **8.1 Every Function Needs:**
- a short description  
- parameter explanation  
- return value explanation  

### **8.2 Every File Needs:**
- a top‑level comment describing purpose  

### **8.3 Every PR Needs:**
- summary  
- what changed  
- why it changed  
- how to test it  

---

# **9. Alpha Version Notice**

This is the **alpha** version of our coding standards.  
It will evolve as:
- architecture stabilizes  
- SACS matures  
- Tabu modules become more defined  
- linting rules become stricter  
- security requirements increase

---
Absolutely — the **mandatory file header** belongs *inside the Coding Standards document*, because it is part of your enforceable code‑quality baseline.  
This is where contributors learn that **every file must begin with a professional, traceable header** that supports:

- audit trails  
- grant compliance  
- author accountability  
- version tracking  
- consistent documentation  

Below is the **alpha version** of the File Header section you can insert directly into `02_coding_standards.md`.

I’ll write it cleanly, professionally, and in a way that junior contributors can follow without confusion.

---

# ✅ **Section 10 — Mandatory File Header (Alpha Version)**

Every source file in this ecosystem **must** begin with the standard file header shown below.  
This header ensures traceability, audit readiness, and consistent documentation across all projects (SACS, Tabu, onboarding, prototypes).

This is **non‑negotiable**.  
Files without this header will not be accepted in PRs.

---

## **10.1 File Header Template**

```txt
/**
 * File: <filename.ext>
 * Author: <full name or GitHub username>
 * Created: <YYYY-MM-DD>
 * Last Modified: <YYYY-MM-DD>
 * Description: <short description of the file’s purpose>
 *
 * Project: <SACS | Tabu | Onboarding | Prototype>
 * Module: <module or feature name>
 *
 * Notes:
 * - Follow coding standards from 0_READ_FIRST.
 * - Ensure all logic is clean, readable, and maintainable.
 * - Do not include sensitive data or credentials.
 */
```

---

## **10.2 Header Rules**

### **R1 — The header is required for every file**
This includes:
- JavaScript / TypeScript files  
- React components  
- backend modules  
- utility files  
- configuration files (except auto‑generated ones)  

### **R2 — Dates must be updated**
- `Created` stays the same  
- `Last Modified` must be updated with each meaningful change  

### **R3 — Description must be accurate**
No vague descriptions like:
- “helper file”  
- “test”  
- “stuff”  

Descriptions must explain the file’s purpose in one sentence.

### **R4 — Project and Module must be correct**
Examples:
- `Project: SACS`  
- `Module: conflict-mapping`  
- `Project: Tabu`  
- `Module: heatmap-analysis`  
- `Project: Onboarding`  
- `Module: clean-code-starter`  

### **R5 — No personal data**
Do not include:
- emails  
- phone numbers  
- real names if the contributor prefers a username  

GitHub username is acceptable and preferred for privacy.

---

## **10.3 Example Header (Filled In)**

```txt
/**
 * File: conflictScore.js
 * Author: @student123
 * Created: 2026-05-03
 * Last Modified: 2026-05-03
 * Description: Calculates conflict scores based on interaction patterns.
 *
 * Project: SACS
 * Module: conflict-mapping
 *
 * Notes:
 * - Follows clean code standards.
 * - No sensitive data included.
 */
```

---

## **10.4 Why This Header Exists**

This header supports:
- **audit trails** (required for grants)  
- **traceability** (mapping code → contributor → issue → requirement)  
- **professional documentation habits**  
- **consistent onboarding for juniors**  
- **cleaner PR reviews**  
- **safer collaboration in youth‑facing systems**  

It also prevents:
- anonymous code  
- unclear ownership  
- undocumented logic  
- missing context during audits  

---

If you want, I can now:

### 🔧 Add this section into the full Coding Standards document  
### 📄 Generate the Git Workflow document  
### 🔐 Generate the Security & Privacy Baseline  
### 🧭 Generate the Audit & Traceability document  
### 🧩 Generate the Cheat Sheet (top 10 rules)

Which one do you want next, Hèlen?

Contributors must follow this version until the next revision is published.

