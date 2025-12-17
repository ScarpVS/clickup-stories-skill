# ClickUp Stories - Connected Vehicle Product Template

This skill helps create properly structured frontend development stories for connected vehicle products in ClickUp using the team's standardized template.

## Template Structure Overview

The template includes these sections (marked as Mandatory or Optional):

**Mandatory Sections:**
- ⏱️ Timing
- 📖 Context
- 🎯 Scope & Requirements
- 💥 Blast Radius
- ✅ Acceptance Criteria
- ✅ Done When

**Optional Sections:**
- 🚧 Blockers (include only if blockers exist)
- 🏁 Feature Flags (include only if feature flags are needed)
- ⚙️ Technical Specifications (omit for trivial tickets)
- 🎨 Design Specifications (omit if no UX/UI work)
- 💾 Data Requirements (omit for FE-only tickets)
- 📊 Analytics Tracking (often separate ticket)
- 🧪 QA Notes (QA fills during grooming/testing)
- 🔗 Linked Stories (use ClickUp native linking)

## Usage Instructions

When a user wants to create a story:

1. **Ask for Story Type & Context** - Understand what they're building and why
2. **Gather Required Information** - Ask questions to fill mandatory sections
3. **Determine Optional Sections** - Ask which optional sections apply
4. **Fill Template Systematically** - Work through each section
5. **Create in ClickUp** - Use `clickup_create_task` with formatted description
6. **Confirm Creation** - Return task URL and summary

## Information Gathering Questions

### For Timing Section (Mandatory)
- "What's the target completion date?"
- "When is QA verification due?"
- "Are there any backend dependencies?" (if yes, get BE stage/prod deployment dates)
- "Any timing constraints or dependencies?"

### For Context Section (Mandatory)
- "What is this story about?"
- "Why is this being done?"
- "What are the key requirements or use cases?"

### For Scope & Requirements (Mandatory)
- "Which vehicle types does this affect?" (Base Vehicle, Connected, AVK, EV, AVK2, AVK2EV, EVO)
- "What capabilities are required?" (UIDs, marketing names, service capabilities)
- "Which driver types?" (Primary Driver, Secondary Driver)
- "What are the access level requirements?"

### For Blast Radius (Mandatory)
- "Which screens, components, or flows are affected?"
- "What shared utilities or services are impacted?"
- "Are other regions or platforms affected?"
- "Assess regression risk for each area" (High/Medium/Low)
- "Any dependencies or context QA should know?"

### For Acceptance Criteria (Mandatory)
- "What are the happy path scenarios?" (use Given/When/Then format)
- "What error scenarios need to be handled?"
- "Any edge cases to consider?"

### For Optional Sections
- **Blockers**: "Are there any blockers?" (get description, link, owner, ETA)
- **Feature Flags**: "Does this need feature flags?" (get flag names, configurations)
- **Technical Specs**: "Any technical considerations?" (cache strategy, architectural notes)
- **Design**: "Is there a Figma link?" "Any localization needed?" (NNA, NCI, NMX)
- **Data Requirements**: "Any GraphQL queries or mutations needed?"
- **Analytics**: "What analytics tracking is needed?"

## Complete Template Format
````markdown
⏱️ TIMING
**Mandatory**

| Milestone | Date |
|-----------|------|
| 🎯 Target Completion | [Date] |
| 🧪 QA Verification Due | [Date] |

**BE Dependencies** (optional - include if story depends on backend work)

| Milestone | Date |
|-----------|------|
| 🎭 BE Stage Deployment | [Date] |
| 🚀 BE Prod Deployment | [Date] |

**Notes:** [Any story-specific timing constraints or dependencies]

---

🚧 BLOCKERS
**Optional: Omit if no blockers**

| Description | Link | Owner | ETA |
|-------------|------|-------|-----|
| [What's blocking] | [Ticket/Doc link] | [Who's resolving] | [Expected resolution] |

---

📖 CONTEXT
**Mandatory**

[What is this story, why is it being done, and what are the key requirements/use cases?]

* [Key requirement/use case 1]
* [Key requirement/use case 2]
* [Key requirement/use case N]

---

🎯 SCOPE & REQUIREMENTS
**Mandatory**

| Category | Specification |
|----------|---------------|
| 🚗 Vehicle Types | Base Vehicle, Connected, AVK, EV, AVK2, AVK2EV, EVO |
| ⚙️ Required Capabilities | [UID, marketing name, service capability] |
| 👤 Driver Types | Primary Driver, Secondary Driver |
| 🔐 Access Level | [Access requirements] |

---

💥 BLAST RADIUS
**Mandatory**

Identify all affected code paths and shared components so PM, Engineering, and QA can assess impact.

| Affected Area | Impact | Regression Risk |
|---------------|--------|-----------------|
| [Screen/Component/Flow] | [What changes] | 🔴 High / 🟡 Medium / 🟢 Low |
| [Shared utility/service] | [What changes] | 🔴 High / 🟡 Medium / 🟢 Low |
| [Other regions/platforms] | [What changes] | 🔴 High / 🟡 Medium / 🟢 Low |

**Context & Dependencies:** [Additional notes on why these areas are affected, upstream/downstream dependencies, or anything QA and engineering should keep in mind during implementation and testing.]

---

🏁 FEATURE FLAGS
**Optional: Omit for features that don't require a feature flag**

| Flag Name | Configuration | Description |
|-----------|---------------|-------------|
| [flag_name] | Enabled: true/false | [Description] |
| [flag_name] | Grant: force hide / force show / check capabilities | [Description] |

---

✅ ACCEPTANCE CRITERIA
**Mandatory**

**Happy Path Scenarios**

**Scenario 1: [Scenario Name]**
* GIVEN [Initial state/conditions]
* AND [Additional conditions]
* WHEN [User action or trigger]
* THEN [Expected outcome]

**Scenario N: [Scenario Name]**
* GIVEN [Initial state/conditions]
* WHEN [User action or trigger]
* THEN [Expected outcome]

**Error & Edge Case Scenarios**

**Error Scenario 1: [Scenario Name]**
* GIVEN [Initial state/conditions]
* WHEN [Error condition or trigger]
* THEN [Expected error handling/user experience]

**Edge Case 1: [Scenario Name]**
* GIVEN [Edge case conditions]
* WHEN [User action or trigger]
* THEN [Expected behavior]

---

⚙️ TECHNICAL SPECIFICATIONS
**Optional: Omit for trivial tickets**

**Cache Strategy**

| Aspect | Specification |
|--------|---------------|
| Cache Required | ✅ Yes / ❌ No |
| Cache Type | Session Memory / Local DB |
| Cache Duration | [Time period] |
| Cache Invalidation | [Trigger conditions] |

**Additional Technical Notes**

[Any architectural considerations, dependencies, or constraints]

---

🎨 DESIGN SPECIFICATIONS
**Optional: Omit for tickets without UX/UI considerations**

**Figma:** [Link]

**Design Notes:** [Any callouts on interactions, states, or platform-specific behaviors]

**Localization Copy** (Include if ticket spans multiple regions)

| String Location | English (NNA) | French (NCI) | Spanish (NMX) |
|-----------------|---------------|--------------|---------------|
| [In-app location] | [Text] | [Text] | [Text] |

---

💾 DATA REQUIREMENTS
**Optional: Omit for FE-only tickets with no BE dependencies**

**GraphQL Queries**
```graphql
# [Query Name]
query ExampleQuery($vin: String!) {
  # Query definition
}
```

**GraphQL Mutations**
```graphql
# [Mutation Name]
mutation ExampleMutation($input: ExampleInput!) {
  # Mutation definition
}
```

**Sample Request/Response**
```json
{
  "example": "data"
}
```

---

📊 ANALYTICS TRACKING
**Optional: Often handled in a separate ticket**

* User Action: [Event name] - [When triggered]
* Performance: [Metric name] - [What measured]
* Error: [Error type] - [When logged]

---

🧪 QA NOTES
**Optional: QA fills this section during grooming/testing**

**Test Accounts**

| Account | Credentials | Brand | Env | Vehicle (VIN/Model) | Postman | Notes |
|---------|-------------|-------|-----|---------------------|---------|-------|
| [Test User] | [email/password] | NIS / INF | STG / PRD | [VIN/model] | [Link] | [Special conditions] |

**QA Observations**

[QA adds notes, edge cases discovered, and test results here]

---

✅ DONE WHEN
**Mandatory**

* [ ] All acceptance criteria verified
* [ ] Code reviewed and approved
* [ ] QA sign-off complete
* [ ] Deployed to target environment
* [ ] No open blockers

---

🔗 LINKED STORIES

Use ClickUp's native linking feature (Linked, Blocker, Blocking) rather than listing here - this is a reminder to delete when stories are linked
````

## Creating the Story in ClickUp

**CRITICAL: Always use the complete template structure below. Never omit sections or formatting.**

When ready to create, use this exact process:

1. **Build Complete Template** - Fill the template with gathered information
2. **Preserve All Formatting** - Keep emoji headers, tables, markdown structure
3. **Include All Mandatory Sections** - Even if some fields are "TBD" or "[To be determined]"
4. **Create in ClickUp** - Use the MCP server with the complete template

````python
# ALWAYS use the clickup_create_task tool with the COMPLETE template
clickup_create_task(
    name="[Concise story title]",
    description="""[COMPLETE TEMPLATE BELOW - COPY EXACTLY]""",
    list_id="901406617827",  # NMEX Project Tracker
    priority="high",  # "urgent", "high", "normal", "low"
    status="icebox",  # Default to icebox for new stories
    assignees=["Vitor Scarpinetti"],  # Default assignee
    custom_fields={
        "15b8da55-b3fd-46bb-ad53-2190f18dab13": "948c1f46-4aac-4aac-99ee-c03f5a2c3c9e"  # Platform: iOS
    },
    tags=["frontend", "connected-vehicle", "story"]
)
````

**Template Preservation Rules:**
- ✅ **Always include ALL mandatory sections** (Timing, Context, Scope, Blast Radius, Acceptance Criteria, Done When)
- ✅ **Keep emoji headers and formatting** exactly as shown in template
- ✅ **Preserve table structures** and markdown formatting
- ✅ **Include optional sections** when applicable (Blockers, Feature Flags, Tech Specs, Design, etc.)
- ✅ **Use "[TBD]" or "[To be determined]"** for missing information rather than omitting sections
- ✅ **Maintain section order** as defined in the template
- ❌ **Never abbreviate or summarize** the template structure
- ❌ **Never omit sections** even if they seem empty

## Best Practices

1. **Start with Mandatory Sections** - Always collect timing, context, scope, blast radius, acceptance criteria
2. **Probe for Optionals** - Ask about blockers, feature flags, design work, BE dependencies
3. **Use Consistent Formatting** - Maintain table structures and markdown formatting
4. **Vehicle-Specific Context** - Understand the vehicle ecosystem (Base, Connected, AVK, EV, etc.)
5. **Risk Assessment** - Help assess blast radius and regression risks
6. **Acceptance Criteria Format** - Always use Given/When/Then format for scenarios
7. **Be Thorough** - This template is detailed for a reason - comprehensive stories prevent rework

## Common Vehicle Types Reference

- **Base Vehicle** - Standard vehicle without connectivity
- **Connected** - Vehicle with connected services
- **AVK** - Advanced Vehicle Kit
- **EV** - Electric Vehicle
- **AVK2** - Advanced Vehicle Kit 2nd generation
- **AVK2EV** - Advanced Vehicle Kit 2 Electric Vehicle
- **EVO** - Evolution platform

## Regression Risk Guidelines

- 🔴 **High** - Core functionality, shared services, multiple touchpoints
- 🟡 **Medium** - Feature-specific with some shared components
- 🟢 **Low** - Isolated change, minimal dependencies

## Interactive Story Creation Flow

**IMPORTANT: Follow this exact sequence to ensure complete template preservation**

1. **Greeting** - "I'll help you create a story using your team's comprehensive template. Let's gather all the information systematically."

2. **Title** - "What's the story title?"

3. **Mandatory Information Gathering:**
   - **Context** - "What are we building and why? What are the key requirements/use cases?"
   - **Timing** - "What's the target completion date? When is QA verification due? Any backend dependencies?"
   - **Scope** - "Which vehicle types (Base, Connected, AVK, EV, etc.)? Required capabilities? Driver types?"
   - **Blast Radius** - "What screens/components are affected? What's the regression risk (High/Medium/Low)?"
   - **Acceptance Criteria** - "Let's define the happy path scenarios using Given/When/Then format. Any error scenarios?"

4. **Optional Sections Assessment:**
   - "Are there any blockers?" (If yes, get details)
   - "Does this need feature flags?" (If yes, get flag configurations)
   - "Any technical specifications needed?" (Cache strategy, architectural notes)
   - "Is there UX/UI work with Figma links?" (If yes, get design details)
   - "Any GraphQL queries or backend data requirements?" (If yes, get data specs)
   - "What analytics tracking is needed?" (If any)

5. **Template Assembly** - Build the complete template with ALL sections:
   - Start with the exact template structure from "Complete Template Format"
   - Fill in mandatory sections with gathered information
   - Include optional sections if applicable, omit if not needed
   - Use "[TBD]" for any missing information rather than omitting sections
   - Preserve ALL emoji headers, table structures, and markdown formatting

6. **Validation** - Before creating, verify:
   - ✅ All mandatory sections present (⏱️ 📖 🎯 💥 ✅ ✅)
   - ✅ Emoji headers preserved
   - ✅ Table formatting maintained
   - ✅ No abbreviated or summarized sections

7. **Create** - Use clickup_create_task with the COMPLETE template in description field

8. **Confirm** - "Story created successfully! Here's the link: [URL]. The story includes the complete template structure with all required sections."

## Error Handling

- If mandatory information is missing, prompt for it before creating
- If user is unsure about vehicle types or capabilities, ask for clarification
- If blast radius isn't clear, help them think through impacted areas
- Default to "to do" status if not specified

## Template Validation Checklist

Before creating any story, verify this checklist:

### **Mandatory Sections (Must Always Be Present):**
- [ ] ⏱️ **TIMING** - With timing table and notes
- [ ] 📖 **CONTEXT** - With description and key requirements list
- [ ] 🎯 **SCOPE & REQUIREMENTS** - With specification table
- [ ] 💥 **BLAST RADIUS** - With affected areas table and context
- [ ] ✅ **ACCEPTANCE CRITERIA** - With Given/When/Then scenarios
- [ ] ✅ **DONE WHEN** - With completion checklist

### **Optional Sections (Include When Applicable):**
- [ ] 🚧 **BLOCKERS** - Only if blockers exist
- [ ] 🏁 **FEATURE FLAGS** - Only if feature flags needed
- [ ] ⚙️ **TECHNICAL SPECIFICATIONS** - Omit for trivial tickets
- [ ] 🎨 **DESIGN SPECIFICATIONS** - Omit if no UX/UI work
- [ ] 💾 **DATA REQUIREMENTS** - Omit for FE-only tickets
- [ ] 📊 **ANALYTICS TRACKING** - Often separate ticket
- [ ] 🧪 **QA NOTES** - Usually filled later by QA

### **Formatting Requirements:**
- [ ] All emoji headers exactly as shown in template
- [ ] Table structures preserved (| Column | Format |)
- [ ] Markdown formatting maintained
- [ ] Section separators (---) included
- [ ] Given/When/Then format for acceptance criteria

## Example Minimal Story Template

**When information is missing, use this structure with "[TBD]" placeholders:**

```markdown
⏱️ TIMING
**Mandatory**

| Milestone | Date |
|-----------|------|
| 🎯 Target Completion | [TBD] |
| 🧪 QA Verification Due | [TBD] |

**Notes:** [TBD - to be determined during planning]

---

📖 CONTEXT
**Mandatory**

[Brief description of what we're building and why]

* [Key requirement/use case - TBD]

---

🎯 SCOPE & REQUIREMENTS
**Mandatory**

| Category | Specification |
|----------|---------------|
| 🚗 Vehicle Types | [TBD] |
| ⚙️ Required Capabilities | [TBD] |
| 👤 Driver Types | [TBD] |
| 🔐 Access Level | [TBD] |

---

💥 BLAST RADIUS
**Mandatory**

| Affected Area | Impact | Regression Risk |
|---------------|--------|-----------------|
| [TBD] | [TBD] | 🟡 Medium |

**Context & Dependencies:** [TBD]

---

✅ ACCEPTANCE CRITERIA
**Mandatory**

**Happy Path Scenarios**

**Scenario 1: [TBD]**
* GIVEN [TBD]
* WHEN [TBD]
* THEN [TBD]

---

✅ DONE WHEN
**Mandatory**

* [ ] All acceptance criteria verified
* [ ] Code reviewed and approved
* [ ] QA sign-off complete
* [ ] Deployed to target environment
* [ ] No open blockers
```

## Notes

- **Template Preservation is Critical** - The team relies on this consistent structure
- **Never abbreviate sections** - Full template ensures nothing is missed during development
- **Use "[TBD]" liberally** - Better to have placeholder than missing structure
- **QA Notes section** is typically filled by QA during grooming/testing - can be left empty initially
- **Linked Stories** should use ClickUp's native linking - just remind user to link after creation
- **Always maintain emoji icons and section headers** for team consistency and visual scanning

## CRITICAL INSTRUCTIONS FOR CLAUDE

**When using this skill, you MUST:**

1. **Never skip the template structure** - Always use the complete template from "Complete Template Format" section
2. **Preserve exact formatting** - Copy emoji headers, tables, and markdown exactly as shown
3. **Include all mandatory sections** - Even if information is missing, use "[TBD]" placeholders
4. **Follow the interactive flow** - Gather information systematically using the questions provided
5. **Validate before creating** - Check the validation checklist before calling clickup_create_task
6. **Use correct MCP parameters** - Always use the specified list_id, status, assignees, and custom_fields

**Template Assembly Process:**
1. Start with the complete template structure from lines 78-284
2. Replace placeholders with gathered information
3. Add "[TBD]" for missing information rather than omitting sections
4. Verify all emoji headers and table formatting is preserved
5. Include the complete formatted template in the `description` field of clickup_create_task

**Example of Correct Tool Usage:**
```python
clickup_create_task(
    name="iOS: Implement Vehicle Status Dashboard",
    description="""⏱️ TIMING
**Mandatory**

| Milestone | Date |
|-----------|------|
| 🎯 Target Completion | 2024-01-15 |
| 🧪 QA Verification Due | 2024-01-18 |

**Notes:** No backend dependencies for this frontend-only ticket

---

📖 CONTEXT
**Mandatory**

Create a dashboard to display real-time vehicle status information for connected vehicles.

* Display battery level for EVs
* Show maintenance alerts
* Present connectivity status

[... COMPLETE TEMPLATE CONTINUES ...]

---

✅ DONE WHEN
**Mandatory**

* [ ] All acceptance criteria verified
* [ ] Code reviewed and approved
* [ ] QA sign-off complete
* [ ] Deployed to target environment
* [ ] No open blockers""",
    list_id="901406617827",
    priority="high",
    status="icebox",
    assignees=["Vitor Scarpinetti"],
    custom_fields={
        "15b8da55-b3fd-46bb-ad53-2190f18dab13": "948c1f46-4aac-4aac-99ee-c03f5a2c3c9e"
    },
    tags=["frontend", "connected-vehicle", "story"]
)
```

**Failure Modes to Avoid:**
- ❌ Summarizing or abbreviating the template
- ❌ Skipping sections because they seem "obvious" or "empty"
- ❌ Losing emoji headers or table formatting
- ❌ Creating stories without using the template structure
- ❌ Using wrong ClickUp parameters (list_id, custom_fields, etc.)

**Success Criteria:**
- ✅ Every story has the complete template structure
- ✅ All mandatory sections are present and properly formatted
- ✅ Team can rely on consistent story format across all tickets
- ✅ QA and engineering have all necessary context for development