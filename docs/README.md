# Non-Developer Agentic Toolkit Documentation

Welcome to the documentation for the Non-Developer Agentic Toolkit. This toolkit provides AI-assisted workflows designed for knowledge workers, managers, and anyone who wants to leverage AI for research, decision-making, and knowledge management.

## Getting Started

### What is This Toolkit?

This toolkit is a collection of AI workflows that help you:

- **Conduct comprehensive research** in 20-30 minutes instead of 4-6 hours
- **Make better decisions** using structured frameworks
- **Manage knowledge** effectively with AI assistance
- **Facilitate strategic thinking** with proven methodologies
- **Integrate research** into your personal knowledge system

Unlike developer-focused tools, these workflows are designed for **non-technical users** who want to leverage AI for thinking work, not coding work.

### Active Partner: Your AI Thinking Partner

The AI in this toolkit uses the **Active Partner** pattern - it asks clarifying questions and helps refine your thinking before investing time and tokens in the wrong direction. Think of it as a safety net that prevents wasted effort.

**Learn more**: [Using Active Partner](using-active-partner.md) ([source](https://lexler.github.io/augmented-coding-patterns/patterns/active-partner/))

## Core Workflows

### Research Workflow (`/research`)

Transform hours of manual research into structured, comprehensive documentation.

**Use it when you need to:**
- Understand unfamiliar topics quickly
- Explore security or compliance implications
- Compare frameworks or approaches
- Gather authoritative sources on a topic
- Create reference documentation

**Learn more:**
- [Using the Research Workflow](using-the-research-workflow.md) - Practical guide
- [Understanding the Research Workflow Pattern](understanding-research-workflow-pattern.md) - Deep dive into the pattern
- [File Upload Security Research Example](../examples/file-upload-security-research.md) - Complete example

**Quick start:**
```
/research I want to understand [TOPIC].

[Optional context about what you're trying to accomplish and why]
```

### Other Workflows

Additional workflows are available in the `.windsurf/workflows/` directory:

- `/article-summary` - Summarize web articles with consistent formatting
- `/decision-facilitation` - Facilitate decision-making using structured frameworks
- `/integrate-research` - Integrate research findings into your knowledge system
- `/wardley-mapping` - Facilitate Wardley Mapping sessions
- `/daily-reflection` - Reflect on your day
- `/daily-summary` - Create daily summaries

See individual workflow files for detailed usage instructions.

## Documentation Structure

```
docs/
├── README.md (you are here)
├── using-active-partner.md
├── using-the-research-workflow.md
└── understanding-research-workflow-pattern.md

examples/
├── README.md
├── toyota-kata-scientific-thinking.md
├── modern-knowledge-work-frameworks.md
└── facilitating-wardley-mapping.md

templates/
└── Research Note.md

.windsurf/workflows/
├── research.md
├── article-summary.md
├── decision-facilitation.md
└── ... (other workflows)
```

## Key Concepts

### AI Research vs. Human Research

**AI Research = Summarization**
- Transforms scattered information into structured summaries
- Finds and extracts content from multiple sources
- Organizes information thematically

**Human Research = Integration**
- Integrates new information with existing knowledge
- Makes connections across domains
- Applies context and judgment

**The toolkit handles AI research. You handle integration.**

### Fertilizer vs. Plants

**Research notes are fertilizer** - exterior content that enriches your knowledge garden but isn't the garden itself.

**Your notes are plants** - your thoughts, observations, and connections that grow from the fertilizer.

**Keep them separate** to avoid the machine-feeding-itself problem where AI summaries become inputs to future AI work, degrading quality over time.

## Getting the Most Value

### 1. Start with Real Needs

Use workflows for actual work, not practice exercises. The best learning happens when you have a real research question or decision to make.

### 2. Review and Refine

When workflows propose topics or approaches, actively refine them. Don't just approve - add, remove, and adjust to match your specific needs.

### 3. Integrate, Don't Just File

After research, schedule time to integrate findings. Read through the research note, make connections to what you know, and create your own synthesis.

### 4. Build Your Practice

These workflows are tools that get better with practice. You'll develop better question-asking skills and learn to guide the AI more effectively.

### 5. Share and Collaborate

Research notes can be shared with teams. Use them to build shared understanding and reduce duplicate research efforts.

## Examples and Case Studies

### Toyota Kata and Scientific Thinking

**Scenario**: Understanding continuous improvement practices and how to coach teams through systematic problem-solving.

**Research produced**:
- 10 topics covering improvement kata, coaching kata, PDCA, Shu Ha Ri progression
- 461 lines of detailed findings with quotes and frameworks
- 2,000+ word synthesis explaining the pattern and philosophy
- Practical implementation guidance and common pitfalls

**Time**: ~30 minutes of guided conversation

**See**: [Complete example](../examples/toyota-kata-scientific-thinking.md)

### Modern Knowledge Work Frameworks

**Scenario**: Understanding how to measure and optimize knowledge work in the modern era.

**Research produced**:
- 20 topics covering OKRs, Deep Work, cognitive load, remote work, AI augmentation, deliberate practice
- 547 lines of detailed findings with practical techniques
- 2,000+ word synthesis integrating five interconnected frameworks
- Actionable strategies for self-managing professionals

**Time**: ~35 minutes of guided conversation

**See**: [Complete example](../examples/modern-knowledge-work-frameworks.md)

### Facilitating Wardley Mapping

**Scenario**: Learning how to facilitate strategic mapping sessions with teams.

**Research produced**:
- Multiple topics covering mapping process, facilitation approaches, value chains, evolution stages
- 849 lines of detailed findings with quotes and techniques
- Comprehensive synthesis of facilitation best practices
- Three distinct facilitation approaches with implementation guidance

**Time**: ~40 minutes of guided conversation

**See**: [Complete example](../examples/facilitating-wardley-mapping.md)

### More Examples Coming Soon

We're building a library of examples showing different use cases:
- Framework comparisons
- Domain learning
- Security reviews
- Process improvement research
- Strategic planning

## Adapting to Your Context

### For Individual Contributors

- Research notes in personal knowledge system
- Integration through personal notes
- Focus on immediate application

### For Managers and Leaders

- Research notes in team knowledge base
- Integration through team discussions
- Focus on decision-making and strategy

### For Teams

- Shared research notes in team repository
- Integration through documentation and training
- Focus on consistent practices and shared understanding

## Best Practices

### For Research

1. **Be specific** - Describe what you're trying to accomplish and why
2. **Provide context** - Explain constraints and what you already know
3. **Review topics carefully** - Shape the research direction actively
4. **Trust the process** - Let AI handle the execution
5. **Integrate findings** - Don't just file research notes away

### For Knowledge Management

1. **Separate fertilizer from plants** - Keep research notes separate from your knowledge
2. **Attribute everything** - Every quote and summary needs a source
3. **Organize by theme** - Group by concept, not by source
4. **Focus on sufficiency** - 2-3 excellent sources beat 10 shallow ones
5. **Make it resumable** - Update notes incrementally as you research

### For Teams

1. **Share research notes** - Build collective knowledge
2. **Document decisions** - Link research to decision records
3. **Create onboarding materials** - Use research notes for training
4. **Establish conventions** - Agree on where research notes live
5. **Review and refine** - Improve workflows based on team feedback

## Troubleshooting

### Research feels too shallow
- Refine topics to be more specific
- Request investigation of technical documentation
- Add specific authoritative sources

### Research goes off track
- Review proposed topics more carefully
- Remove tangential topics before research begins
- Provide more context in initial request

### Can't find time to integrate
- Schedule integration time immediately after research
- Start with smaller research topics
- Focus on immediate application

### Research notes pile up
- Enforce separation: research notes are fertilizer, not plants
- Create separate location for integrated knowledge
- Make integration a required step

## Contributing

This toolkit is designed to evolve based on real usage. If you:

- Develop new workflows
- Find better patterns
- Create useful examples
- Discover improvements

Please share them! The best workflows emerge from real needs and evolve with practice.

## Related Resources

### From This Repository

- [Using Active Partner](using-active-partner.md) - AI as your thinking partner
- [Using the Research Workflow](using-the-research-workflow.md)
- [Understanding the Research Workflow Pattern](understanding-research-workflow-pattern.md)

### External Resources

- [Agentic Dev Ecosystem Template](https://github.com/djscheuf/agentic-dev-ecosystem-template) - Developer-focused version of this toolkit
- Personal Knowledge Management resources (coming soon)
- Decision-making frameworks (coming soon)

### All Examples

- [Toyota Kata and Scientific Thinking](../examples/toyota-kata-scientific-thinking.md) - Process improvement and coaching
- [Modern Knowledge Work Frameworks](../examples/modern-knowledge-work-frameworks.md) - Productivity and measurement
- [Facilitating Wardley Mapping](../examples/facilitating-wardley-mapping.md) - Strategic planning facilitation

## Next Steps

1. **Read** [Using the Research Workflow](using-the-research-workflow.md)
2. **Review** an example that matches your interest:
   - [Toyota Kata](../examples/toyota-kata-scientific-thinking.md) for process improvement
   - [Knowledge Work](../examples/modern-knowledge-work-frameworks.md) for productivity
   - [Wardley Mapping](../examples/facilitating-wardley-mapping.md) for strategy
3. **Try** the `/research` workflow with a real research question
4. **Integrate** your findings into your own notes
5. **Refine** your approach based on experience

---

**Remember**: These workflows are tools for compression and organization. The real value comes from your integration and application of the findings. Keep fertilizer and plants separate, and you'll build knowledge that's actually yours.
