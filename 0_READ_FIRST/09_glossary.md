# **09\_glossary.md**

## **Glossary of Terms (Stage 0 — Mandatory)**

This glossary defines all core terminology used across the onboarding, upskilling, SACS, and Tabu repositories.  
 It ensures consistent language, shared understanding, and clear communication between contributors, reviewers, and maintainers.

---

# **A**

### **AC — Acceptance Criteria**

Clear, testable conditions that must be met for an issue or feature to be considered complete.

### **AI‑Generated Code**

Code produced by an AI tool (e.g., LM Studio).  
 Must always start in `/prototypes` and undergo manual review.

---

# **C**

### **Checklist (Coding Standards Checklist)**

A structured list of required coding practices used during PR review to ensure compliance with standards.

### **Clean Code**

Readable, maintainable, and minimal code that follows naming conventions, structure rules, and clarity principles.

### **Commit Message**

A short, structured message describing a change.  
 Must reference an issue.

### **Contributor**

Anyone who submits code, documentation, or improvements to the project.

### **Conflict‑Sensitive Design**

Design principles that avoid harm, reduce risk, and ensure ethical handling of sensitive contexts.

---

# **D**

### **Documentation Set (Stage 0\)**

The mandatory documents in `0_READ_FIRST` that define standards, workflow, and expectations.

---

# **E**

### **Eval (Prohibited Pattern)**

A dangerous JavaScript function that executes arbitrary code.  
 Banned unless explicitly approved.

---

# **F**

### **Feature Branch**

A branch created for a specific issue or task.  
 Follows naming rules like `feat/name/task`.

### **File Header**

The required metadata block at the top of every file, containing author, dates, description, module, and notes.

---

# **G**

### **Git Workflow**

The mandatory process for creating branches, making commits, opening PRs, and merging code.

### **Glossary**

This document.  
 Defines shared terminology across the ecosystem.

---

# **I**

### **Inherited Code**

Code migrated from prototypes, earlier contributors, or other repos.  
 Must be reviewed and documented in the file header.

### **Issue**

A tracked task, bug, or feature request.  
 Every PR must reference an issue.

---

# **L**

### **LM Studio Review**

A mandatory local AI‑assisted security and privacy review performed before submitting a PR.

---

# **M**

### **Main Branch**

The protected branch representing stable code.  
 Direct commits are prohibited.

### **Module**

A functional unit of the system (e.g., conflict‑mapping, scoring, parsing).

---

# **P**

### **PR — Pull Request**

A request to merge changes from a feature branch into `main`.  
 Must include issue reference, checklist, and review confirmation.

### **Prototype**

Experimental or AI‑generated code stored in `/prototypes`.  
 Not production‑ready.

### **Privacy‑First Engineering**

A design principle requiring that no personal or sensitive data is stored, logged, or exposed.

---

# **R**

### **Refs**

A commit message field linking the commit to an issue.

### **REQ — Requirements Document**

High‑level functional and non‑functional requirements that define what the system must do.

### **Reviewer**

A contributor responsible for verifying standards, security, and traceability before approving a PR.

---

# **S**

### **SACS — Socially Aware Conflict System**

The core system for conflict mapping, pattern detection, and ethical analysis.  
 Contributors reach SACS after completing the Upskilling Track.

### **SDD — System Design Document**

A technical interpretation of requirements.  
 Defines architecture, modules, and logic.

### **Security Baseline**

The mandatory rules for safe, privacy‑aligned development.

### **Silent Catch Block (Prohibited Pattern)**

A `try/catch` block that hides errors.  
 Not allowed.

---

# **T**

### **Tabu**

An invite‑only, ethically sensitive environment for advanced contributors.  
 Requires strict privacy, security, and traceability.

### **Traceability**

The ability to track every change back to a person, date, issue, requirement, and decision.

---

# **U**

### **Upskilling Track**

The first engineering environment after onboarding.  
 Focuses on clean code, early SACS modules, and professional development habits.

---

# **V**

### **Validation**

The process of checking that inputs, data, and logic meet expected constraints.  
 Required for all external data.

---

# **W**

### **Workflow (Development Workflow)**

The structured process contributors must follow:

Issue → Feature Branch → Commit → PR → Review → Merge

---

# **End of Glossary**

This glossary is the single source of truth for terminology across all repositories.  
 If a new term becomes common, it must be added here.


