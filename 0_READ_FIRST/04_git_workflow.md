## **Audit Tracking Header**

| Field | Value |
| :---- | :---- |
| **Document ID** | POL-20251102-039 |
| **Filepath** | docs/policies/ |
| **Document Title** | **Branching and Git Workflow Policy** |
| Internal Module Code | **MOD\_SYS\_008** |
| EU WP Code (Legacy) | N/A (Placeholder: WPX\_DXX.X) |
| **Document Revision** | **v04** |
| Date Created | 2025-11-02 |
| **Last Modified** | 2025-11-05 |
| Conceptual Author | Hèlen Grives |
| Documenting Author | Gemini LLM |
| Module Owner (Legal) | Makea B.V. |
| Operational Owner | Hèlen Grives |
| GitHub Commit Hash | N/A (Placeholder: a1b2c3d) |
| Evidence Folder Path | N/A (Placeholder: /06\_Deliverables/...) |
| SHA256 Checksum | N/A (Only for final PDF version) |
| **Status** | **Draft** |
| Linked Budget Line | N/A (Placeholder: B.1 Personnel) |
| Related Deliverable Sheet | N/A (Placeholder: Filename/Link) |
| **Notes** | Defines the mandatory Git workflow for all project contributors, enforced via policy. |

##  **Branching and Git Workflow Policy**

### **1\. Introduction and Goals**

This policy defines the standard Git workflow for the central project repository. Its primary goals are to:

1. Prevent accidental breaks in the main application code through structured workflow.  
2. Ensure all code is reviewed and approved before being accepted into the stable branch.  
3. Teach standard, professional branching practices used by industry teams.

### **2\. Branch Protection (Policy-Enforced)**

**IMPORTANT: Due to repository plan limitations (free tier), enforcement of these rules relies on strict adherence to this policy and mandatory peer review, not platform settings.**

| Rule | Enforcement Method |
| :---- | :---- |
| **NEVER Commit Directly to main** | **Policy Violation:** Any direct commit to main must be immediately reverted and resubmitted via a PR. |
| **Require Peer Review** | **Manual:** No Pull Request can be merged without at least one assigned reviewer providing explicit approval. |

### **3\. Branch Types and Naming Convention**

All branches must be created from the most current state of the main branch.

#### **3.1 Branch Types**

| Branch Type | Purpose |
| :---- | :---- |
| **main** | **Production Code.** This branch must always contain stable, deployable code. |
| **feature** | New features, development tasks, or assignments. **All volunteer work is done here.** |
| **bug** | Specific fixes for known issues. |
| **proto** | Reserved for merging validated prototypes into the core application structure (rarely used by volunteers). |

#### **3.2 Branch Naming Convention (Mandatory for All Contributors)**

The naming convention ensures the work is traceable back to the originator and the type of task. **This applies to the Owner/Lead as well.**

**Format:** \[type\]/\[contributor-id\]/\[short-description\]

| Element | Accepted Values | Contributor ID | Example |
| :---- | :---- | :---- | :---- |
| **type** | feat (feature), bug (bug fix), docs (documentation), style (refactoring/cleanup) | **Volunteer ID:** Assigned Alias (e.g., jane, joe, intern-01) | feat/jane/login-page-ui |
| **contributor-id** | **Owner/Lead ID:** Assigned Alias (e.g., owner, lead-id, my-initials) | docs/owner/update-branching-policy |  |
| **description** | Hyphenated, concise summary of the change. | N/A | bug/joe/fix-api-timeout |

#### **3.3 Branch Name Character Rules (Non-Technical Guide)**

Using the correct symbols is **MANDATORY** for your branch name to work correctly. Think of the branch name as a file path.

| Character | Name | Purpose | Status |
| :---- | :---- | :---- | :---- |
| **/** | **Forward Slash** | Separates the main parts of the name (like folders). | **MANDATORY** |
| **\-** | **Hyphen (Dash)** | Separates words inside the description (e.g., login-page-ui). | **MANDATORY** |
|  | **Space** | Creates errors and confusion in the system. | **FORBIDDEN** |
| **\_** | **Underscore** | Should be avoided; use the hyphen (-) instead. | **AVOID** |

#### **3.4 Mockup Branch Name Examples**

These examples illustrate how **all contributors** (including the Owner/Lead) must structure their branch names according to the rules above.

| Scenario | Type | Contributor ID | Description | Full Branch Name |
| :---- | :---- | :---- | :---- | :---- |
| New Feature (Volunteer) | feat | jane | Creating the basic login screen UI. | feat/jane/login-screen-ui |
| Bug Fix (Volunteer) | bug | joe | Fixing an issue where API calls time out on mobile. | bug/joe/fix-api-timeout-mobile |
| Documentation Update (Lead) | docs | owner | Updating the branching policy document itself. | docs/owner/update-branching-policy |
| Refactoring/Cleanup | style | intern-01 | Changing variable names for consistency in the utility file. | style/intern-01/refactor-util-vars |
| Integrating a Prototype | proto | lead-id | Merging the validated map component prototype. | proto/lead-id/integrate-map-component |

### **4\. Pull Request (PR) Workflow**

The PR is the **only way** code moves from a working branch into main.

#### **4.1 PR Creation Checklist**

When submitting a PR, the contributor **must** ensure the following:

1. **Tested Locally:** The code has been run and tested successfully on the contributor’s machine.  
2. **VIBE Code Compliant:** The PR description confirms adherence to the **VIBE CODE Policy (MOD\_SYS\_038)**, especially concerning code **Verification** and **Testing**.  
3. **Prompt Record Linked:** For AI-generated code, the PR must link directly to the **Prompt Record Log file(s)** within the /prototypes/\[feature\]/logs directory.  
4. **No Conflicts:** The branch is up-to-date with main and all conflicts have been resolved by the contributor.

#### **4.2 Merging a PR**

A PR can only be merged when:

1. It passes all required **status checks** (if any are configured).  
2. It has received a positive review/approval from **at least one assigned peer reviewer** or the Operational Owner.

### **5\. Troubleshooting and Support**

#### **5.1 Handling Conflicts**

If Git reports a conflict when you try to merge or rebase:

1. **Stop:** Do not force-push or try to guess the fix.  
2. **Pull main:** Pull the latest changes from main into your feature branch and resolve the conflicts locally on your feature branch.  
3. **Ask for Help:** If you struggle to resolve a conflict, stop and ask the Operational Owner or another volunteer for assistance.

#### **5.2 Initial Setup (HTTPS vs. SSH)**

* **Recommendation:** While HTTPS works, we **strongly recommend setting up and using SSH keys** for a faster and more secure workflow that avoids repeated password entry. Consult official GitHub/GitLab documentation for setup instructions.
