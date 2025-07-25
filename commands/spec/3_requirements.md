# Spec Requirements Command

Generate or update requirements document for an existing spec.

## Usage
```
/spec:3_requirements [feature-name]
```

## Instructions
You are working on the requirements phase of the spec workflow.

**FILE LOCATION**: Feature files are located in `documentation/features/{feature-name}/`

1. **Identify Current Spec**
   - If no feature-name provided, look for specs in `./documentation/features/` directory
   - If multiple specs exist, ask user to specify which one
   - Load existing requirements.md if it exists from `documentation/features/{feature-name}/`
   - Load research.md if it exists from `documentation/features/{feature-name}/` for valuable context

2. **Generate Requirements Document**
   - **Check for Research**: If `research.md` exists, use its findings to inform requirements
   - Use EARS format (Easy Approach to Requirements Syntax)
   - Structure: Introduction, Requirements with User Stories and Acceptance Criteria
   - Each requirement should have:
     - User story: "As a [role], I want [feature], so that [benefit]"
     - Numbered acceptance criteria: "WHEN [event] THEN [system] SHALL [response]"
   - **Leverage Research**: Reference similar features, constraints, and recommendations from research

3. **Content Guidelines**
   - Consider edge cases and error handling
   - Include non-functional requirements (performance, security, etc.)
   - **NEW**: If research exists, incorporate:
     - Constraints identified in research
     - Security considerations from research
     - Performance requirements from research
     - Integration points discovered
   - Reference existing codebase patterns from research findings
   - Ensure requirements are testable and verifiable

4. **Approval Process**
   - Present the complete requirements document
   - Ask: "Do the requirements look good? If so, we can move on to the design."
   - Make revisions based on feedback
   - Continue until explicit approval is received

## Requirements Format
```markdown
# Requirements Document

## Introduction
[Brief summary of the feature]

### Research Context
[If research.md exists, reference key findings that inform these requirements]

## Requirements

### Requirement 1
**User Story:** As a [role], I want [feature], so that [benefit]

#### Acceptance Criteria
1. WHEN [event] THEN [system] SHALL [response]
2. IF [condition] THEN [system] SHALL [response]
```

## Next Phase
After approval, proceed to `/spec:4_design`.
