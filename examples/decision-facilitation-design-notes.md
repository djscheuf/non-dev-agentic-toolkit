---
status: "design"
created: 2026-02-13
---

# Decision Facilitation Workflow - Design Notes

## Intent
Create a step-by-step facilitation workflow for individual decision-makers to work through strategic, operational, and tactical decisions using Drucker's Elements of Decision Making framework. The workflow should help translate decisions into organizational reality.

## Target Audience
- **Individual decision-makers** (not group facilitation)
- **Decision types**: Strategic, operational, tactical
- **Explicitly NOT for**: Technical decisions (redirect to Design Buddy)

## Core Requirements

### 1. Document Production
- Must produce decision artifacts similar to ADRs
- Extended ADR format to capture:
  - Context gathering (incremental)
  - Trade-off evaluations
  - Drucker's decision elements
  - Implementation planning
- Based on template: `templates/Decision Record.md`

### 2. Facilitation Style
- **Step-by-step facilitation** (like Wardley Mapping workflow)
- Progressive document building
- Explicit wait points for user input
- Resumable at any stage
- Check-ins to manage decision fatigue

### 3. Critical Focus: Organizational Implementation
**Most critical aspect**: Translation from decision to organizational action
- Cannot proceed to implementation until trade-offs are evaluated
- Must address:
  - Who needs to know
  - What actions must be taken
  - Who takes those actions
  - What capabilities do they need (training, permissions, resources)
  - How to make the decision "real" in the organization

### 4. Key Decision Elements to Facilitate

#### Early Identification (Before Deep Work)
- **Delegate**: Is this something that should be delegated?
- **Defer**: Does this decision need to be made now?
- **Eliminate**: Can this be automated/eliminated rather than solved?

#### Domain Classification (Cynefin)
- Clear: Best practices, standard procedures
- Complicated: Expert analysis, multiple right answers
- Complex: Experimentation, emergent patterns
- Chaotic: Immediate action required
- Confusion: Break down and identify domains

#### Problem Classification
- **Generic vs Exceptional**: Drucker's first question
  - Generic → needs rule/principle
  - Exceptional → one-off solution
- **One-way vs Two-way door**: Reversibility assessment
  - Two-way door → lower certainty bar, move fast
  - One-way door → higher certainty bar, more analysis

#### Trade-off Evaluation
- Must evaluate **2-3 options minimum**
- Consider positive and negative elements of each
- Timeline constraints (when impact is needed)
- Political realities (after identifying "right" solution)

#### Boundary Conditions
- What specifications must the solution satisfy?
- What are the immovables vs nice-to-haves?
- "Half a loaf vs half a baby" - which compromises are acceptable?

### 5. Supporting Elements (Light Touch)

#### Estimation Frameworks (Optional)
- FAIR-ME scales for impact assessment
- Cost vs probability of success evaluation
- Work breakdown guidance
- **Approach**: Instruct user these exist, don't facilitate through them

#### Decision Fatigue Management
- Check-ins after several steps
- Offer to pause and resume
- Acknowledge cognitive load

## Workflow Structure Pattern

Following successful patterns from:
- `.windsurf/workflows/wardley-mapping.md` - Progressive facilitation with wait points
- `.windsurf/workflows/research.md` - Incremental document updates, resumable
- Design Buddy - Challenge-based exploration

## Key Drucker Elements to Integrate

From Drucker's *Effective Executive*:

1. **Clear realization problem is generic** → establish rule/principle
2. **Definition of boundary conditions** → specifications solution must satisfy
3. **Think through "right" solution** → before compromises/adaptations
4. **Build action into decision** → who knows, what action, who takes it, can they do it
5. **Feedback to test validity** → test against actual events

### Converting Decision to Action
- Who has to know of this decision?
- What action has to be taken?
- Who is to take it?
- What does the action have to be so that people who have to do it _can_ do it?

Supporting questions:
- What kind of people do we have available?
- What can they do?

## Related PKM Resources

### Decision-Making Concepts
- Training in Decision Making - Gaps, Cynefin, decision fatigue
- What is a Decision - Definition, temporal nature, reversibility
- Decentralized Command - Trust, delegation, boundaries
- Multiplicative Impact in Leadership - Scaling through delegation
- Delegation - Goal, boundaries, freedoms framework
- Organizational Change Management - Making change real

### Feedback & Metrics
- Feedback - Action generates feedback, testing hypotheses
- Metrics - Measuring decision effectiveness
- Metrics in Tension - Balanced measurement to prevent gaming

### Decision Frameworks
- OODA Loop - Observe-Orient-Decide-Act, reversibility assessment
- PDCA vs OODA - A Spectrum of Environmental Stability - When to use which framework

## Design Decisions Made

### 1. Scope
- ✅ Individual decision-makers (not group facilitation)
- ✅ Strategic, operational, tactical decisions
- ✅ Explicitly exclude technical decisions → redirect to Design Buddy
- ✅ Solo decision-making focus

### 2. Document Artifacts
- ✅ Must produce decision documents
- ✅ Extended ADR format with Drucker elements
- ✅ Incremental capture during facilitation
- ✅ Template base: ADR format

### 3. Facilitation Approach
- ✅ Step-by-step facilitation (not just framework guidance)
- ✅ Progressive document building
- ✅ Explicit wait points
- ✅ Resumable workflow
- ✅ Decision fatigue check-ins

### 4. Critical Implementation Focus
- ✅ Organizational implementation is THE most critical aspect
- ✅ Cannot proceed to implementation until trade-offs evaluated
- ✅ Must address: who, what, when, can they actually do it
- ✅ Training, communication, systems, propagation

### 5. Early Filters
- ✅ Check for delegate/defer/eliminate before deep work
- ✅ Cynefin domain identification early
- ✅ Generic vs exceptional classification
- ✅ One-way vs two-way door assessment

### 6. Trade-off Evaluation
- ✅ Minimum 2-3 options required
- ✅ Evaluate positive and negative elements
- ✅ Consider timeline constraints
- ✅ Political realities after "right" solution identified

### 7. Estimation (Light Touch)
- ✅ Mention FAIR-ME scales, work breakdown
- ✅ Instruct user these exist
- ✅ Don't facilitate through estimation (secondary concern)

### 8. Decision Fatigue
- ✅ Acknowledge it exists
- ✅ Check-ins after several steps
- ✅ Offer pause/resume capability
- ⚠️ Cannot fully "solve" decision fatigue in workflow

## Confirmed Decisions (2026-02-13)

### 1. Extended ADR Format ✅
Created Decision Record template with sections:
- Context (with Problem Classification subsection)
- Boundary Conditions (Must Have, Nice to Have, Constraints)
- Trade-off Analysis (2-3 options with positives/negatives/feasibility)
- Decision (Chosen approach, rationale, compromises)
- Implementation Plan (Who knows, actions, capability gaps, communication, propagation)
- Feedback & Testing (Success criteria, metrics, review schedule, failure conditions)
- Consequences (Easier/harder, risks)
- Related Decisions & References
- Notes (parking lot)

**Template Location**: `templates/Decision Record.md`

### 2. Workflow Phase Structure ✅
Confirmed phases:
- Phase 0: Initialize & Early Filters (delegate/defer/eliminate)
- Phase 1: Problem Classification (Cynefin, generic/exceptional, reversibility)
- Phase 2: Boundary Conditions & "Right" Solution
- Phase 3: Trade-off Evaluation (2-3 options)
- Phase 4: Feasible Solution (political realities, compromises)
- Phase 5: Implementation Planning (organizational reality)
- Phase 6: Feedback Design (testing against reality)

### 3. PKM Integration ✅
- Prompt for additional context during **initialization**
- Prompt for additional context during **feasibility section** (Phase 4)
- User can reference Seeds/Evergreens/past decisions as needed

### 4. Two-Document Approach ✅
**Document 1: Discussion Log** (Progressive, conversational)
- Captures the facilitation conversation
- Records exploration, questions, insights as they emerge
- Includes parking lot items
- Working document during facilitation
- Location: `Capture/YYYYMMDDHHNN - Decision Discussion - [Topic].md`

**Document 2: Decision Record** (Formal, structured)
- Built progressively during facilitation
- Follows Decision Record template
- Finalized upon completion
- Serves as formal artifact
- Location: User-specified (likely project-specific ADR folder or `Capture/`)

**Integration Approach**:
- Update Decision Record incrementally as phases complete
- Discussion Log captures the "why behind the why"
- Decision Record is the authoritative artifact
- Cross-reference between documents

## Next Steps

1. Confirm workflow phase structure with user
2. Design extended ADR template format
3. Draft workflow with explicit steps and wait points
4. Integrate Drucker elements at appropriate phases
5. Add decision fatigue check-ins
6. Create example walkthrough

## References
- Drucker, Peter. *Effective Executive* - Elements of Decision Making (Ch. 5)
- Boyd, John. OODA Loop framework
- Snowden, Dave. Cynefin Framework
- ADR template pattern
