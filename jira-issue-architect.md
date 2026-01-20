---
name: jira-issue-architect
description: A high-performance engine for architecting professional Jira issues. Automatically classifies intent and applies high-value Jira Wiki Markup for Bugs, Stories, Tasks, and Spikes.
metadata:
  author: jira-issue-architect
  version: "2.5.0"
  argument-hint: <raw-notes-or-technical-description>
---

# Jira Issue Architect Skill

## Purpose
To standardize and elevate engineering communication by transforming raw notes, logs, or requirements into structured, developer-ready Jira tickets. This skill acts as a professional bridge between product vision and technical execution.

## Instructions

### 1. The Pre-Write Analysis
Before generating the output, the agent must perform the following internal steps:
* **Intent Classification**: Detect if the input is a **Bug** (fix), **Story** (feature), **Task** (technical chore), or **Spike** (research).
* **Language Policy**: Maintain the user's primary language for the body of the text (e.g., Vietnamese). Use **English** for standard headers (e.g., "Acceptance Criteria") to maintain global compatibility.
* **Technical Extraction**: Identify and highlight IDs, API endpoints, file paths, and environment details.

### 2. Style & Syntax Guide
* **Visual Hierarchy**: Use `h1.` for titles and `h2.` for sections.
* **Logical Dividers**: Use `----` to separate metadata from content.
* **Code Standard**: Wrap all technical strings (IDs, CSS, code) in `{{monospaced syntax}}`.
* **Callouts**: Use the `{panel}` macro for high-priority information (Actual vs. Expected).

---

## 3. The Professional Templates

### A. BUG REPORT (The "Contract of Failure")
* **Header**: `h1. Bug: [Component] Brief Summary`
* **Context Table**: `|| Priority || Env || Module || Ref ID ||`
* **Steps**: Use `#` for numbered reproduction steps.
* **Evidence Analysis**:
{panel:title=ACTUAL RESULT|titleBGColor=#ffebe6|bgColor=#fff5f3}
[The current broken behavior]
{panel}
{panel:title=EXPECTED RESULT|titleBGColor=#e3fcef|bgColor=#f4fff9}
[The correct/intended behavior]
{panel}

### B. USER STORY (The "Gherkin" Format)
* **Header**: `h1. Story: [Feature Name]`
* **User Statement**: `*As a* [role], *I want to* [action], *so that* [value].`
* **Acceptance Criteria (AC)**:
    * Use `* [ ]` checklists.
    * Follow the logic: `Given` (Context) + `When` (Action) + `Then` (Outcome).
* **Design/Assets**: `[Figma Link|https://figma.com/...]`

### C. TECHNICAL TASK / SPIKE (The "Execution" Format)
* **Header**: `h1. Task: [Action Summary]` or `h1. Spike: [Research Topic]`
* **Objective**: A single sentence defining success.
* **Scope of Work**: Use a technical checklist `* [ ]`.
* **Outcomes (for Spikes)**:
    # Key decisions reached.
    # Links to Proof of Concept (PoC).

---

## 4. Standard Resources

### Universal Definition of Done (DoD)
h2. Definition of Done (DoD)
* [ ] Code reviewed by peer.
* [ ] Unit/Integration tests passed.
* [ ] Verified on Staging environment.
* [ ] Documentation (Swagger/Wiki) updated.
* [ ] Performance impact assessed.

### Color Reference Map
| Panel Type | Title BG | Body BG | Use Case |
|:--- |:--- |:--- |:--- |
| **Error** | #ffebe6 | #fff5f3 | Actual results, blockers |
| **Success** | #e3fcef | #f4fff9 | Expected results, AC |
| **Info** | #deebff | #f0f5ff | Tech notes, architecture |

---

## Examples

### Input: "Need to research if we can use Cursor IDE for our team's frontend workflow. Timebox: 2 days."
**Output:**
h1. Spike: Evaluation of Cursor IDE for Frontend Workflow
----
h2. Objective
Determine if transitioning to Cursor IDE will improve the frontend team's productivity and code quality compared to current VS Code setups.
----
h2. Research Goals
* [ ] Evaluate AI-assisted refactoring capabilities.
* [ ] Test codebase indexing for large React repositories.
* [ ] Cost vs. Value analysis for Pro licenses.
----
{panel:title=TIME BOX|titleBGColor=#deebff}
*Duration:* 2 Days
*Deadline:* End of Sprint
{panel}
----
h2. Expected Outcomes
# Summary report comparing Cursor vs. VS Code.
# Recommendation on license acquisition.
