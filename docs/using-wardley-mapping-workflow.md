# Using the Wardley Mapping Workflow

## What is Wardley Mapping?

Wardley Mapping is a strategic planning technique that visualizes:
- **Who** you're serving (personas and their needs)
- **What** capabilities are required to serve them (value chains)
- **Where** each capability sits on an evolution spectrum (Genesis → Custom → Product → Commodity)
- **How** these elements connect and influence each other

The resulting map reveals strategic opportunities, bottlenecks, and disruption risks that are invisible in traditional planning approaches.

**Learn more about the technique**: https://learnwardleymapping.com/

## Overview of the Workflow

The Wardley Mapping workflow (`.windsurf/workflows/wardley-mapping.md`) enables anyone to facilitate strategic mapping sessions without being a Wardley Mapping expert. This document explains why the workflow is valuable and how it democratizes access to this specialized strategic thinking technique.

## The Challenge: Expert Facilitation is Scarce

Wardley Mapping is powerful but not widely known. Effective facilitation requires:
- Deep understanding of the mapping phases and principles
- Skill in asking the right questions at the right time
- Ability to guide groups through complex strategic conversations
- Experience recognizing patterns and anti-patterns

**The problem**: Most organizations don't have Wardley Mapping experts on staff. When they need strategic mapping, they must either:
- Hire expensive external consultants
- Send staff to extensive training
- Attempt mapping without guidance (often producing poor results)

This creates a bottleneck: valuable strategic thinking is locked behind scarce expertise.

## The Solution: AI-Facilitated Mapping

The Wardley Mapping workflow captures expert facilitation knowledge and makes it available through AI. Instead of needing a human expert, you can:

1. Invoke the workflow with your strategic question
2. The AI guides you through the proven 6-phase process
3. The map builds progressively on an Obsidian Canvas
4. You get expert-level facilitation questions and guidance
5. The result is a strategic map comparable to what an expert would help you create

For more insights about how this workflow was created and the broader pattern of capturing expert knowledge, see [Capturing Expert Workflows](capturing-expert-workflows.md).

## Understanding the Gap: AI vs. Expert

It's important to be realistic about what this workflow provides:

### What the AI Gives You

- **Average-level facilitation**: The workflow captures common patterns, best practices, and proven approaches from multiple sources
- **Structured process**: Step-by-step guidance through all 6 phases with clear exit conditions
- **Pattern recognition**: Identification of common strategic patterns (leverage points, bottlenecks, disruption indicators)
- **Consistent application**: The same quality facilitation every time, no off days

### What a Human Expert Adds

- **Nuanced judgment**: Deep experience recognizing subtle patterns specific to your industry
- **Adaptive questioning**: Ability to read the room and adjust approach based on team dynamics
- **Domain expertise**: Understanding of your specific market context and competitive landscape
- **Creative insight**: Novel strategic moves that go beyond established patterns

### The Value Proposition

The workflow doesn't replace expert consultants for high-stakes strategic decisions. Instead, it:

1. **Enables exploration**: Try Wardley Mapping on smaller decisions before investing in expert help
2. **Builds capability**: Develop internal understanding of the technique through guided practice
3. **Provides baseline**: Create initial maps that experts can then refine and extend
4. **Scales access**: Make strategic mapping available across your organization, not just to executives

Think of it as having a competent facilitator available 24/7, versus waiting for the world-class expert who's booked months in advance.

## Real-World Application

### When to Use This Workflow

**Good fits:**
- Product strategy decisions (build vs. buy, where to invest)
- Technology roadmap planning
- Organizational capability assessment
- Market positioning analysis
- Understanding competitive dynamics

**Less suitable:**
- High-stakes decisions requiring expert validation
- Situations where you need industry-specific strategic plays
- Contexts where team buy-in depends on expert credibility

## Getting Started

### Prerequisites

1. **Obsidian vault**: You need a place to store the canvas files
2. **Strategic question**: Come with a specific decision or area to map
3. **Time commitment**: Plan for 1-2 hours for a complete mapping session

**Skill dependency**: This workflow requires the [Obsidian Canvas skill](../.windsurf/skills/obsidian-canvas.md) to create visual maps. For more information on how skills work, see the Understanding Skills documentation.

### Example Scenario

**Situation**: Your e-commerce team is debating whether to build a custom shopping cart system or buy an off-the-shelf solution.

**Invocation**:
```
I want to think about the strategic implications of building our own shopping cart system 
versus buying one, and what it would take for us to do it better than our competitors.
```

**Without the workflow**: 
- Team argues based on opinions and preferences
- Decision driven by whoever argues most forcefully
- Strategic implications remain invisible

**With the workflow**:
1. Map the user need for "purchase products online"
2. Identify the value chain from cart management down to payment processing, inventory tracking, etc.
3. Position each component on the evolution axis
4. Discover that shopping cart functionality is largely product/commodity (multiple mature solutions exist)
5. Recognize where differentiation opportunities exist vs. where you'd be rebuilding commodity features
6. Decision becomes clear: buy the cart infrastructure, invest custom work in unique customer experience features

The workflow guided you to see what an expert would have recognized immediately: focus custom development where you can differentiate, not on rebuilding commodity capabilities.

### What to Expect

The workflow will:
1. Ask clarifying questions about scope and purpose
2. Create a canvas file in your `Capture/` folder
3. Guide you through 6 phases with explicit checkpoints
4. Update the canvas progressively so you see the map grow
5. Help you identify strategic insights and recommended moves

### Tips for Success

**Be specific about scope**: "Map our entire business" is too broad. "Map our customer onboarding capability" is focused.

**Use the parking lot**: When you identify complex areas, note them for later deep-dives rather than derailing the current map.

**Focus on conversation**: The map is a thinking tool. The strategic insights come from the conversation, not just the artifact.

## Conclusion

The Wardley Mapping workflow makes strategic mapping accessible to non-experts. It won't replace expert consultants for critical decisions, but it:

- **Democratizes** a valuable strategic thinking technique
- **Scales** facilitation capability across your organization
- **Enables** exploration and learning without expensive training
- **Provides** consistent, competent guidance on-demand

Use it when you need strategic clarity but don't have (or can't wait for) expert facilitation. The conversation it enables will reveal insights that remain invisible in traditional planning approaches.

## Complementary Workflows

- **Research workflow** ([`.windsurf/workflows/research.md`](../.windsurf/workflows/research.md)): Use before mapping to gather context on your strategic domain
- **Decision facilitation** ([`.windsurf/workflows/decision-facilitation.md`](../.windsurf/workflows/decision-facilitation.md)): Use after mapping to convert strategic insights into decisions
- **Active partner rule** ([`.windsurf/rules/active-partner.md`](../.windsurf/rules/active-partner.md)): Ensures the AI asks clarifying questions rather than making assumptions

## Related Documentation

- **Workflow file**: [`.windsurf/workflows/wardley-mapping.md`](../.windsurf/workflows/wardley-mapping.md)
- **Supporting skill**: [`.windsurf/skills/obsidian-canvas.md`](../.windsurf/skills/obsidian-canvas.md)
- **Research example**: [`examples/facilitating-wardley-mapping.md`](../examples/facilitating-wardley-mapping.md)
- **Process documentation**: [`docs/capturing-expert-workflows.md`](capturing-expert-workflows.md) (how this workflow was created)

## References

- Learn Wardley Mapping: https://learnwardleymapping.com/
- Wardley Maps Official: https://www.wardleymaps.com/
- IT Revolution Guide: https://itrevolution.com/articles/how-to-wardley-map/
