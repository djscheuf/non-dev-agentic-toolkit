# Using Active Partner: AI as Your Thinking Partner

The **Active Partner** rule transforms your AI assistant from a passive order-taker into an engaged thinking partner that helps you clarify and refine your ideas before investing time and effort in the wrong direction.

## What is Active Partner?

Active Partner is an AI interaction pattern that encourages the AI to:

- **Ask clarifying questions** when your intent is unclear
- **Push back** on instructions that seem problematic
- **Challenge assumptions** that might be wrong
- **Flag contradictions** and impossibilities
- **Propose alternatives** when it sees a better path
- **Explain its interpretation** before taking action

Think of it as a **safety net** that catches unclear or confusing requests before the AI spends significant resources (tokens, time, your attention) pursuing the wrong path.

## Why This Matters

### The Problem: Expensive Mistakes

Without Active Partner, AI assistants tend to:

1. **Assume intent** when instructions are unclear
2. **Execute immediately** even when the request seems problematic
3. **Produce large outputs** that miss the mark
4. **Waste tokens** on work that needs to be redone

**Example of what goes wrong:**
```
You: "Help me prepare for the team meeting"

AI: [Immediately generates a generic meeting agenda that doesn't 
     address your actual needs]
```

### The Solution: Clarify First, Execute Second

With Active Partner, the AI acts as a thinking partner:

```
You: "Help me prepare for the team meeting"

AI: "What are you trying to achieve in this meeting? Are you:
     - Making a decision that needs team input?
     - Sharing information or updates?
     - Solving a specific problem together?
     - Planning or coordinating work?
     
     Understanding your goal will help me suggest the right approach."
```

**Result:** You clarify your actual need, and the AI produces exactly what you want on the first try.

## The Active Partner Rules

The rule set includes these specific behaviors:

### 1. Ask "What are you trying to achieve?"

When your request is unclear, the AI asks about your underlying goal rather than guessing.

**Example:**
```
You: "I need information about OKRs"

AI: "What are you trying to achieve? Are you:
     - Implementing OKRs for the first time?
     - Troubleshooting existing OKR problems?
     - Comparing OKRs to other goal-setting frameworks?
     
     This will help me provide the most relevant information."
```

### 2. Push back on unclear instructions

The AI challenges requests that are ambiguous or seem problematic.

**Example:**
```
You: "Write documentation for everything we do"

AI: "That's quite broad - 'everything' would be overwhelming and 
     not very useful. Can you help me narrow this down?
     
     - What's the most critical knowledge gap right now?
     - Who's the primary audience for this documentation?
     - What specific problem are you trying to solve?"
```

### 3. Challenge assumptions that seem wrong

The AI questions assumptions that might lead you astray.

**Example:**
```
You: "I need an estimate on the cost to get my whole team access to 
      a quality AI productivity tool, so go look at Claude CoWork and 
      get me all the details"

AI: "I'm pushing back on a few assumptions here:
     
     - You've already selected a specific tool without comparing options
     - Cost seems to be your primary criteria
     - You haven't described what problems you're trying to solve
     
     What problems are you trying to solve for your team? Understanding 
     that will help determine which tool features matter most, and get you the right costs for those features."
```

*(Note: There's also something delightfully meta about asking an AI to research competing AI tools, but this example AI response focuses on the more important assumptions about solution-jumping and cost-driven decision-making.)*

### 4. Flag contradictions and impossibilities

The AI points out when your request contains conflicting requirements.

**Example:**
```
You: "I want detailed meeting notes but I can't attend the meeting"

AI: "I see a contradiction here. I can't create detailed notes for 
     a meeting I can't observe. Instead, I can:
     
     - Create a meeting template for someone else to fill in
     - Help you prepare questions to ask after the meeting
     - Draft a follow-up email to gather key takeaways
     
     Which would be most valuable?"
```

### 5. Say "I don't understand what you're seeing"

The AI admits when it lacks context rather than guessing.

**Example:**
```
You: "This doesn't match what I expected"

AI: "I don't understand what you're seeing. Can you help me 
     understand:
     
     - What specifically doesn't match?
     - What were you expecting instead?
     - What context am I missing?"
```

### 6. Disagree and propose alternatives

The AI offers different approaches when it sees a better path.

**Example:**
```
You: "Just summarize this article for me"

AI: "I could do that, but I'm seeing an opportunity for more value.
     Instead of just summarizing, would you like me to:
     
     - Extract key concepts and integrate them with your existing notes?
     - Identify actionable insights specific to your context?
     - Compare this approach to frameworks you're already using?
     
     The /article-summary workflow handles this more systematically."
```

### 7. Explain interpretation before acting

The AI describes what it plans to do before doing it.

**Example:**
```
You: "Help me write a project update"

AI: "Here's my interpretation of what you're asking for:
     
     I'll help you create an update covering:
     - Progress since last update
     - Current status and blockers
     - Next steps and timeline
     - What you need from stakeholders
     
     Is this what you're looking for, or should I adjust the focus?"
```

### 8. Show me your plan

For complex requests, the AI outlines its approach before executing.

**Example:**
```
You: "Help me make a decision about our team structure"

AI: "Here's my plan for facilitating this decision:
     
     1. Understand the decision context and constraints
     2. Identify the options you're considering
     3. Clarify what criteria matter most
     4. Use a decision framework (likely Drucker's approach)
     5. Work through the analysis systematically
     
     Does this approach work for you?"
```

### 9. Create large documents section by section

The AI breaks big tasks into reviewable chunks.

**Example:**
```
You: "Create a comprehensive onboarding guide for new team members"

AI: "Rather than generating the entire guide at once, let me 
     create it section by section so you can review and refine 
     as we go:
     
     1. Welcome and team overview (first)
     2. Key tools and access
     3. Core processes and workflows
     4. Team culture and communication norms
     5. First week checklist
     
     I'll start with the welcome section. Review it, and we'll refine 
     before moving to the next section."
```

## When Active Partner Activates

Active Partner is **always on** in this toolkit. It activates whenever, you ask anything in the chat if you use windsurf. Similar settings can be used for other tools.

## How to Work with Active Partner

### 1. Expect Questions

Don't be surprised when the AI asks clarifying questions. This is the safety net working.

**Good response:**
```
AI: "What are you trying to achieve with this OKR implementation?"

You: "We're switching from annual goals to quarterly OKRs. I need to 
      help my team understand how to write good objectives and key results 
      without making it feel like busywork."
```

### 2. Provide Context

The more context you provide upfront, the better the AI can help.

**Instead of:**
```
"Help me write a project update email"
```

**Try:**
```
"Help me write a project update email. Context: Stakeholders are 
anxious about the timeline. I need to communicate that we're behind 
schedule but making progress, without causing panic or losing their 
confidence in the team."
```

**Tip**: Use the [ROCC Prompt format](https://daniel.scheufler.tech/blog/rocc-it-leverage-ai/) to structure your requests:
- **Role** - What role should the AI take?
- **Objective** - What are you trying to accomplish?
- **Context** - What background information is relevant?
- **Constraints** - What limitations or requirements apply?

This framework helps you provide complete context from the start, reducing the need for clarifying questions.

### 3. Engage in the Dialogue

Active Partner creates a conversation, not a command-response interaction.

**Example dialogue:**
```
You: "I need to improve our team retrospectives"

AI: "What are you trying to achieve? Are you:
     - Getting more participation from quiet team members?
     - Turning insights into actual action items?
     - Making retrospectives feel less repetitive?"

You: "The second one - we identify issues but nothing changes"

AI: "That's helpful. A few more questions:
     - How do you currently track action items?
     - Who's responsible for following up?
     - What happens between retrospectives?"

You: "We write them down but no one owns them, and we forget 
      to check progress"

AI: "Perfect. I'll focus on:
     - Action item ownership and accountability
     - Between-retro tracking systems
     - Making improvements visible to the team
     
     Sound good?"
```

### 4. Push Back When Needed

If the AI's questions or suggestions don't fit, say so.

**Example:**
```
AI: "Should I include detailed technical specifications?"

You: "No, my audience is non-technical stakeholders. 
      Focus on business impact and user benefits."

AI: "Got it - I'll focus on outcomes and value, not technical details."
```

## Benefits of Active Partner

### 1. Saves Time and Tokens

Clarifying intent upfront prevents wasted effort on the wrong output.

**Without Active Partner:**
- Generate wrong output: 10 minutes, 5,000 tokens
- Realize it's wrong: 2 minutes
- Regenerate correctly: 10 minutes, 5,000 tokens
- **Total: 22 minutes, 10,000 tokens**

**With Active Partner:**
- Clarify intent: 2 minutes, 500 tokens
- Generate correct output: 10 minutes, 5,000 tokens
- **Total: 12 minutes, 5,500 tokens**

### 2. Improves Output Quality

When the AI understands your goal, it can tailor the output precisely.

### 3. Builds Better Thinking Habits

Regular interaction with Active Partner helps you:
- Clarify your own thinking
- Articulate goals more clearly
- Identify assumptions you're making
- Consider alternative approaches

### 4. Reduces Frustration

Fewer "that's not what I wanted" moments means less frustration and rework.

## Real-World Example

### Scenario: Improving Team Standup Meetings

**Initial request (unclear):**
```
You: "Our standup meetings aren't working"
```

**Active Partner response:**
```
AI: "What specifically isn't working? Are you experiencing:
     - Meetings running too long?
     - People not participating?
     - Updates not being useful?
     - Blockers not getting resolved?
     
     Understanding the core problem will help me suggest the right solution."
```

**Your clarification:**
```
You: "They take 30 minutes for a 5-person team, and we spend most 
      of the time on details that only matter to 2 people"
```

**Active Partner refinement:**
```
AI: "That's helpful. A few more questions:
     
     - Are people giving status reports or having discussions?
     - Do you have a facilitator or does it flow organically?
     - What happens to the detailed conversations - do they continue after?"
```

**Your final clarification:**
```
You: "People give updates, then others ask questions and it becomes 
      a discussion. No facilitator. The detailed stuff just ends when 
      we run out of time."
```

**Active Partner confirmation:**
```
AI: "Perfect. I'll help you design a standup format that:
     
     1. Keeps updates brief and focused (time-boxing)
     2. Parks detailed discussions for after standup
     3. Ensures blockers get addressed without derailing the meeting
     4. Makes it clear who needs to stay for follow-up discussions
     
     Sound good?"
```

**Result:** You get a practical solution tailored to your specific problem, not generic standup advice.

## Comparison to Passive AI

### Passive AI (Traditional)

```
You: "Help me write a team announcement"

AI: [Generates a generic announcement template with 
     placeholders and formal language]

You: "This doesn't fit our team culture at all..."
```

### Active Partner AI

```
You: "Help me write a team announcement"

AI: "What are you announcing? And what's your team's 
     communication style - formal or casual?"

You: "We're changing our meeting schedule. We're pretty casual."

AI: "Got it. I'll draft something conversational that explains 
     the change and the reasoning. Sound good?"

You: "Perfect"

AI: [Generates announcement matching your team's style and needs]
```

## Tips for Getting the Most from Active Partner

### 1. Don't Rush the Clarification

The time spent clarifying is an investment that pays off in better output.

### 2. Provide "Why" Context

Explaining why you need something helps the AI understand your goal.

**Instead of:** "Tell me about OKRs"

**Try:** "Tell me about OKRs because we're considering switching from annual goals and I need to understand the trade-offs, especially around the quarterly cadence and how it affects planning"

### 3. Be Specific About Constraints

Time, scope, audience, and other constraints help the AI tailor its approach.

**Example:** "I have 30 minutes and need practical guidance, not theory"

### 4. Correct Course Early

If the AI's interpretation is off, correct it immediately rather than letting it continue.

### 5. Use the Dialogue

Active Partner creates a conversation. Engage with it rather than trying to get everything perfect in one request.

## When to Override Active Partner

Sometimes you genuinely want the AI to just execute without questions:

**How to signal this:**
```
"I want you to [specific action] without asking clarifying questions.
Here's all the context: [provide complete context]"
```

**Example:**
```
"Create a team communication guide without asking questions.
Context: New team members struggle with knowing which channel to use
for what. I need a simple reference covering when to use Slack vs email
vs meetings, with examples. Keep it to one page and conversational in tone."
```

The AI will still use Active Partner if it sees genuine problems, but it will execute more directly when you provide complete context.

## Source

The Active Partner pattern comes from the [Augmented Coding Patterns](https://lexler.github.io/augmented-coding-patterns/patterns/active-partner/) collection, adapted for non-technical knowledge work.

## Related Workflows

Active Partner works particularly well with:

- **[Research Workflow](using-the-research-workflow.md)** - Clarifies research scope and focus
- **Decision Facilitation** - Ensures decision context is clear before analysis
- **Wardley Mapping** - Clarifies strategic questions before mapping

## Summary

Active Partner transforms AI from a passive tool into an engaged thinking partner. By asking clarifying questions and pushing back on unclear requests, it acts as a **safety net** that prevents wasted effort on the wrong output.

**Key benefits:**
- Saves time and tokens by clarifying intent first
- Improves output quality through better understanding
- Builds better thinking habits
- Reduces frustration and rework

**How to use it:**
- Expect and welcome clarifying questions
- Provide context about your goals
- Engage in the dialogue
- Correct course early if needed

**Remember:** The few minutes spent clarifying with Active Partner saves hours of rework and produces output that actually meets your needs.

---

**Next Steps:**
1. Try a workflow with Active Partner active (it's always on)
2. Notice when it asks clarifying questions
3. Engage with the dialogue rather than fighting it
4. Observe how the output quality improves with better clarity
