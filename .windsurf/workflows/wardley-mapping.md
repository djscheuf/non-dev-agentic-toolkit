---
description: Facilitate Wardley Mapping sessions with progressive canvas visualization
auto_execution_mode: 0
---

# Wardley Mapping Facilitation Workflow

This workflow guides you through creating a Wardley Map using an interactive, turn-based approach. The map is built progressively on an Obsidian Canvas, allowing you to see components appear as they're identified.

**Prerequisites:**
- Load the Obsidian Canvas skill before starting
- Ensure you have access to the Wardley Mapping guide

**Invocation Format:**
```
I want to create a Wardley Map for [TOPIC/SYSTEM/CAPABILITY].

[Optional: Initial context about the system, users, or strategic question]
```

## Workflow Overview

This workflow has 6 phases, with several containing iterative loops. The canvas is updated after each significant step, allowing you to see the map grow in real-time.

---

## Phase 0: Initialize Session

### 0a. **acknowledge-and-setup**
- Acknowledge the mapping request
- Ask clarifying questions:
  - "What are you trying to achieve with this map?"
  - "What's the scope - what's in and out of bounds?"
  - "Is this for a specific strategic decision or general exploration?"
- **WAIT** for user response

### 0b. **create-canvas-file**
// turbo
- Create new canvas file:
  - Location: `Capture/`
  - Filename: `YYYYMMDDHHNN - Wardley Map - [Topic].canvas`
- Initialize canvas with evolution zone groups:
  - Genesis zone (x: 0, y: 0, width: 600, height: 1600, color: "1", label: "Genesis")
  - Custom zone (x: 600, y: 0, width: 600, height: 1600, color: "2", label: "Custom")
  - Product zone (x: 1200, y: 0, width: 600, height: 1600, color: "3", label: "Product")
  - Commodity zone (x: 1800, y: 0, width: 600, height: 1600, color: "4", label: "Commodity")
- Add parking lot node:
  - Position: x: 2500, y: 0
  - Size: 400 × 300
  - Text: "## Parking Lot\n\n*Items for deep dive later:*\n"
  - Color: "3"
- Add strategic summary placeholder:
  - Position: x: 2500, y: 400
  - Size: 500 × 800
  - Text: "## Strategic Summary\n\n*To be completed during analysis phase*"
  - Color: "5"
- Save canvas file
- Inform user: "Canvas created at [path]. You can open it in Obsidian to watch the map build."

### 0c. **initialize-state**
- Store in working memory:
  - Canvas path
  - Current phase: "Phase 1"
  - Personas: []
  - Needs: []
  - Components: {}
  - Edges: []
  - Parking lot items: []
  - Next node ID counter: 1

---

## Phase 1: Define Customer/Persona

**Goal:** Identify and document who we're mapping for.

### 1a. **identify-persona**
- Ask: "Who are we talking about? Who is the customer or user for this system?"
- Guide user to think about:
  - Is this a role-based persona (skeletal) or example persona (rich narrative)?
  - What's their role/position?
  - Are there hierarchical relationships (manager/subordinate)?
- **WAIT** for user response

### 1b. **capture-persona-details**
- For each persona mentioned, ask:
  - "What does [persona] value? What are their incentives?"
  - "What drives their decisions? What are their constraints?"
  - "What jobs are they trying to get done?"
- Probe for organizational context if relevant:
  - Hierarchy layer (reporting relationships)
  - Association layer (teams, communities)
  - Value stream position
- **WAIT** for user responses

### 1c. **validate-persona**
- Summarize persona back to user:
  - Name/role
  - Values and incentives
  - Key constraints
  - Jobs to be done
- Ask: "Does this capture [persona] accurately? Anything to add or correct?"
- **WAIT** for confirmation

### 1d. **add-persona-to-canvas**
// turbo
- Read existing canvas
- For each validated persona:
  - Create text node:
    - ID: `persona-[counter]`
    - Position: x: 100 + (personas.length × 450), y: -200
    - Size: 400 × 150
    - Text: Format as:
      ```
      ## [Persona Name]
      
      **Role:** [role]
      **Values:** [values]
      **Incentives:** [incentives]
      **Jobs to be Done:** [JTBD]
      ```
    - Color: "6" (purple)
  - Add to personas array in state
  - Increment counter
- Save canvas
- Inform user: "Added [persona] to canvas above the map."

### 1e. **check-for-more-personas**
- Ask: "Are there other personas we should consider? Multiple personas can share needs."
- **WAIT** for response
- **If YES**: Return to step 1a
- **If NO**: Proceed to Phase 2

### 1f. **phase-1-exit-check**
- Verify exit conditions:
  - [ ] At least one persona clearly defined
  - [ ] Values and incentives documented
  - [ ] Team demonstrates empathy for persona's situation
  - [ ] Persona connects to jobs to be done
- If conditions not met, loop back to clarify
- If met, proceed to Phase 2

---

## Phase 2: Identify and Validate Needs

**Goal:** Discover what the persona is truly trying to achieve (not just their stated solution).

### 2a. **discover-needs**
- Ask: "What is [persona] asking for? What problem are they bringing to you?"
- Guide user to work backwards from solutions:
  - "You started at the end of the argument - work back to the premises"
  - "What comes after 'so that' in this request?"
- **WAIT** for user response

### 2b. **apply-jtbd-framework**
- For each stated need, probe three dimensions:
  - **Functional job:** "What task needs to be accomplished?" (verb + object + context)
  - **Social job:** "How do they want others to perceive them while doing this?"
  - **Emotional job:** "How do they want to feel while doing this?"
- Ask: "Is this a need they would agree with, or are we imposing our assumptions?"
- **WAIT** for user responses

### 2c. **map-value-recipients**
- Ask: "Who uses this capability? Who pays for it? Who decides to use it? Who gets the value?"
- Clarify: "These might all be different people, especially in B2B contexts"
- For each actor identified:
  - "What value do they get that exceeds the effort they put in?"
- **WAIT** for user responses

### 2d. **classify-need-category**
- Help user identify need category (ERG Theory):
  - **Existence:** "Does this help them survive, maintain stability, meet basic needs?"
  - **Relationship:** "Does this help them feel part of a group, gain status, be valued?"
  - **Growth:** "Does this help them develop, improve, or transcend?"
- Note: This helps understand motivation depth
- **WAIT** for user input

### 2e. **validate-need**
- Summarize need back to user:
  - Need statement (capability/outcome, not solution)
  - Functional/Social/Emotional dimensions
  - Value recipients and their value
  - Need category
- Ask: "Would [persona] explicitly agree: 'Yes, that's the end I want to achieve'?"
- **WAIT** for confirmation
- **If NO**: Return to step 2a to refine
- **If YES**: Proceed to add to canvas

### 2f. **add-need-to-canvas**
// turbo
- Read existing canvas
- For each validated need:
  - Create text node:
    - ID: `need-[counter]`
    - Position: x: 200 + (needs.length × 350), y: 200
    - Size: 300 × 120
    - Text: Format as:
      ```
      **Need:** [need statement]
      
      *Functional:* [functional job]
      *Social:* [social job]
      *Emotional:* [emotional job]
      ```
    - Color: "5" (cyan)
  - Create edge from persona to need:
    - ID: `edge-[counter]`
    - fromNode: [persona-id]
    - fromSide: "bottom"
    - toNode: [need-id]
    - toSide: "top"
    - toEnd: "arrow"
  - Add to needs array in state
  - Increment counter
- Save canvas
- Inform user: "Added need '[need]' to canvas, connected to [persona]."

### 2g. **check-for-more-needs**
- Ask: "Are there other needs for this persona? Or needs for other personas?"
- **WAIT** for response
- **If YES**: Return to step 2a
- **If NO**: Proceed to exit check

### 2h. **phase-2-exit-check**
- Verify exit conditions:
  - [ ] Each need expressed as capability/outcome, not solution
  - [ ] Functional, social, emotional dimensions documented
  - [ ] Value recipients mapped for each need
  - [ ] Persona would agree: "Yes, that's what I want to achieve"
- If conditions not met, loop back to clarify
- If met, proceed to Phase 3

---

## Phase 3: Build Value Chains

**Goal:** Map dependencies from needs down to foundational capabilities.

### 3a. **choose-approach**
- Explain to user:
  - "We can build value chains breadth-first (all first-order dependencies, then next layer)"
  - "Or depth-first (follow one chain all the way down, then start next)"
  - "Breadth-first reveals shared dependencies earlier"
- Ask: "Which approach would you prefer?"
- **WAIT** for user choice
- Store approach in state

### 3b. **select-starting-need**
- If breadth-first: Start with first need
- If depth-first: Ask user which need to start with
- **WAIT** if needed for user selection

### 3c. **identify-dependencies** (LOOP)
- For current component (start with selected need):
  - Ask: "What is needed in order to deliver [component]?"
  - Use Three Questions Technique:
    1. "What is this made of?"
    2. "What does it depend on?"
    3. "What depends on it?"
- Guide user to think about:
  - Start with what's most visible to the persona
  - Work backwards through the system
  - Consider transaction flows: "What's being passed around? From where to where?"
- **WAIT** for user response

### 3d. **capture-component-details**
- For each dependency identified:
  - Component name
  - What it depends on (will be filled in later iterations)
  - Relative visibility to persona (high/medium/low)
  - Ask: "Is this important enough to break down further, or is this level of detail sufficient?"
- **WAIT** for user responses

### 3e. **check-for-submap**
- If component is complex, ask:
  - "Does this component need a deep dive? Should we create a submap for it later?"
- If YES: Add to parking lot
- **WAIT** for user decision

### 3f. **add-components-to-canvas**
// turbo
- Read existing canvas
- For each new component:
  - Create text node:
    - ID: `component-[counter]`
    - Position: 
      - X: 300 (temporary, will be positioned in Phase 4 by evolution)
      - Y: Based on visibility:
        - High visibility: 400-600
        - Medium visibility: 800-1000
        - Low visibility: 1200-1400
    - Size: 250 × 80
    - Text: `[Component Name]`
    - Color: none (will be colored by evolution stage later)
  - Create edge from parent to this component:
    - ID: `edge-[counter]`
    - fromNode: [parent-id]
    - fromSide: "bottom"
    - toNode: [component-id]
    - toSide: "top"
    - toEnd: "arrow"
    - label: "depends on"
  - Add to components map in state: {id: {name, visibility, evolution: null, dependencies: []}}
  - Increment counter
- If parking lot items added, update parking lot node text
- Save canvas
- Inform user: "Added [N] components to canvas. Value chain is growing."

### 3g. **check-chain-completeness**
- Ask: "Have we reached foundational elements for this chain? Or are there more dependencies?"
- **WAIT** for user response
- **If more dependencies**: Return to step 3c with new component as current
- **If chain complete**: Proceed to next check

### 3h. **check-for-more-chains**
- If breadth-first: Move to next need or next layer
- If depth-first: Ask "Should we map another need's value chain?"
- **WAIT** for user response
- **If YES**: Return to step 3b
- **If NO**: Proceed to exit check

### 3i. **identify-shared-dependencies**
- Review all components added
- Ask: "Do you see any components that multiple chains depend on? These are strategic leverage points."
- Highlight shared dependencies
- **WAIT** for user observations

### 3j. **phase-3-exit-check**
- Verify exit conditions:
  - [ ] All needs have complete value chains to foundational elements
  - [ ] Shared dependencies identified
  - [ ] No orphaned capabilities (everything traces to a need)
  - [ ] Team can explain each dependency relationship
- If conditions not met, loop back to fill gaps
- If met, proceed to Phase 4

---

## Phase 4: Position on Evolution Axis

**Goal:** Place each component on the Genesis → Custom → Product → Commodity spectrum.

### 4a. **explain-evolution-stages**
- Briefly explain to user:
  - **Genesis:** "I think this would be a good idea" - experimental, novel
  - **Custom:** "Here's my script/checklist" - repeatable but requires customization
  - **Product:** "Let me run this script" - packaged, service guarantees, standardized
  - **Commodity:** "Built into the platform" - ubiquitous, competing on price/service
- Note: "We'll assess each component across 4 dimensions: Ubiquity, Certainty, Market, Failure Tolerance"

### 4b. **select-component-to-position** (LOOP)
- Pick next unpositioned component from state
- If stuck on which to start: "Let's start with components closest to the user needs"

### 4c. **assess-evolution-stage**
- For current component, ask user to assess across 4 dimensions:
  
  **1. Ubiquity** (to applicable market):
  - "How widespread is [component]?"
  - Genesis: Rare, limited availability
  - Custom: Slowly increasing consumption
  - Product: Rapidly increasing ubiquity
  - Commodity: Ubiquitous availability
  
  **2. Certainty**:
  - "How well understood and stable is [component]?"
  - Genesis: Poorly understood, uncertain
  - Custom: Increasing understanding, becoming defined
  - Product: Well-defined, stable specifications
  - Commodity: Completely understood, standardized
  
  **3. Market**:
  - "What's the market maturity for [component]?"
  - Genesis: Forming, uncertain
  - Custom: Growing, competitive advantage emerging
  - Product: Competitive, multiple providers
  - Commodity: Mature, utility-like
  
  **4. Failure Tolerance**:
  - "How acceptable is failure for [component]?"
  - Genesis: Expected, part of experimentation
  - Custom: Moderate, unsurprising but disappointing
  - Product: Increasingly not tolerated
  - Commodity: Not tolerated, must be reliable

- **WAIT** for user assessment

### 4d. **determine-evolution-placement**
- Based on user's assessment, determine stage:
  - Preponderance of evidence across 4 dimensions
  - If unclear: "Let's place it roughly in the middle for now and leave a breadcrumb to refine later"
- Ask: "Does [stage] feel right for [component]?"
- **WAIT** for confirmation
- Store evolution stage in component state

### 4e. **check-for-inertia**
- Ask: "What's preventing [component] from evolving to the next stage?"
- Probe for:
  - **Customer inertia:** "Would customers have to relearn if this evolved?"
  - **Vendor inertia:** "What internal forces keep this from evolving?"
- Document inertia notes in component state
- **WAIT** for user input

### 4f. **update-component-position-on-canvas**
// turbo
- Read existing canvas
- Find component node by ID
- Update X position based on evolution stage:
  - Genesis: x = 50 + random(0-500)
  - Custom: x = 650 + random(0-500)
  - Product: x = 1250 + random(0-500)
  - Commodity: x = 1850 + random(0-500)
- Keep Y position (visibility already set)
- Save canvas
- Inform user: "Moved [component] to [stage] zone on canvas."

### 4g. **check-for-more-components**
- If unpositioned components remain: Return to step 4b
- If all positioned: Proceed to exit check

### 4h. **phase-4-exit-check**
- Verify exit conditions:
  - [ ] Every capability has evolution classification
  - [ ] Team consensus on positioning (or documented disagreements)
  - [ ] Assumptions about positioning are explicit
  - [ ] Inertia identified where relevant
- If conditions not met, loop back to refine
- If met, proceed to Phase 5

---

## Phase 5: Visualize and Analyze

**Goal:** Complete the visual map and identify strategic patterns.

### 5a. **review-map-with-user**
- Inform user: "The map is now visually complete. Please review it in Obsidian."
- Ask: "What patterns do you notice? What surprises you?"
- **WAIT** for user observations

### 5b. **identify-leverage-points**
- Guide user to look for:
  - **Leverage points:** "Which components have multiple value chains depending on them?"
  - Ask: "What would happen if we improved or controlled these components?"
- **WAIT** for user insights
- Document findings

### 5c. **identify-bottlenecks**
- Guide user to look for:
  - **Bottlenecks:** "Which components limit the evolution of dependent components?"
  - Ask: "What's blocked by these components not evolving?"
- **WAIT** for user insights
- Document findings

### 5d. **identify-ripple-effects**
- Guide user to look for:
  - **Ripple effects:** "Which lower components are moving toward commodity?"
  - Ask: "When these foundations commoditize, what becomes possible above them?"
- **WAIT** for user insights
- Document findings

### 5e. **identify-disruption-indicators**
- Guide user to look for:
  - **Disruption indicators:** "Are there new genesis components built on newly-commoditized foundations?"
  - Ask: "Could this disrupt the current value chains? Are we the disruptor or the disrupted?"
- **WAIT** for user insights
- Document findings

### 5f. **update-strategic-summary**
// turbo
- Read existing canvas
- Find strategic summary node
- Update text with findings:
  ```markdown
  ## Strategic Summary
  
  ### Personas and Needs
  [List personas and their key needs]
  
  ### Leverage Points
  [Components with high strategic value]
  
  ### Bottlenecks
  [Constraints to address]
  
  ### Ripple Effects
  [Anticipated cascading changes]
  
  ### Disruption Indicators
  [Threats or opportunities]
  
  ### Key Insights
  [Major observations from the mapping exercise]
  ```
- Save canvas
- Inform user: "Strategic summary updated on canvas."

### 5g. **phase-5-exit-check**
- Verify exit conditions:
  - [ ] Map is visually complete and comprehensible
  - [ ] Team can explain strategic implications
  - [ ] Bottlenecks and leverage points identified
  - [ ] Movement opportunities documented
- If conditions not met, loop back to analyze further
- If met, proceed to Phase 6

---

## Phase 6: Identify Strategic Moves

**Goal:** Determine build/buy decisions and strategic actions.

### 6a. **assess-differentiators**
- For each component, ask:
  - "Is [component] a differentiator for your business?"
  - "Does this make you unique in the market?"
- **WAIT** for user assessment
- Document differentiator status

### 6b. **build-vs-buy-decisions**
- Guide user through decision framework:
  - **Genesis/Custom differentiators:** "Should build - creates competitive advantage"
  - **Genesis/Custom non-differentiators:** "Consider if this should exist at all, or buy if product available"
  - **Product/Commodity:** "Should buy - focus energy elsewhere"
- Ask: "For each component, what's the build/buy decision?"
- **WAIT** for user decisions
- Document decisions

### 6c. **prioritize-advancements**
- Ask: "Which capabilities should we focus on advancing?"
- Guide user to consider:
  - Differentiators in genesis/custom: Invest to maintain advantage
  - Non-differentiators in custom: Push toward product/commodity
  - Bottlenecks: Prioritize evolution to unblock value chains
  - Leverage points: Control or improve for maximum impact
- **WAIT** for user prioritization
- Document priorities

### 6d. **identify-risks**
- Ask: "What disruption risks do you see?"
- Guide user to consider:
  - Competitors building genesis on newly-commoditized foundations
  - Your custom solutions being disrupted by new products
  - Market movements forcing your hand
- **WAIT** for user risk assessment
- Document risks and mitigation strategies

### 6e. **finalize-strategic-summary**
// turbo
- Read existing canvas
- Find strategic summary node
- Add Phase 6 findings:
  ```markdown
  ### Strategic Moves
  
  **Build Decisions:**
  [Components to custom-build with rationale]
  
  **Buy Decisions:**
  [Components to outsource/purchase with rationale]
  
  **Priority Advancements:**
  [Ordered list of capabilities to advance]
  
  **Risk Mitigation:**
  [Identified risks and mitigation strategies]
  ```
- Save canvas
- Inform user: "Strategic moves documented on canvas."

### 6f. **phase-6-exit-check**
- Verify exit conditions:
  - [ ] Clear strategic recommendations with rationale
  - [ ] Build vs. Buy decisions documented
  - [ ] Risk mitigation strategies identified
  - [ ] Team alignment on next moves
- If conditions not met, loop back to clarify
- If met, proceed to completion

---

## Completion

### 7a. **final-review**
- Present complete map to user
- Summarize:
  - Personas and their needs
  - Key components and value chains
  - Evolution positioning
  - Strategic insights
  - Recommended moves
- Ask: "Does this map capture the strategic landscape? Any final adjustments?"
- **WAIT** for user feedback

### 7b. **document-session**
- Inform user of canvas location
- Suggest next steps:
  - "Review parking lot items for potential submaps"
  - "Share map with stakeholders for feedback"
  - "Revisit map quarterly as market evolves"
  - "Use map to guide build/buy decisions"

### 7c. **offer-submap-creation**
- Ask: "Would you like to create submaps for any parking lot items?"
- **WAIT** for user response
- If YES: Can re-run workflow with narrower scope
- If NO: Workflow complete

---

## Key Facilitation Principles

### Turn-Taking Pattern
- Always **WAIT** for user response after asking questions
- Never assume user's answers
- Build incrementally based on user input

### Progressive Visualization
- Update canvas after each significant step
- User can watch map grow in real-time
- Provides visual feedback on progress

### Resumability
- Canvas file persists all work
- Can pause and resume at any phase
- State stored in canvas structure itself

### Parking Lot Discipline
- Capture "deep dive later" items without derailing
- Don't get stuck on one component
- Can create submaps after main map complete

### Validation Gates
- Each phase has explicit exit conditions
- Don't proceed until conditions met
- Loop back to clarify when needed

---

## Cross-Phase Reminders

### General Guidance
- **The map is not the territory** - It's a thinking tool
- **Assumptions must be explicit** - Document what you believe and why
- **People above, capabilities in** - Never put people in the map
- **Everything trends toward commodity** - Unless disrupted
- **The conversation is the value** - Not just the artifact

### Key Questions to Ask
1. "Who are we talking about?" (Persona)
2. "What are they trying to achieve?" (Need)
3. "Is this an imposed need or their actual need?" (Validation)
4. "What is needed to deliver that?" (Value chain)
5. "Where is this on the evolution axis?" (Positioning)
6. "Is this a differentiator for us?" (Strategy)
7. "Should we build or buy this?" (Execution)

### Warning Signs
- Team rushing to solutions without mapping dependencies
- Confusing outputs with needs
- Assuming custom development without checking for products
- Missing shared dependencies across chains
- Not documenting assumptions
- Creating the map but skipping strategic conversation

---

## Integration Points

- **Skill required**: Obsidian Canvas skill (`.windsurf/skills/obsidian-canvas.md`)
- **Reference guide**: Wardley Mapping Phases and Facilitation Guide
- **Output location**: `Capture/` (canvas files)
- **Related workflows**: Can create submaps by re-running with narrower scope

---

## Troubleshooting

### Canvas Not Updating
- Verify canvas file path is correct
- Check JSON structure is valid
- Ensure Obsidian has reloaded the file

### User Stuck on Component Positioning
- Use "Map First" approach: place roughly, refine later
- Leave breadcrumbs for later refinement
- Don't get stuck on precision early

### Too Many Components
- Consider creating submaps for complex areas
- Use parking lot for deep dives
- Focus on strategic components, not exhaustive detail

### Unclear Dependencies
- Use Three Questions Technique
- Ask about transaction flows
- Work backwards from visible to invisible

### Session Interrupted
- Canvas file contains all work done so far
- Can resume by reviewing canvas and continuing from last phase
- Check which components lack evolution positioning or which needs lack value chains
