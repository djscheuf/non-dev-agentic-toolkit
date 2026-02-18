# Using the Research Workflow

The research workflow transforms hours of manual research into a structured, 20-30 minute guided process that produces comprehensive, reusable documentation. This guide shows you how to use the `/research` workflow effectively.

## What is the Research Workflow?

The research workflow is an AI-assisted process that:

1. **Takes your research question** - You describe what you're trying to understand and why
2. **Proposes research topics** - The AI suggests 6-12+ angles to investigate
3. **Conducts systematic research** - Finds authoritative sources and extracts key information
4. **Creates structured documentation** - Produces a comprehensive research note with quotes, summaries, and synthesis

**Time savings**: What typically takes 4-6 hours of manual research becomes a 20-30 minute guided conversation.

## When to Use This Workflow

Use the research workflow when you need to:

- **Understand unfamiliar technologies** before implementing a feature
- **Explore security implications** of a design decision
- **Compare frameworks or approaches** for solving a problem
- **Learn best practices** in an area outside your expertise
- **Gather authoritative sources** on a specific topic
- **Create reference documentation** for future use

## How to Invoke the Workflow

Start by invoking the workflow with a clear description of what you're trying to accomplish:

```
/research I want to understand [TOPIC].

[Optional: Here are specific sources to investigate: URL1, URL2, URL3]
[Optional: Additional context or specific angles to explore]
```

### Good Research Requests

**Specific with context:**
```
/research I want to understand Toyota Kata and Scientific Thinking.

Why: I've heard about continuous improvement but want to understand 
the specific practice of improvement kata and coaching kata.
Value: Looking for concrete techniques that bridge theory to practice.
```

**Focused on a decision:**
```
/research I need to choose between React and Vue for a new project. 
The team has JavaScript experience but no framework experience. 
I want to understand learning curves, ecosystem maturity, and 
long-term maintenance considerations.
```

**Exploring best practices:**
```
/research I'm implementing user authentication for the first time. 
I want to understand current best practices for password storage, 
session management, and multi-factor authentication.
```

### Less Effective Requests

**Too vague:**
```
/research Tell me about React
```

**Too broad:**
```
/research Everything about web security
```

**Better to be specific about what you're trying to accomplish and why.**

## The Research Process

### Step 1: Topic Proposal

After you submit your research request, the AI will:

1. Create a new research note file in your designated location
2. Analyze your request and propose 6-12+ research topics
3. Present these topics for your review

**Your role**: Review the proposed topics and:
- Approve the list as-is
- Add topics the AI missed
- Remove irrelevant topics
- Refine topics to be more specific
- Suggest better search approaches

**Example topic list:**
```
- [ ] Core concepts of Toyota Kata
- [ ] Improvement Kata pattern and steps
- [ ] Coaching Kata pattern and steps
- [ ] Scientific thinking in Toyota Kata
- [ ] Shu Ha Ri and its relationship to kata practice
- [ ] Deming's PDCA cycle and scientific method
- [ ] Relationship to Toyota Production System and lean
- [ ] Practical applications and examples
- [ ] Common mistakes and pitfalls
```

### Step 2: Research Execution

The AI investigates each approved topic:

1. **Searches for authoritative sources** - Official documentation, established experts, reputable publications
2. **Extracts content** in two forms:
   - **Direct quotes** for precision, definitions, and key principles
   - **Bullet summaries** for comprehension and practical guidance
3. **Updates the research note immediately** after each source
4. **Marks topics complete** as it progresses

**This happens automatically** - you can monitor progress as the research note updates in real-time.

### Step 3: Synthesis

After all topics are researched, the AI creates a comprehensive 1,000-2,000 word summary that:

- Synthesizes patterns discovered across sources
- Answers your key questions
- Highlights major insights and themes
- Provides practical implications
- Points to specific sources for claims

**This summary acts as an index** to the detailed findings below, making the research note useful for both quick reference and deep exploration.

## Understanding the Research Note Structure

The completed research note follows [the Research Note template](../templates/Research%20Note.md) and has four main sections:

### 1. Initial Prompt
Your original research request, captured verbatim. This provides context for why the research was conducted.

### 2. Research Summary
A 1,000-2,000 word synthesis that:
- Provides a comprehensive overview
- Highlights key findings and patterns
- Offers practical recommendations
- Points to detailed sections below

**Read this first** to get oriented, then dive into specific sections as needed.

### 3. Topics for Research
A checklist showing:
- All topics investigated (checked when complete)
- Sources reviewed for each topic
- Progress tracking with ✅ emoji

**Example:**
```
- [x] Core concepts of Toyota Kata
  - ✅ [Toyota Kata - Wikipedia](URL) - Captured
- [x] Improvement Kata pattern and steps
  - ✅ [Toyota Kata: A Complete Guide - ProAction International](URL) - Captured
- [x] Coaching Kata pattern and steps
  - ✅ [Toyota Kata: A Complete Guide - ProAction International](URL) - Captured
```

### 4. Research Notes
Detailed findings organized by **themes** (not by source):

```markdown
### Attack Vectors and Threat Categories

From [OWASP File Upload Cheat Sheet](URL):

> "There is no silver bullet in validating user content. 
> Implementing a defense in depth approach is key..."

**Key Points:**
- Extension checking alone is insufficient
- Attackers use double extensions, null bytes, poor regex
- Use allowlist approach rather than blocklist
```

**Organization principle**: Content is grouped by concept/theme, making it easier to find specific information. The same source may appear in multiple sections if it addresses different angles.

## Working with Research Notes

### Reading the Research Note

**For quick reference:**
1. Read the Research Summary
2. Scan the Topics for Research to see what was covered
3. Jump to specific themed sections as needed

**For deep understanding:**
1. Read the Research Summary
2. Work through each themed section in Research Notes
3. Follow source links for additional context
4. Note patterns and connections

### Using Research Notes for Decisions

Research notes provide **fertilizer for your thinking**, not final answers. Use them to:

1. **Inform decisions** - Understand options and trade-offs
2. **Create action plans** - Identify specific steps to take
3. **Write documentation** - Use as source material with proper attribution
4. **Brief team members** - Share comprehensive context quickly
5. **Create decision records** - Document why you chose a particular approach

**Critical distinction**: The research note is raw material. You still need to:
- Interpret findings for your specific context
- Make decisions based on your constraints
- Integrate insights into your own thinking
- Document your reasoning separately

## Examples

### Toyota Kata and Scientific Thinking

See the complete example in [`examples/toyota-kata-scientific-thinking.md`](../examples/toyota-kata-scientific-thinking.md).

**Initial request:**
```
I want to understand Toyota Kata and Scientific Thinking - the specific 
practice of improvement kata and coaching kata, and how they provide 
concrete techniques for continuous improvement.
```

**What the research produced:**
- 10 research topics covering improvement kata, coaching kata, PDCA, Shu Ha Ri progression
- 461 lines of detailed findings with quotes and frameworks
- 2,000+ word synthesis explaining the pattern and philosophy
- Practical implementation guidance and common pitfalls
- Clear connection between theory and practice

**Time invested**: ~30 minutes of guided conversation
**Value delivered**: Comprehensive understanding of a management practice that bridges theory to practice

### Modern Knowledge Work Frameworks

See the complete example in [`examples/modern-knowledge-work-frameworks.md`](../examples/modern-knowledge-work-frameworks.md).

**Initial request:**
```
I want to understand modern frameworks for measuring and optimizing 
knowledge work, including OKRs, Deep Work, cognitive load management, 
remote work practices, and AI augmentation.
```

**What the research produced:**
- 20 research topics covering five interconnected frameworks
- 547 lines of detailed findings with practical techniques
- 2,000+ word synthesis integrating measurement, cognition, remote work, AI, and deliberate practice
- Actionable strategies for self-managing professionals
- Clear framework for modern knowledge work

**Time invested**: ~35 minutes of guided conversation
**Value delivered**: Comprehensive framework for understanding and optimizing knowledge work in the modern era

### Facilitating Wardley Mapping

See the complete example in [`examples/facilitating-wardley-mapping.md`](../examples/facilitating-wardley-mapping.md).

**Initial request:**
```
I want to understand how to facilitate Wardley Mapping sessions effectively, 
including the mapping process, facilitation approaches, and best practices 
for working with groups.
```

**What the research produced:**
- Multiple topics covering mapping process, facilitation approaches, value chains, evolution stages
- 849 lines of detailed findings with quotes and techniques
- Comprehensive synthesis of facilitation best practices
- Three distinct facilitation approaches with implementation guidance
- Practical guidelines for session design and execution

**Time invested**: ~40 minutes of guided conversation
**Value delivered**: Complete guide to facilitating strategic mapping sessions with teams

## Tips for Effective Research

### 1. Be Specific About Your Goal

**Instead of**: "Research React"
**Try**: "I need to choose a framework for a team with JavaScript experience but no framework experience. Compare React and Vue for learning curve, ecosystem maturity, and maintenance."

### 2. Provide Context

Explain:
- What you're trying to accomplish
- Why you need this information
- What constraints you're working with
- What you already know or have tried

### 3. Review Topics Carefully

The topic proposal is your chance to shape the research. Don't just approve - actively refine:
- Add topics the AI missed
- Remove tangents
- Make topics more specific
- Suggest better angles

### 4. Trust the Process

The AI will:
- Find authoritative sources
- Extract relevant information
- Organize findings thematically
- Create a comprehensive synthesis

Your job is to guide the direction, not micromanage the execution.

### 5. Use Research Notes as Starting Points

Research notes are **inputs to your thinking**, not outputs. After research:
- Review findings with your specific context in mind
- Make your own decisions
- Document your reasoning
- Create action plans

## Common Questions

### How long does research take?

**Research execution**: 15-25 minutes depending on topic complexity
**Your active time**: 5-10 minutes (initial request + topic review)
**Total elapsed time**: 20-30 minutes

### How many sources does it investigate?

Typically 2-3 high-quality sources per topic, focusing on:
- Official documentation
- Established experts
- Reputable publications
- Authoritative guides

**Quality over quantity** - better to have deep extraction from excellent sources than shallow coverage of many sources.

### Can I add my own sources?

Yes! Include them in your initial request:

```
/research I want to understand Wardley Mapping facilitation.

Here are specific sources to investigate:
- https://learnwardleymapping.com/
- https://medium.com/wardleymaps/
- https://blog.gardeviance.org/
```

The AI will include these as research topics and may find additional complementary sources.

### What if I need to pause and resume?

Research notes are designed to be resumable:
- Check the "Topics for Research" section
- Unchecked topics haven't been researched yet
- Topics without sources need work
- You can ask the AI to continue where it left off

### Can I use this for non-technical topics?

Absolutely! The workflow works for any research topic:
- Business frameworks and methodologies
- Management practices
- Decision-making approaches
- Process improvement techniques
- Organizational patterns

See examples in the `examples/` directory.

## Next Steps

1. **Try the workflow** with a topic you need to research this week
2. **Review an example** that matches your interest:
   - [`examples/toyota-kata-scientific-thinking.md`](../examples/toyota-kata-scientific-thinking.md) for process improvement
   - [`examples/modern-knowledge-work-frameworks.md`](../examples/modern-knowledge-work-frameworks.md) for productivity
   - [`examples/facilitating-wardley-mapping.md`](../examples/facilitating-wardley-mapping.md) for strategy
3. **Check the template** at `templates/Research Note.md` to see the structure
4. **Explore** [the workflow file](../.windsurf/workflows/research.md) for technical details
5. **Read about the pattern** in `docs/understanding-research-workflow-pattern.md`

## Related Workflows

- `/integrate-research` - Integrate research findings into your knowledge system
- `/article-summary` - Summarize specific articles with consistent formatting
- `/decision-facilitation` - Use research to facilitate decision-making

---

**Remember**: Research notes are fertilizer for your thinking, not the final product. The real value comes from how you integrate and apply the findings to your specific context.
