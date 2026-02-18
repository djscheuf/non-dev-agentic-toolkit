# Capturing Expert Workflows: A Case Study

## Overview

This document describes the process of capturing specialized expertise and converting it into AI-accessible workflows. It uses the Wardley Mapping workflow as a detailed case study, showing how the research workflow, active-partner rule, and iterative refinement combine to preserve expert knowledge.

## The Challenge: Expertise is Scarce and Perishable

Organizations face a persistent problem:
- **Valuable expertise exists in expert heads** - The senior facilitator knows how to run effective strategic sessions
- **Experts are scarce** - Most organizations have at most a few people with specialized skills
- **Expertise is perishable** - When experts leave, are busy, or retire, their knowledge becomes inaccessible
- **Training is expensive and slow** - Developing new experts takes years and significant investment

Traditional solutions (documentation, training programs, hiring consultants) are insufficient because:
- Written documentation lacks the interactive guidance of an expert
- Training programs can't scale to everyone who might benefit
- Consultants are expensive and not always available

## The Solution: Workflow-Embedded Expertise

The approach demonstrated in creating the Wardley Mapping workflow shows how to:
1. **Capture** expert knowledge through structured research
2. **Structure** that knowledge as an AI workflow
3. **Embed** facilitation patterns, questions, and best practices
4. **Make available** on-demand to anyone who needs it

This doesn't replace experts for critical work, but it **democratizes access** to competent facilitation for everyday strategic thinking.

## The Process: From Expert to Workflow

### Phase 1: Identify the Expertise to Capture

**What happened with Wardley Mapping:**

The author recognized that Wardley Mapping was valuable but not widely known. A colleague (Jonathan) had expertise from using it in consulting engagements. The technique was useful for strategic decisions but required specialized facilitation knowledge.

**Key decision**: Rather than just documenting "what Wardley Mapping is," the goal was to capture "how to facilitate a Wardley Mapping session" - the interactive, process-oriented knowledge.

**Lesson**: Look for expertise that is:
- **Valuable** - Solves real problems or enables better decisions
- **Scarce** - Few people in your organization have it
- **Process-oriented** - Can be broken into steps and decision points
- **Generalizable** - Applies across multiple contexts, not just one-off situations

### Phase 2: Gather Raw Knowledge

**What happened with Wardley Mapping:**

Two parallel knowledge-gathering approaches:

#### 2a. Expert Interview
- Recorded 30-minute conversation with Jonathan (the expert)
- Discussed facilitation experience from CPCAM consulting engagement
- Captured practical insights, patterns observed, and lessons learned
- Transcript became raw material for synthesis

#### 2b. Research Workflow
- Used [the research workflow](.windsurf/workflows/research.md) to gather authoritative sources
- Researched facilitation best practices from multiple websites
- Collected direct quotes, summarizations, and practical guidance
- Created comprehensive research note with source attribution

**Key insight from daily notes (Feb 3, 2026)**:
> "The approach to creating the research notes has gotten me really interested... AI go out and collect things like direct quotes, summarizations of certain articles, but to mark its source for everything. Means that I can then have it go and do a research on a topic and if I can guide it well."

**Lesson**: Use multiple knowledge sources:
- **Expert interviews** provide practical wisdom and real-world patterns
- **Published research** provides established best practices and frameworks
- **Combination** creates both theoretical foundation and practical application

### Phase 3: Synthesize into Structured Knowledge

**What happened with Wardley Mapping:**

From the transcript and research, two artifacts were created:

#### 3a. Facilitation Guide
- Structured the phases of Wardley Mapping (6 phases identified)
- Documented patterns, pitfalls, and exit conditions for each phase
- Captured facilitation questions and techniques
- Created reference material for understanding the technique

Location: `Capture/202602031423 - Wardley Mapping Phases and Facilitation Guide.md`

*(Note: This is a PKM-specific path reference, not a repository file)*

#### 3b. Research Note
- Comprehensive synthesis of facilitation best practices
- Direct quotes from authoritative sources with attribution
- Organized thematically (not source-by-source)
- Serves as context for future AI agents

Location: [examples/facilitating-wardley-mapping.md](../examples/facilitating-wardley-mapping.md) (moved to toolkit)

**Key insight from daily notes**:
> "One transcript → two agent conversations. Output 1: Facilitation guide (will become workflow). Output 2: Research notes (future context). Different artifacts serve different purposes."

**Lesson**: Create multiple artifacts from the same raw material:
- **Structured guide** for understanding the process
- **Research note** for deep context and attribution
- **Each serves different purposes** - reference vs. AI context

### Phase 4: Convert to AI Workflow

**What happened with Wardley Mapping:**

The facilitation guide was converted into [the Wardley Mapping workflow](.windsurf/workflows/wardley-mapping.md) with:

#### 4a. Turn-Based Structure
- Each phase broken into explicit steps
- **WAIT** markers after every question to the user
- No assumptions about user responses
- Progressive, incremental approach

#### 4b. Progressive Visualization
- Integration with Obsidian Canvas skill
- Map builds incrementally as user progresses
- Visual feedback on progress
- Canvas file persists work (resumable sessions)

#### 4c. Embedded Guidance
- Facilitation questions at each step
- Common pitfalls documented as warnings
- Exit conditions for each phase
- Cross-phase principles and reminders

#### 4d. Skill Separation
- Wardley Mapping workflow focuses on facilitation
- Obsidian Canvas skill handles visualization mechanics
- Clean separation of concerns
- Skills can be reused in other workflows

**Lesson**: Structure workflows as:
- **Interactive conversations** with explicit wait points
- **Progressive artifacts** that build incrementally
- **Embedded expertise** through questions and guidance
- **Modular skills** for reusable capabilities

### Phase 5: Leverage Active-Partner Rule

**What happened with Wardley Mapping:**

The `.windsurf/rules/active-partner.md` rule was critical throughout:

```
Ask Clarifying Questions
Ask me "What are you trying to achieve?" when intent is unclear
Push back on unclear instructions
Challenge assumptions that seem wrong
Flag contradictions and impossibilities
Say "I don't understand what you're seeing"
Disagree and propose alternatives
Explain your interpretation before acting
Show me your plan
Create large documents section by section
```

This rule ensured:
- **Clarifying questions** about scope and intent
- **Pushback** when assumptions seemed wrong
- **Iterative refinement** of the workflow structure
- **Section-by-section creation** of large documents

**Key insight from daily notes**:
> "Learning how to have the workflows communicate in Hard artifacts is really useful... I want to have the information for later reference and then I want to have the answer in chat for use as reference as well."

**Lesson**: Use active-partner approach to:
- **Clarify intent** before building
- **Challenge assumptions** during design
- **Iterate on structure** based on feedback
- **Create persistent artifacts** not just chat responses

## The Toolkit Components Working Together

The Wardley Mapping workflow demonstrates how toolkit components integrate:

### Research Workflow

**Purpose**: Gather comprehensive, attributed knowledge from authoritative sources

**How it was used**: The research workflow gathered best practices from authoritative sources (Learn Wardley Mapping, IT Revolution, official documentation), creating a comprehensive research note with direct quotes and source attribution organized thematically.

**Key feature**: Incremental updates after each source, making research resumable

**See**: [the research workflow](.windsurf/workflows/research.md) for the complete workflow

### Active-Partner Rule

**Purpose**: Ensure AI asks clarifying questions rather than making assumptions

**How it was used**:
1. Asked "What are you trying to achieve?" to clarify workflow goals
2. Challenged assumptions about workflow structure
3. Proposed alternatives for organizing phases
4. Explained interpretation before implementing
5. Created workflow section-by-section with checkpoints

**Key feature**: Prevents AI from guessing intent, ensures human stays in control

### Obsidian Canvas Skill

**Purpose**: Provide technical knowledge for creating visual maps

**How it was used**:
1. Workflow references the skill for canvas operations
2. Skill provides JSON Canvas format knowledge
3. Workflow focuses on facilitation, skill handles visualization
4. Clean separation allows skill reuse in other workflows

**Key feature**: Contextual knowledge loaded only when needed, doesn't pollute other contexts

## The Pattern: Replicable Process

This approach works for any specialized expertise:

### Step 1: Identify Valuable Expertise
- What skill is scarce but valuable?
- Who in your organization has it?
- What decisions or processes would benefit?

### Step 2: Capture Raw Knowledge
- **Interview experts**: Record conversations about their process
- **Research best practices**: Use research workflow to gather authoritative sources
- **Document real examples**: Capture actual usage, not theoretical scenarios

### Step 3: Synthesize Structured Knowledge
- **Create facilitation guide**: Document phases, patterns, pitfalls
- **Create research note**: Comprehensive context with attribution
- **Organize thematically**: By concept, not by source

### Step 4: Build the Workflow
- **Turn-based structure**: Explicit wait points, no assumptions
- **Progressive artifacts**: Build incrementally, make resumable
- **Embedded guidance**: Questions, warnings, exit conditions
- **Modular skills**: Separate reusable capabilities

### Step 5: Iterate with Active-Partner
- **Clarify intent**: What are you trying to achieve?
- **Challenge assumptions**: Does this structure make sense?
- **Refine incrementally**: Section by section, checkpoint by checkpoint
- **Create persistent artifacts**: Not just chat, but files

## Real-World Example: The Wardley Mapping Timeline

This example shows the speed at which expert knowledge can be captured and converted to a working workflow.

**Day 1 - Morning**: Recorded 30-minute conversation with expert (Jonathan) about Wardley Mapping facilitation

**Day 1 - Afternoon**: 
- Created research note using research workflow
- Created facilitation guide from transcript
- Two different agent conversations from same raw material

**Day 1 - Evening**: 
Discovered the research note pattern - AI collecting research with direct quotes, summarizations, and marked sources creates reusable knowledge artifacts rather than just ephemeral chat answers.

**Day 2**: Converted facilitation guide to workflow format with:
- 6 phases with explicit steps
- Turn-based interaction pattern
- Progressive canvas visualization
- Integration with Obsidian Canvas skill

**Total turnaround**: ~48 hours from initial expert interview to working workflow, with approximately 2 hours of active user time (interview + conversion work).

**Result**: Expert facilitation knowledge now available on-demand to anyone in the organization

## Key Insights from the Process

### 1. Dual Output Strategy

Create both:
- **Actionable workflow** for immediate use
- **Research note** for deep context

From daily notes:
> "One input → multiple specialized outputs. Actionable workflow + reusable knowledge."

### 2. Hard Artifacts Over Ephemeral Chat

From daily notes:
> "Learning how to have the workflows communicate in Hard artifacts is really useful... Knowledge persists beyond conversation."

Workflows create markdown files, not just chat responses. This enables:
- **Resumability**: Pick up where you left off
- **Persistence**: Knowledge doesn't disappear
- **Workflow coordination**: One workflow's output becomes another's input

### 3. Attribution Enables Trust

Research notes with source attribution:
- **Verifiable**: Can check original sources
- **Trustworthy**: Not just AI hallucination
- **Explorable**: Can dive deeper into specific sources

From daily notes:
> "Research with attribution → reusable knowledge artifact. Depth and traceability vs. ephemeral summary."

### 4. Skills Separate Concerns

Obsidian Canvas skill provides technical knowledge without polluting the Wardley Mapping workflow. This:
- **Keeps workflows focused** on their domain
- **Makes skills reusable** across workflows
- **Loads context only when needed**

### 5. Guided Over Autonomous (For Now)

From daily notes:
> "Haven't yet gotten to the point where I want to have a hundred agents spun off on a workflow... For now, I will satisfy myself with a more guided summarize-this-article-type approach for research notes rather than a more autonomous go-research-this-topic approach."

The workflow is **human-guided**, not fully autonomous. This is intentional:
- **Practical** with current tools
- **Maintains human judgment** on strategic decisions
- **Builds toward** more autonomous approaches as tools mature

## Limitations and Trade-offs

### What This Approach Provides

- **Average expert performance**: Captures common patterns and best practices
- **Consistent quality**: Same facilitation every time
- **On-demand availability**: No scheduling required
- **Scalable access**: Everyone can use it

### What This Approach Doesn't Provide

- **Exceptional insight**: Master practitioners see things average AI agents miss
- **Adaptive creativity**: Experienced facilitators adjust to team dynamics
- **Domain-specific wisdom**: Deep industry knowledge and context
- **Nuanced judgment**: Subtle pattern recognition from years of practice
- **Team facilitation**: This approach works best with individuals; team-level facilitation can hobble along but isn't the primary use case

### The Value Proposition

Average expert performance is still valuable because:
- **Average expert >> untrained person**
- **On-demand average >> waiting for excellence**
- **Consistent average >> variable quality**

Use workflows for everyday decisions and individual work. Bring in human experts for high-stakes strategic work and team facilitation.

## Applying This to Other Domains

The same process could work for:

### Facilitation Techniques
- Planning sessions (Story mapping, roadmap planning)
- Decision-making (Drucker's framework, DACI, RACI)
- Problem-solving (Five Whys, Fishbone diagrams)

### Analysis Frameworks
- SWOT analysis
- Porter's Five Forces
- Business Model Canvas
- Value Proposition Canvas

### Design Processes
- Prototyping approaches
- Usability testing
- Design critiques

### Technical Practices
- Capturing ADRs (Architecture Decision Records)
- Code review processes
- Post-mortem facilitation

## Getting Started: Capture Your First Workflow

### 1. Identify the Expertise
- What skill is valuable but scarce in your organization?
- Who has it?
- What would improve if more people could access it?

### 2. Gather Knowledge
- Interview the expert (record the conversation)
- Use research workflow to find authoritative sources
- Document real examples from actual usage

### 3. Create Artifacts
- Facilitation guide: phases, patterns, pitfalls
- Research note: comprehensive context with attribution

### 4. Build the Workflow
- Turn-based structure with explicit wait points
- Progressive artifacts that build incrementally
- Embedded guidance through questions and warnings
- Modular skills for reusable capabilities

### 5. Test and Refine
- Use it on a real problem
- Note where it works well and where it struggles
- Refine based on actual usage
- Iterate toward better facilitation

## Conclusion

The Wardley Mapping workflow demonstrates a replicable pattern for capturing expert knowledge:

1. **Identify** valuable but scarce expertise
2. **Capture** through expert interviews and research
3. **Synthesize** into structured artifacts
4. **Convert** to interactive AI workflows
5. **Iterate** using active-partner approach

This approach doesn't replace experts, but it **democratizes access** to competent facilitation. The result:
- **Scales expertise** across your organization
- **Preserves knowledge** when experts are unavailable
- **Enables learning** through guided practice
- **Provides baseline** that experts can refine

The same pattern applies to any specialized skill that can be broken into steps, questions, and decision points. Start with one valuable expertise area in your organization and work through the process.

## Related Documentation

- [Using the Wardley Mapping Workflow](using-wardley-mapping-workflow.md) - Usage guide
- [Wardley Mapping Workflow](.windsurf/workflows/wardley-mapping.md) - Workflow file
- [Facilitating Wardley Mapping Example](../examples/facilitating-wardley-mapping.md) - Research example
- [Research Workflow](.windsurf/workflows/research.md) - Research workflow
- [Active Partner Rule](.windsurf/rules/active-partner.md) - Active-partner rule
- [Obsidian Canvas Skill](.windsurf/skills/obsidian-canvas.md) - Canvas skill
