# ✅ **1. Coding Standards Checklist (Alpha Version)**

This checklist belongs in:

`0_READ_FIRST/02_coding_standards_checklist.md`

Contributors must complete this before submitting any PR.

---

## **📌 Coding Standards Checklist**

### **1. File Header**
```
[ ] Every file begins with the mandatory header  
[ ] Author, Created, Last Modified fields are correct  
[ ] Description is accurate and specific  
[ ] Project and Module fields are correct  
```

### **2. Clean Code**
```
[ ] No dead code  
[ ] No commented‑out blocks  
[ ] No unnecessary abstraction  
[ ] Functions are small and single‑purpose  
[ ] No deeply nested logic (guard clauses used)  
```

### **3. Naming**
```
[ ] camelCase for variables and functions  
[ ] PascalCase for components/classes  
[ ] UPPER_SNAKE_CASE for constants  
[ ] File names follow kebab-case or PascalCase (React)  
[ ] All names are meaningful and descriptive  
```

### **4. Structure**
```
[ ] File structure follows: imports → constants → functions → exports  
[ ] Folder structure follows feature‑based grouping  
[ ] One component per folder (React)  
```

### **5. Git Discipline**
```
[ ] Commit messages follow: type(scope): description  
[ ] Commits are small and logical  
[ ] Branch name follows conventions  
```

### **6. Linting & Formatting**
```
[ ] 2‑space indentation  
[ ] Semicolons used  
[ ] Single quotes for strings  
[ ] Max line length respected  
[ ] No unused imports  
[ ] Linter passes with no warnings  
```

### **7. Error Handling**
```
[ ] No silent failures  
[ ] Errors are logged or thrown  
[ ] Guard clauses used where appropriate  
```

### **8. Security**
```
[ ] No sensitive data in code  
[ ] All inputs validated  
[ ] No dangerous patterns (eval, dynamic imports from user input)  
```

### **9. Documentation**
```
[ ] Functions have short descriptions  
[ ] Parameters and return values documented  
[ ] PR description includes summary, what changed, why, and how to test  
```

---

# ✅ **2. LM Studio Self‑Assessment Prompt**

This is a **copy‑paste prompt** contributors can use locally in LM Studio or Continue to evaluate their code before submitting a PR.

It forces them to reflect on the standards and get structured feedback.

---

## **📌 Self‑Assessment Prompt for LM Studio**

```
You are my local code reviewer. Evaluate my code strictly against the following Coding Standards (alpha version):

1. Mandatory file header (author, dates, description, project, module)
2. Clean code principles (no dead code, no commented blocks, no unnecessary abstraction)
3. Naming conventions (camelCase, PascalCase, UPPER_SNAKE_CASE, meaningful names)
4. File and folder structure (imports → constants → functions → exports, feature-based grouping)
5. Git discipline (commit message format, small commits, correct branch naming)
6. Linting and formatting rules (2-space indent, semicolons, single quotes, max line length, no unused imports)
7. Error handling (no silent failures, guard clauses)
8. Security baseline (no sensitive data, input validation, no dangerous patterns)
9. Documentation (function descriptions, parameter notes, PR clarity)

For the code I provide, do the following:
- Identify every violation of the standards
- Explain why it is a violation
- Suggest the corrected version
- Rate the overall code quality from 1–5
- Provide a final checklist of what I must fix before submitting a PR

Here is the code to review:
<PASTE CODE HERE>
```

