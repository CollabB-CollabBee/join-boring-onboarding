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
 * - File migrated from /prototypes/conflict-score-v1.js (2026-04-20).
 * - Original logic by @student123; refactored and standardized by @helen.

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

## **Inherited Code Rules**

When a contributor works on code that was inherited from another file, prototype, or contributor, the file header must reflect this clearly and consistently. The following rules apply:

### **1. Author**
The **Author** field always reflects the person who created the file *in this repository*, not the original creator of the logic.  
Do **not** change the Author when inheriting or refactoring code.

### **2. Created**
The **Created** date is the date the file first appeared in this repository.  
It does not track the age of the original logic.

### **3. Last Modified**
Update the **Last Modified** field every time you make changes to the file.

### **4. Notes (Required for inherited code)**
If the file contains inherited, migrated, or heavily refactored logic, add a short note in the **Notes** section.  
This ensures transparency and audit traceability.

Example:

```
Notes:
- Migrated from /prototypes/conflict-score-v1.js (2026-04-20).
- Original logic by @student123; refactored and standardized by @helen.
```

### **5. Git History**
Git remains the authoritative source of truth for:
- who changed what  
- when  
- how  

The header provides human‑readable context; Git provides full traceability.

---

