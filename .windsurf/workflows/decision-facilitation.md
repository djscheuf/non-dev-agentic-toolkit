---
description: Facilitate effective decision-making using Drucker's framework with organizational implementation focus
auto_execution_mode: 0
---

# Decision Facilitation Workflow

This workflow guides individual decision-makers through strategic, operational, and tactical decisions using Drucker's Elements of Decision Making. The focus is on translating decisions into organizational reality.

**Prerequisites:**
- For strategic, operational, or tactical decisions
- NOT for technical decisions (use Design Buddy instead)
- Individual decision-maker (not group facilitation)

**Invocation Format:**
```
I need to make a decision about [TOPIC/SITUATION].

[Optional: Initial context about the situation, constraints, or urgency]
```

## Workflow Overview

This workflow has 7 phases with explicit wait points. Two documents are created:
1. **Discussion Log** - Conversational capture of exploration
2. **Decision Record** - Formal structured artifact

---

## Phase 0: Initialize Session

### 0a. **acknowledge-and-assess**
- Acknowledge the decision request
- **CRITICAL CHECK**: Is this a technical decision?
  - If YES: "This workflow is designed for strategic, operational, and tactical decisions. For technical decisions, please use the Design Buddy workflow instead."
  - If NO: Proceed
- Ask initial scoping questions:
  - "What decision are you trying to make?"
  - "What's prompting this decision now?"
  - "What's the urgency or timeline?"
- **WAIT** for user response

### 0b. **create-documents**
// turbo
- Create Discussion Log:
  - Location: `Capture/`
  - Filename: `YYYYMMDDHHNN - Decision Discussion - [Topic].md`
  - Initialize with:
    ```markdown
    # Decision Discussion - [Topic]
    Date: YYYY-MM-DD HH:NN
    
    ## Initial Request
    [User's request]
    
    ## Discussion Log
    
    ## Parking Lot
    - 
    
    ## Key Insights
    - 
    ```
- Create Decision Record:
  - Ask user: "Where should I save the Decision Record? (Suggest: `Capture/` or project-specific ADR folder)"
  - **WAIT** for user response
  - Use template from: `templates/Decision Record.md`
  - Populate title and date
- Store document paths in working memory

### 0c. **gather-context**
- Prompt user for additional context:
  - "Are there related decisions or principles I should know about?"
  - "Do you have relevant Seeds, Evergreens, or past decisions to reference?"
  - "What organizational constraints or political realities should I be aware of?"
- **WAIT** for user response
- Document context in Discussion Log

### 0d. **early-filters**
Ask three critical filter questions:

**1. Delegate?**
- "Could this decision be delegated to someone else?"
- "Who is closest to this problem and has the context to decide?"
- If YES: Discuss delegation approach and potentially exit workflow
- **WAIT** for response

**2. Defer?**
- "Does this decision need to be made right now?"
- "What's the cost of waiting vs deciding today?"
- If defer is appropriate: Document why and when to revisit
- **WAIT** for response

**3. Eliminate?**
- "Could this problem be automated or eliminated rather than solved?"
- "Is there a way to make this decision unnecessary?"
- If eliminate is possible: Shift to elimination strategy
- **WAIT** for response

### 0e. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Context gathered
  - Early filter assessments (delegate/defer/eliminate)
  - Initial observations
- Save Discussion Log

### 0f. **phase-0-exit-check**
- Verify exit conditions:
  - [ ] Decision is not technical (or redirected to Design Buddy)
  - [ ] Both documents created
  - [ ] Context gathered
  - [ ] Early filters assessed (delegate/defer/eliminate)
  - [ ] User ready to proceed with decision facilitation
- If conditions not met, loop back to clarify
- If met, proceed to Phase 1

---

## Phase 1: Problem Classification

**Goal:** Understand the nature of the decision before diving into solutions.

### 1a. **identify-cynefin-domain**
Explain Cynefin Framework briefly, then assess:

**Ask:** "Which domain does this decision operate in?"

- **Clear**: "Are there established best practices that clearly apply?"
- **Complicated**: "Does this require expert analysis with multiple valid approaches?"
- **Complex**: "Is this emergent, requiring experimentation to see what works?"
- **Chaotic**: "Is immediate action required to stabilize the situation?"
- **Confusion**: "Are we unclear which domain this is?"

Guide user through assessment questions:
- "How well-understood is this problem?"
- "How predictable are the outcomes?"
- "Is there a right answer, or do we need to discover what works?"

**WAIT** for user assessment

### 1b. **classify-problem-type**
**Drucker's First Question:** "Is this a generic situation or an exception?"

Explain distinction:
- **Generic**: A recurring pattern that needs a rule/principle
- **Exceptional**: Truly unique, one-off situation (rare!)

Ask probing questions:
- "Have you or others faced this before?"
- "Is this a symptom of a systemic issue?"
- "If this is 'unique to you,' is it generic in your industry?" (TRIZ principle)
- "Could this be the early manifestation of a new generic problem?"

**Rule of thumb**: Assume generic until proven exceptional. Test with: "Does the explanation explain all observed events?"

**WAIT** for user classification

### 1c. **assess-reversibility**
**Critical for decision velocity:** "Is this a one-way door or two-way door?"

**Two-way door (reversible):**
- Can be undone with minimal cost
- Allows for fast decision-making
- Lower certainty bar required
- Example: Process experiment, pilot program

**One-way door (irreversible):**
- Difficult or costly to reverse
- Requires higher certainty
- Warrants more analysis
- Example: Organizational restructure, major technology commitment

Ask:
- "If this doesn't work out, how hard is it to reverse?"
- "What's the cost of being wrong?"
- "Can we run a small experiment first?"

**WAIT** for user assessment

### 1d. **identify-timeline**
Ask about timeline constraints:
- "When do you need this decision to have impact?"
- "What happens if we delay?"
- "Are there external deadlines driving this?"

Timeline affects scope and scale of feasible solutions.

**WAIT** for user response

### 1e. **update-decision-record**
// turbo
- Update Decision Record Context section:
  - Problem description
  - Domain (Cynefin)
  - Problem Type (Generic/Exceptional)
  - Reversibility (One-way/Two-way door)
  - Timeline constraint
- Save Decision Record

### 1f. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Domain assessment reasoning
  - Generic vs exceptional analysis
  - Reversibility discussion
  - Timeline considerations
- Save Discussion Log

### 1g. **phase-1-exit-check**
- Verify exit conditions:
  - [ ] Cynefin domain identified
  - [ ] Generic vs exceptional classified
  - [ ] Reversibility assessed
  - [ ] Timeline constraint documented
  - [ ] User understands problem nature
- If conditions not met, loop back to clarify
- If met, proceed to Phase 2

---

## Phase 2: Boundary Conditions & "Right" Solution

**Goal:** Define what the solution MUST satisfy before considering compromises.

### 2a. **identify-boundary-conditions**
**Drucker's Second Element:** Define specifications the solution must satisfy.

Explain: "We need to know what 'right' looks like before we consider what's 'feasible.'"

Ask systematically:

**Must Have (Immovables):**
- "What absolutely cannot be compromised?"
- "What would make this solution unacceptable?"
- "What constraints are non-negotiable?"

**Nice to Have (Flexible):**
- "What would be ideal but isn't required?"
- "What could we compromise on if needed?"

**Constraints:**
- "Budget limits?"
- "Resource constraints?"
- "Regulatory requirements?"
- "Cultural or political constraints?"

**WAIT** for user to articulate boundary conditions

### 2b. **validate-boundary-conditions**
Review boundary conditions with user:
- "Are these truly immovable, or are some negotiable?"
- "Have we captured all critical constraints?"
- "Is anything in 'must have' actually a 'nice to have'?"

**WAIT** for confirmation

### 2c. **define-right-solution**
**Drucker's Third Element:** Think through what's "right" BEFORE compromises.

Ask:
- "Ignoring politics and feasibility for a moment, what's the RIGHT solution?"
- "What solution fully satisfies all boundary conditions?"
- "If you had unlimited resources and authority, what would you do?"

This is the ideal solution before considering organizational reality.

**WAIT** for user to describe "right" solution

### 2d. **update-decision-record**
// turbo
- Update Decision Record:
  - Boundary Conditions section (Must Have, Nice to Have, Constraints)
  - Document "right" solution in notes
- Save Decision Record

### 2e. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Boundary condition exploration
  - "Right" solution discussion
  - Any tensions or conflicts identified
- Save Discussion Log

### 2f. **decision-fatigue-check-1**
- Inform user: "We've completed problem classification and boundary definition. This is a good checkpoint."
- Ask: "Would you like to take a break and resume later, or continue?"
- **WAIT** for user response
- If break: Document stopping point, save both files, provide resume instructions
- If continue: Proceed to Phase 3

### 2g. **phase-2-exit-check**
- Verify exit conditions:
  - [ ] Boundary conditions clearly defined
  - [ ] Must-haves vs nice-to-haves distinguished
  - [ ] "Right" solution articulated
  - [ ] User ready for trade-off evaluation
- If conditions not met, loop back to clarify
- If met, proceed to Phase 3

---

## Phase 3: Trade-off Evaluation

**Goal:** Evaluate 2-3 realistic options with their trade-offs.

### 3a. **generate-options**
Explain: "We need at least 2-3 options to evaluate. This creates real choice and reveals trade-offs."

Work with user to identify options:
- Start with the "right" solution from Phase 2
- Generate 2 alternative approaches
- Consider different scales, scopes, or approaches

Ask:
- "What are the realistic alternatives?"
- "What's a smaller/larger version of this?"
- "What's a different approach to the same problem?"

**WAIT** for user to propose 2-3 options

### 3b. **evaluate-option-1**
For first option, systematically evaluate:

**Positives:**
- "What are the benefits of this approach?"
- "What problems does it solve?"
- "What becomes easier?"

**Negatives:**
- "What are the downsides?"
- "What new problems does it create?"
- "What becomes harder?"

**Feasibility:**
- "Can we actually do this?"
- "What resources does it require?"
- "What's the timeline?"
- "What organizational barriers exist?"

**WAIT** for user evaluation

### 3c. **evaluate-option-2**
Repeat systematic evaluation for second option:
- Positives
- Negatives
- Feasibility

**WAIT** for user evaluation

### 3d. **evaluate-option-3**
If third option exists, repeat evaluation:
- Positives
- Negatives
- Feasibility

**WAIT** for user evaluation

### 3e. **compare-trade-offs**
Facilitate comparison:
- "Which option best satisfies boundary conditions?"
- "Where do the trade-offs differ most?"
- "Which negatives are acceptable vs unacceptable?"
- "Which option aligns with timeline constraints?"

**For Generic Problems:** "Which option establishes the best rule/principle for future decisions?"

**For Two-Way Doors:** "Which option can we test quickly and reverse if needed?"

**For One-Way Doors:** "Which option are we most confident in given the irreversibility?"

**WAIT** for user analysis

### 3f. **update-decision-record**
// turbo
- Update Decision Record Trade-off Analysis section:
  - Option 1 (positives, negatives, feasibility)
  - Option 2 (positives, negatives, feasibility)
  - Option 3 (if applicable)
- Save Decision Record

### 3g. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Option generation process
  - Trade-off discussions
  - Comparison insights
  - Any concerns or uncertainties
- Save Discussion Log

### 3h. **decision-fatigue-check-2**
- Inform user: "We've evaluated options and trade-offs. Another good checkpoint."
- Ask: "Would you like to take a break, or continue to feasibility and implementation?"
- **WAIT** for user response
- If break: Document stopping point, save both files
- If continue: Proceed to Phase 4

### 3i. **phase-3-exit-check**
- Verify exit conditions:
  - [ ] At least 2 options evaluated
  - [ ] Positives and negatives identified for each
  - [ ] Feasibility assessed for each
  - [ ] Trade-offs compared
  - [ ] User ready to select approach
- If conditions not met, loop back to clarify
- If met, proceed to Phase 4

---

## Phase 4: Feasible Solution

**Goal:** Move from "right" to "feasible" by addressing political realities and organizational constraints.

### 4a. **gather-additional-context**
Prompt for organizational context:
- "What political realities do we need to navigate?"
- "Who are the key stakeholders who could block or enable this?"
- "What organizational dynamics affect feasibility?"
- "Are there recent changes or sensitivities to consider?"

**WAIT** for user context

### 4b. **select-approach**
Ask user to select preferred option:
- "Based on trade-offs and organizational reality, which option do you want to pursue?"
- "Is this the 'right' solution, or a compromise?"

**WAIT** for user selection

### 4c. **identify-compromises**
If selected option differs from "right" solution:

Ask about compromises:
- "What are we compromising from the ideal?"
- "Why is this compromise necessary?"
- "Is this 'half a loaf' (acceptable) or 'half a baby' (unacceptable)?"

**Critical check:** "Does this solution still satisfy the must-have boundary conditions?"
- If NO: Return to Phase 3 to find better option
- If YES: Document compromises and proceed

**WAIT** for user to articulate compromises

### 4d. **document-rationale**
Work with user to articulate:
- "Why this option over others?"
- "What makes this the best choice given constraints?"
- "How does this establish a principle (if generic problem)?"

**WAIT** for user rationale

### 4e. **update-decision-record**
// turbo
- Update Decision Record Decision section:
  - Chosen Approach
  - Rationale
  - Compromises Made (political realities, adaptations)
- Save Decision Record

### 4f. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Additional context gathered
  - Selection reasoning
  - Compromise discussion
  - Rationale development
- Save Discussion Log

### 4g. **phase-4-exit-check**
- Verify exit conditions:
  - [ ] Approach selected
  - [ ] Compromises identified and justified
  - [ ] Rationale documented
  - [ ] Solution still satisfies must-have boundary conditions
  - [ ] User ready for implementation planning
- If conditions not met, loop back to clarify
- If met, proceed to Phase 5

---

## Phase 5: Implementation Planning

**Goal:** Translate decision into organizational action. THIS IS THE MOST CRITICAL PHASE.

### 5a. **explain-implementation-focus**
Explain to user:
"A decision isn't done when you've made the choice. It's done when the organization is actually doing the decision. This phase is about making it real."

Reference Drucker's Fourth Element: Building action into the decision.

### 5b. **identify-who-needs-to-know**
**Drucker's First Question:** "Who has to know of this decision?"

Ask systematically:
- "Who will be directly affected?"
- "Who needs to approve or support this?"
- "Who needs to be informed (even if not involved)?"
- "What does each person/group need to know?"

Create list with:
- Person/Role
- What they need to know
- Why they need to know

**WAIT** for user to identify stakeholders

### 5c. **define-required-actions**
**Drucker's Second Question:** "What action has to be taken?"

Work with user to enumerate:
- "What specific actions must happen?"
- "In what sequence?"
- "What are dependencies?"

For each action, capture:
- Action description
- Owner (who will do it)

**WAIT** for user to define actions

### 5d. **assess-capability**
**Drucker's Critical Question:** "What does the action have to be so that the people who have to do it CAN do it?"

For each action and owner, ask:
- "Can they actually do this?"
- "Do they have the skills?"
- "Do they have the permissions/access?"
- "Do they have the resources?"
- "Do they have the time?"

**If NO to any:** Identify capability gaps.

**WAIT** for user assessment

### 5e. **identify-capability-gaps**
For any "NO" answers, identify what's needed:

**Training:**
- "What skills need to be developed?"
- "Who provides training?"
- "How long will it take?"

**Permissions/Access:**
- "What access needs to be granted?"
- "Who approves access?"

**Resources:**
- "What budget, tools, or support is needed?"
- "How do we secure resources?"

**Systems/Process Changes:**
- "What processes need to change?"
- "What systems need updating?"

**WAIT** for user to identify gaps and solutions

### 5f. **design-communication-plan**
Ask about communication:
- "How will you communicate this decision?"
- "What's the message for each audience?"
- "What channel (email, meeting, doc)?"
- "What's the timing?"

Create communication plan table:
- Audience
- Message
- Channel
- Timing

**WAIT** for user to design communication

### 5g. **plan-propagation**
Ask about organizational propagation:
- "How does this decision move through organizational layers?"
- "Who communicates to whom?"
- "How do we ensure consistent understanding?"
- "What happens if people misunderstand or resist?"

**WAIT** for user propagation strategy

### 5h. **update-decision-record**
// turbo
- Update Decision Record Implementation Plan section:
  - Who Needs to Know (list with details)
  - Actions Required (table with owner and capability assessment)
  - Capability Gaps (training, permissions, resources, systems)
  - Communication Plan (table)
  - Propagation Strategy
- Save Decision Record

### 5i. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Stakeholder identification process
  - Action definition
  - Capability assessment discussions
  - Gap identification
  - Communication planning
  - Propagation strategy
- Save Discussion Log

### 5j. **decision-fatigue-check-3**
- Inform user: "We've completed implementation planning. One more phase to go."
- Ask: "Would you like to take a break before designing feedback, or continue?"
- **WAIT** for user response
- If break: Document stopping point, save both files
- If continue: Proceed to Phase 6

### 5k. **phase-5-exit-check**
- Verify exit conditions:
  - [ ] All stakeholders identified
  - [ ] Required actions defined with owners
  - [ ] Capability assessed for each action
  - [ ] Gaps identified with solutions
  - [ ] Communication plan created
  - [ ] Propagation strategy defined
  - [ ] User confident decision can be executed
- If conditions not met, loop back to clarify
- If met, proceed to Phase 6

---

## Phase 6: Feedback Design

**Goal:** Build feedback into the decision to test validity against reality.

### 6a. **explain-feedback-importance**
Explain to user:
"Drucker's Fifth Element: We must test our decision against actual events. All our assumptions could be wrong. We need to know when to adapt or abandon this decision."

### 6b. **define-success-criteria**
Ask:
- "This decision was successful if...?"
- "What does 'working' look like?"
- "What outcomes are we expecting?"

Be specific and measurable where possible.

**WAIT** for user to define success criteria

### 6c. **identify-metrics**
Ask about measurement:
- "What will we measure to test validity?"
- "What leading indicators show we're on track?"
- "What lagging indicators confirm success?"

Consider [[Metrics in Tension]]:
- "What paired metrics prevent gaming?"
- "What balance metric ensures we're not optimizing one thing at expense of another?"

**WAIT** for user to identify metrics

### 6d. **set-review-schedule**
Ask about timing:
- "When should we first check if this is working?"
- "How often should we review after that?"
- "Who reviews the metrics?"

Define:
- First check date/trigger
- Ongoing frequency
- Review owner

**WAIT** for user to set schedule

### 6e. **identify-failure-conditions**
**Critical question:** "At what point do we revisit or reverse this decision?"

Ask:
- "What would tell us this isn't working?"
- "What's the threshold for 'this was wrong'?"
- "What triggers a decision review?"

This is especially important for one-way doors.

**WAIT** for user to define failure conditions

### 6f. **document-consequences**
Ask user to think through:

**What Becomes Easier:**
- "What problems does this solve?"
- "What workflows improve?"

**What Becomes More Difficult:**
- "What new challenges does this create?"
- "What gets harder?"

**Risks & Mitigation:**
- "What could go wrong?"
- "How do we mitigate each risk?"

**WAIT** for user to articulate consequences

### 6g. **update-decision-record**
// turbo
- Update Decision Record:
  - Feedback & Testing section (success criteria, metrics, review schedule, failure conditions)
  - Consequences section (easier, harder, risks)
- Save Decision Record

### 6h. **update-discussion-log**
// turbo
- Add to Discussion Log:
  - Success criteria discussion
  - Metrics identification
  - Review schedule planning
  - Failure condition definition
  - Consequences exploration
- Save Discussion Log

### 6i. **phase-6-exit-check**
- Verify exit conditions:
  - [ ] Success criteria defined
  - [ ] Metrics identified
  - [ ] Review schedule set
  - [ ] Failure conditions documented
  - [ ] Consequences articulated
  - [ ] User has complete feedback plan
- If conditions not met, loop back to clarify
- If met, proceed to Completion

---

## Completion

### 7a. **finalize-decision-record**
// turbo
- Review Decision Record for completeness
- Add any final notes or parking lot items
- Update Status to "Proposed" (user will change to "Accepted" when implemented)
- Add cross-reference to Discussion Log in References section
- Save Decision Record

### 7b. **finalize-discussion-log**
// turbo
- Add final summary to Discussion Log:
  - Key insights from facilitation
  - Major decision points
  - Unresolved questions (parking lot)
  - Next steps
- Add cross-reference to Decision Record
- Save Discussion Log

### 7c. **present-summary**
Present to user:
- "Decision facilitation complete. Here's what we've created:"
- Summary of decision made
- Key implementation actions
- Critical success metrics
- Location of both documents

### 7d. **offer-next-steps**
Suggest:
- "Review Decision Record and update Status to 'Accepted' when ready"
- "Share Decision Record with stakeholders identified"
- "Schedule first feedback review"
- "Add to calendar: implementation actions and review dates"

If parking lot has items:
- "Would you like to create follow-up decision sessions for parking lot items?"

### 7e. **optional-research-suggestions**
If gaps were identified during facilitation:
- "I noticed we discussed [topic] but lacked deep context. Would you like me to research that?"
- Suggest using `/research` workflow for:
  - Frameworks mentioned but not fully explored
  - Best practices for implementation challenges
  - Case studies of similar decisions

**WAIT** for user response on next steps

---

## Key Facilitation Principles

### Turn-Taking Pattern
- Always **WAIT** for user response after asking questions
- Never assume user's answers
- Build incrementally based on user input
- Challenge assumptions when they seem unclear

### Progressive Documentation
- Update both documents after each phase
- User can review progress at any time
- Provides visual feedback on completion
- Documents serve different purposes (exploration vs artifact)

### Resumability
- Both documents persist all work
- Can pause at any decision fatigue checkpoint
- Can resume by reviewing documents and continuing from last phase
- Phase exit checks ensure completeness before proceeding

### Parking Lot Discipline
- Capture sub-decisions and follow-ups without derailing
- Don't get stuck on implementation details in early phases
- Can create follow-up decision sessions after completion

### Decision Fatigue Management
- Three explicit checkpoints (after Phases 2, 3, 5)
- Acknowledge cognitive load
- Offer breaks without judgment
- Resumability enables multi-session decisions

### Implementation Focus
- Phase 5 is the most critical
- Don't rush through capability assessment
- "Can they do it?" is the key question
- Making decisions "real" requires organizational change management

---

## Cross-Phase Reminders

### General Guidance
- **Assume generic until proven exceptional** - Most problems have patterns
- **Think "right" before "feasible"** - Don't compromise prematurely
- **Two-way doors move fast** - Lower bar for reversible decisions
- **One-way doors need certainty** - Higher bar for irreversible decisions
- **Action generates feedback** - Decisions are tested through implementation
- **Half a loaf vs half a baby** - Know which compromises are acceptable

### Key Questions Throughout
1. "Is this generic or exceptional?" (Phase 1)
2. "What must the solution satisfy?" (Phase 2)
3. "What are the trade-offs?" (Phase 3)
4. "Can they actually do it?" (Phase 5)
5. "How will we know if this works?" (Phase 6)

### Warning Signs
- Jumping to solutions without understanding problem domain
- Accepting first option without evaluating alternatives
- Defining "right" solution with compromises already baked in
- Planning actions without assessing capability
- Missing feedback mechanisms
- Treating all decisions as equally reversible/irreversible

### Drucker's Elements (Integrated Throughout)
1. **Generic vs Exceptional** → Phase 1
2. **Boundary Conditions** → Phase 2
3. **"Right" Solution First** → Phase 2-4
4. **Build in Action** → Phase 5
5. **Build in Feedback** → Phase 6

---

## Integration Points

- **Template**: `templates/Decision Record.md`
- **Output locations**: 
  - Discussion Log: `Capture/`
  - Decision Record: User-specified (often project ADR folder)
- **Related workflows**: 
  - `/research` for investigating frameworks or best practices
  - Design Buddy for technical decisions

---

## Troubleshooting

### User Stuck on Problem Classification
- Use concrete examples from their context
- Ask about past similar situations
- Default to generic unless clearly exceptional

### User Can't Generate Options
- Start with "right" solution from Phase 2
- Ask "what's a smaller version?" and "what's a different approach?"
- Offer to brainstorm alternatives together

### Implementation Seems Impossible
- Break down into smaller actions
- Identify which capability gaps are blockers
- Consider if this reveals wrong option selected (return to Phase 3)

### No Clear Metrics
- Start with success criteria (qualitative)
- Ask "how would you know it's working?"
- Consider both leading and lagging indicators
- Reference [[Metrics]] and [[Metrics in Tension]] concepts

### Session Interrupted
- Both documents contain all work done so far
- Resume by reviewing documents and asking "where were we?"
- Check phase exit conditions to see what's incomplete
- Continue from last incomplete phase

---

## Estimation Guidance (Optional)

If user needs to evaluate costs or probabilities during trade-off evaluation:

**FAIR-ME Scales** (for impact assessment):
- Minimal, Minor, Moderate, Major, Extreme
- Helps quantify "how bad if this goes wrong"

**Work Breakdown**:
- Break large actions into smaller estimable pieces
- Use reference class forecasting (similar past efforts)
- Express as ranges with confidence levels (P50, P80, P90)

**Note**: Don't facilitate through estimation unless user specifically requests it. Mention these exist and move on.
