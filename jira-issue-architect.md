---
name: jira-issue-architect
description: Comprehensive engine for generating high-quality Jira issues. Detects issue type (Bug, Story, Task, Epic, Spike) and applies professional Jira Wiki Markup for clear developer communication.
metadata:
  author: jira-issue-architect
  version: "2.6.0"
  argument-hint: <raw-notes-or-technical-description>
---

# Jira Issue Architect Skill

## Purpose
A universal system to standardize Jira communication. This skill transforms raw notes or technical requirements into structured, professional, and developer-ready Jira tickets using validated Wiki Markup.

## Instructions

### 1. Classification & Language Logic
* **Intent Detection**: Categorize the input as **BUG** (error/regression), **STORY** (user value), **TASK** (technical work), or **SPIKE** (research).
* **Language Handling**: Preserve the user's primary language (e.g., Vietnamese) for the descriptive body, but use **English** for standard headers (e.g., "Acceptance Criteria") for global compatibility.

### 2. Formatting Standards
* **Header Syntax**: Use `h1.` for titles and `h2.` for sections.
* **Alignment Fix**: Use `||Header||` for all context tables to ensure centered, bolded, and proportional columns as per the required UI style.
* **Technical Terms**: Wrap all IDs, variables, and API paths in `{{double curly braces}}`.

---

## 3. Structural Templates

### A. BUG (The Problem)
* **Header**: `h1. Bug: [Component] Brief Summary`
* **Metadata Table**: 
|| Priority || Env || Module ||
| Medium | Production/Staging | [Module Name] |
----
* **Steps**: Numbered `#` list for reproduction.
* **Result Comparison**:
{panel:title=ACTUAL RESULT|titleBGColor=#ffebe6|bgColor=#fff5f3}
[Describe the broken behavior]
{panel}
{panel:title=EXPECTED RESULT|titleBGColor=#e3fcef|bgColor=#f4fff9}
[Describe the correct behavior]
{panel}

### B. USER STORY (The Value)
* **Header**: `h1. Story: [Feature Name]`
* **Requirement**: `*As a* [role], *I want to* [action], *so that* [value]`.
* **Acceptance Criteria**: 
* [ ] `Given` [context] + `When` [action] + `Then` [result].

### C. TASK / SPIKE (The Effort)
* **Header**: `h1. Task: [Action Summary]` or `h1. Spike: [Research Topic]`
* **Objective**: Define the high-level success criteria.
* **Scope of Work**: Specific technical checklist `* [ ]`.
* **Technical Notes**: Use `{panel:title=TECH NOTES|titleBGColor=#deebff}` for implementation details.

---

## 4. Standard Resources

### Universal Definition of Done (DoD)
h2. Definition of Done (DoD)
* [ ] Code reviewed by peer.
* [ ] Unit/Integration tests passed.
* [ ] Verified on Staging environment.
* [ ] Documentation (Swagger/Wiki) updated.

### Visual Reference Map
| Element | Syntax | Usage |
|:--- |:--- |:--- |
| **Monospaced** | `{{text}}` | IDs, API endpoints, code. |
| **Separators** | `----` | Logical section breaks. |
| **Checklist** | `* [ ]` | Actionable items/DoD. |

---

## Examples

### Input: "Fix bug layout column Tên chiến dịch overlapping Người tạo. ID: CVKS080126002"
**Output:**
h1. Bug: [FE] Campaign Name column overlaps Creator column
----
|| Priority || Env || Module ||
| Medium | Production/Staging | Survey Report |
----
h2. Steps to Reproduce
# Truy cập Danh sách công việc
# Kiểm tra chiến dịch có tên dài: {{CVKS080126002}}
----
{panel:title=ACTUAL RESULT|titleBGColor=#ffebe6}
Tên chiến dịch quá dài đè sang cột Người tạo.
{panel}
{panel:title=EXPECTED RESULT|titleBGColor=#e3fcef}
Tên chiến dịch tự động ngắt dòng và không đè lên các cột khác.
{panel}
