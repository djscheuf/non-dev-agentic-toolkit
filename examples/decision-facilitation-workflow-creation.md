# Decision Facilitation Workflow - Creation Conversation

This document captures the conversation that led to the creation of the decision facilitation workflow, showing how expert knowledge was translated into a structured AI-facilitated process.

## Initial Request

**User**: I want your help creating a facilitation workflow for effective decision making and consideration based on Drucker's *Effective Executive*, specifically the sections on Elements of Decision making, and Effective decisions. I have other resources in my PKM related to effective decision making, training in the same, as well as related activities like delegation, organizational change management, etc.

I have found prompts and workflows like research, integrate-research, active-partner, design-buddy, and draft-blog-post work very well.

I recently drafted the Wardley Mapping workflow using a facilitation guide to help.

I want you to discover relevant content in the named folders, and assemble a decision facilitation guide, being especially cognizant of the gaps described in Training in Decision Making. Ask any clarifying questions you need, and suggest research you think would support the creation of an effective facilitation workflow.

## AI's Initial Analysis

After reviewing the resources, the AI identified:

**Core Decision-Making Framework (Drucker's Elements):**
1. Identify if problem is generic or exceptional
2. Define boundary conditions (specifications the solution must satisfy)
3. Think through what's "right" before compromises
4. Build action into the decision (who, what, when)
5. Create feedback loops to test against reality

**Key Gaps Identified:**
- Domain identification (Cynefin Framework)
- Decision fatigue awareness and management
- Making decisions "real" in organizations (training, communication, systems)
- Trade-off evaluation under uncertainty
- Connection to delegation and decentralized command

**Existing Successful Patterns:**
- Wardley Mapping workflow uses progressive facilitation with explicit wait points
- Research workflow uses incremental, resumable structure
- Design Buddy uses challenge-based exploration

## Clarifying Questions Asked

**1. Target Audience & Context:**
- Who is this workflow for? (Individual decision-makers? Facilitators helping teams? Both?)
- What types of decisions should this cover? (Strategic? Operational? Technical? All?)
- Should this be for solo decision-making or group facilitation?

**2. Scope & Integration:**
- Should this workflow integrate with existing PKM structure (Seeds/Evergreens)?
- Do you want this to produce artifacts (decision documents, ADRs, decision logs)?
- Should it reference or create decision principles/tenets for future use?

**3. Depth & Approach:**
- Should this be step-by-step facilitation or more of a guided framework?
- How much emphasis on organizational implementation aspects?
- Should it include estimation/uncertainty quantification elements?

**4. Specific Elements:**
- What does "consideration" mean in addition to decision-making?
- Should this explicitly address the gaps from "Training in Decision Making"?
- Do you want this to help identify when NOT to make a decision?

## User's Clarifications

**Audience**: Individual decision-makers (not group facilitation)

**Scope**: Strategic, operational, and tactical decisions - NOT technical decisions (redirect to Design Buddy)

**Approach**: Step-by-step facilitation with explicit wait points

**Critical Focus**: Organizational implementation is THE most critical aspect
- Must address who/what/when and whether people can actually execute
- Cannot proceed to implementation until trade-offs are evaluated

**Key Elements to Include:**
- Early filters: Delegate/defer/eliminate check before deep work
- Cynefin domain identification
- Generic vs exceptional classification
- One-way vs two-way door assessment (reversibility)
- Trade-off evaluation (minimum 2-3 options)
- Timeline constraints
- Political realities (after identifying "right" solution)

**Estimation**: Light touch only - mention FAIR-ME scales and work breakdown, but don't facilitate through it

**Decision Fatigue**: Check-ins after several steps, offer to pause/resume

## Design Decisions Made

### Document Approach
**Two documents created during facilitation:**

1. **Discussion Log** (Progressive, conversational)
   - Captures the facilitation conversation
   - Records exploration, questions, insights as they emerge
   - Includes parking lot items
   - Working document during facilitation

2. **Decision Record** (Formal, structured)
   - Built progressively during facilitation
   - Follows extended ADR template with Drucker elements
   - Finalized upon completion
   - Serves as formal artifact

### Workflow Phase Structure

**Phase 0: Initialize & Early Filters**
- Create both documents
- Check: delegate/defer/eliminate
- Gather initial context

**Phase 1: Problem Classification**
- Cynefin domain identification
- Generic vs exceptional
- Reversibility assessment (one-way vs two-way door)
- Timeline constraints

**Phase 2: Boundary Conditions & "Right" Solution**
- Define must-haves vs nice-to-haves
- Identify constraints
- Define "right" solution (before compromises)

**Phase 3: Trade-off Evaluation**
- Generate 2-3 options
- Evaluate positives/negatives/feasibility for each
- Compare trade-offs

**Phase 4: Feasible Solution**
- Gather additional organizational context
- Select approach
- Identify necessary compromises
- Document rationale

**Phase 5: Implementation Planning** (MOST CRITICAL)
- Who needs to know
- What actions required
- Who takes actions
- **Can they actually do it?** (capability assessment)
- Training, permissions, resources, systems needed
- Communication plan
- Propagation strategy

**Phase 6: Feedback Design**
- Success criteria
- Metrics to track
- Review schedule
- Failure conditions

### Extended ADR Template Created

The Decision Record template includes:
- Context with Problem Classification
- Boundary Conditions (must-haves, nice-to-haves, constraints)
- Trade-off Analysis (3 option slots)
- Decision (chosen approach, rationale, compromises)
- Implementation Plan (with capability assessment)
- Feedback & Testing
- Consequences
- Notes/parking lot

## Key Insights from Creation Process

### 1. Implementation is the Hard Part
The most time-consuming step isn't making the decision - it's converting it into organizational action. The workflow emphasizes "Can they actually do it?" as the critical question.

### 2. Progressive Documentation Reduces Friction
Building both documents incrementally throughout the process:
- Reduces end-of-session documentation burden
- Provides visual feedback on progress
- Enables resumability at any point
- Separates exploration (Discussion Log) from artifact (Decision Record)

### 3. Early Filters Save Time
Checking delegate/defer/eliminate before deep work prevents unnecessary decision-making effort on problems that shouldn't be solved this way.

### 4. Decision Fatigue is Real
Three explicit checkpoints (after Phases 2, 3, 5) acknowledge cognitive load and offer breaks without judgment.

### 5. "Right" Before "Feasible"
Identifying the ideal solution first, then working backward to handle compromises, prevents premature optimization for political palatability.

### 6. Reversibility Changes the Bar
Two-way doors (reversible decisions) can move fast with lower certainty. One-way doors (irreversible) need higher confidence before proceeding.

## Research Suggested

The AI suggested researching:
1. Structured decision frameworks (OODA loop, WRAP framework, decision matrices)
2. Boundary condition definition techniques
3. Feedback mechanism design (leading vs lagging indicators)
4. Group decision facilitation (for future extension)
5. Decision documentation patterns

The user provided existing resources covering:
- Metrics and Metrics in Tension
- Feedback concepts
- OODA Loop
- PDCA vs OODA spectrum
- Delegation frameworks

## Workflow Invocation Format

```
I need to make a decision about [TOPIC/SITUATION].

[Optional: Initial context about the situation, constraints, or urgency]
```

The workflow guides through all phases with explicit wait points, building both documents progressively.

## Lessons for Creating Similar Workflows

### 1. Start with Clarifying Questions
Don't assume you understand the user's intent. Ask about:
- Target audience
- Scope and boundaries
- Depth of facilitation needed
- Critical success factors

### 2. Identify Existing Patterns
Look for successful workflows to emulate:
- Progressive facilitation with wait points
- Resumable structure
- Document artifacts produced

### 3. Find the Critical Bottleneck
For decision-making, it's organizational implementation. Focus workflow energy on the hardest part.

### 4. Build in Escape Hatches
- Early filters (delegate/defer/eliminate)
- Decision fatigue checkpoints
- Parking lot for sub-decisions
- Redirect to other workflows when appropriate

### 5. Two Documents Serve Different Purposes
- Exploration document captures the journey
- Formal artifact captures the destination
- Both are valuable for different reasons

### 6. Test Assumptions Explicitly
- "Assume generic until proven exceptional"
- "Does the explanation explain all observed events?"
- Build testing into the workflow

## References

- Drucker, Peter. *Effective Executive* - Elements of Decision Making
- Cynefin Framework (Snowden)
- OODA Loop (Boyd)
- Two-way door vs one-way door concept (Bezos)
- ADR pattern for decision documentation
