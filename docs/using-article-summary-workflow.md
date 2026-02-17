# Using the Article Summary Workflow

This guide shows you how to use the article-summary workflow to capture and integrate web articles into your knowledge base. For advanced usage including video summaries and combining workflows with skills, see the [Advanced Article Summary with Video](advanced-article-summary-with-video.md) guide.

## What is the Article Summary Workflow?

The article-summary workflow helps you systematically capture insights from web articles, blog posts, and other online content. It creates structured summaries with proper attribution, consistent formatting, and integration into your knowledge system.

**Key benefits:**
- **Consistent capture** - Every summary follows the same structure
- **Proper attribution** - All content links back to original sources
- **Quality standards** - Built-in review process ensures completeness
- **Knowledge integration** - Summaries connect to your existing notes

## Basic Usage: Summarizing Web Articles

The most straightforward use case is summarizing a web article. This example shows the complete process using the Decision Making Science article.

### Step 1: Invoke the Workflow

Start by calling the workflow and providing the article URL:

```
/article-summary

I want to summarize this article about decision-making science:
https://www.nytimes.com/2018/09/01/opinion/sunday/how-make-big-decision.html
```

### Step 2: Confirm Details

The AI will ask clarifying questions:

**AI**: "I'll help you summarize this article. What specific aspects should I emphasize, or should I capture the full scope?"

**You**: "Capture the full scope - I'm interested in the research findings and practical techniques."

**AI**: "Great. I'll suggest a filename following the format `YYYYMMDDHHmm - Summary - {title}`. Does `202602081356 - Summary - Decision Making Science.md` work?"

**You**: "Perfect."

### Step 3: AI Extracts and Analyzes

The AI automatically:
1. Fetches the article content
2. Identifies the core thesis
3. Extracts key findings and techniques
4. Organizes information thematically
5. Creates proper YAML frontmatter

### Step 4: Review the Draft

The AI presents a draft summary following this structure:

```markdown
---
title: "How to Make a Big Decision - Summary"
tags:
  - decision-making
  - cognitive-science
  - critical-thinking
source: "https://www.nytimes.com/..."
author: "Steven Johnson"
dateCreated: 2018-09-01
---

## Core Thesis
[1-2 sentences capturing the main argument]

## Key Research Findings
[Organized findings with clear attribution]

## Four Evidence-Based Techniques
[Table format for easy comparison]

## Relevance to Work
[Connections to your existing notes]
```

### Step 5: File Creation

After your approval, the AI:
- Creates the file in `Capture/Research/`
- Uses the agreed-upon filename
- Ensures proper markdown formatting
- Saves with complete metadata

### Result

You now have `Capture/Research/202602081356 - Summary - Decision Making Science.md` - a structured summary ready for integration into your knowledge system.

**Time investment**: 5-10 minutes of guided conversation

## Beyond Web Articles

While this guide focuses on web articles, the article-summary workflow can be extended to other content types by combining it with skills. Skills teach the AI new capabilities without modifying the workflow itself.

**Examples of what's possible:**
- **YouTube videos** - Using the youtube-transcript-extraction skill
- **Meeting recordings** - Processing VTT files from recorded meetings
- **Podcasts** - With audio transcription skills
- **PDFs** - With document extraction skills

**Learn more:** See [Advanced Article Summary with Video](advanced-article-summary-with-video.md) for detailed examples of combining workflows with skills.

## Quality Standards

### Content Requirements

Every summary should have:
- [ ] **Core thesis** - 1-2 sentences capturing the main argument
- [ ] **Clear organization** - Logical sections with descriptive headings
- [ ] **Proper attribution** - Source URL and author in frontmatter
- [ ] **Key insights** - Main findings or techniques extracted
- [ ] **Connections** - Links to relevant existing notes (when applicable)

### Formatting Requirements

- [ ] **YAML frontmatter** - Complete with title, tags, source, author, date
- [ ] **Consistent structure** - Follows template pattern
- [ ] **Tables for comparisons** - Not nested bullet lists
- [ ] **Code blocks** - Only 1-2 illustrative examples (if applicable)
- [ ] **Target length** - 50-120 lines (not counting frontmatter)

### Attribution Standards

- [ ] **Source URL** - In frontmatter and at top of content
- [ ] **Author attribution** - All credited authors listed
- [ ] **Date created** - Original publication date when available
- [ ] **Content type** - Clear whether article, video, podcast, etc.

## Best Practices

### 1. Be Specific About Focus

**Good**: "Capture the decision-making frameworks and practical techniques"

**Bad**: "Summarize this article"

**Why**: Specificity helps the AI prioritize what matters to you.

### 2. Review Before Saving

Always review the draft summary:
- Check that core thesis is accurate
- Verify key points are captured
- Ensure connections are relevant
- Confirm formatting is consistent

**Why**: The AI's first pass might miss nuances or make incorrect connections.

### 3. Use Consistent Naming

Follow the format: `YYYYMMDDHHmm - Summary - {3-5 word title}.md`

**Examples**:
- `202602081356 - Summary - Decision Making Science.md`
- `202602161612 - Summary - Batman Productivity Protocols.md`
- `202602161537 - Summary - NotebookLM Complete Guide.md`

**Why**: Consistent naming makes summaries easy to find and sort chronologically.

### 4. Connect to Existing Knowledge

During the workflow, the AI searches for relevant existing notes. Guide this:

**Good**: "Check if I have notes on habit formation or systems thinking"

**Bad**: Letting the AI guess what might be relevant

**Why**: You know your knowledge system better than the AI does.

## Common Patterns

### Pattern 1: Article Research

**Use case**: Building understanding of a specific topic

**Process**:
1. Find 2-3 authoritative articles on the topic
2. Summarize each using the workflow
3. Review summaries together
4. Create your own synthesis note

**Example**: Researching decision-making science, productivity systems, and knowledge management tools

### Pattern 2: Content Curation

**Use case**: Building a reference library on a topic

**Process**:
1. Collect relevant articles/videos over time
2. Batch summarize using the workflow
3. Tag consistently for easy retrieval
4. Create index note linking summaries

**Example**: Building a library on AI tools, productivity techniques, or decision frameworks

## Troubleshooting

### Issue: Paywall or Access Restrictions

**Problem**: Article is behind paywall or requires login

**Solution**:
- Provide article text directly (copy/paste)
- Use alternative URL (archive.org, etc.)
- Find similar article on same topic

### Issue: Summary Too Generic

**Problem**: Summary doesn't capture what matters to you

**Solution**:
- Be more specific about focus areas upfront
- Request revision with specific emphasis
- Provide examples of what you want highlighted

## Integration with Knowledge Systems

### The Capture → Process → Integrate Flow

**Capture** (Article Summary Workflow):
- Creates structured summary in `Capture/Research/`
- Consistent format and attribution
- Ready for review

**Process** (Your Work):
- Review the summary
- Identify key insights
- Make connections to existing knowledge
- Decide what to integrate

**Integrate** (Your Knowledge System):
- Create your own notes based on insights
- Link to relevant existing notes
- Update evergreen notes with new understanding
- Apply insights to current projects

### Separation of Concerns

**Research summaries** (in 0-Capture):
- AI-generated content with attribution
- Comprehensive coverage of source material
- Reference material for future use
- "Fertilizer" for your knowledge garden

**Your notes** (in your knowledge system):
- Your synthesis and understanding
- Connections you've made
- Context-specific applications
- "Plants" in your knowledge garden

**Critical distinction**: Don't treat summaries as final knowledge. They're raw material for your thinking.

## Customizing the Workflow

The workflow can be adapted for your specific needs:
- Different output locations
- Alternative metadata schemas
- Team-specific tagging conventions
- Custom quality standards

**How**: Fork the workflow file and modify the steps while keeping the core structure.

**Advanced customization**: For extending to new content types (videos, PDFs, etc.), see [Advanced Article Summary with Video](advanced-article-summary-with-video.md).

## Real-World Example: Decision Making Science

**Source**: NYT Opinion article by Steven Johnson

**Content type**: Web article

**Result**: 85-line summary with:
- Core thesis on evidence-based decision-making
- Research findings from multiple studies
- Four techniques in table format
- Connections to existing decision frameworks

**Time**: ~8 minutes

**View**: `Capture/Research/202602081356 - Summary - Decision Making Science.md`

This example demonstrates the basic workflow applied to a web article, showing how the AI extracts key concepts, organizes them thematically, and creates a structured summary with proper attribution.

## Key Takeaways

1. **Consistent process** - Every summary follows the same structure
2. **Quality standards** - Built-in review ensures completeness
3. **Proper attribution** - Every summary links back to original source
4. **Integration is separate** - Summaries are fertilizer, not final knowledge
5. **Review before saving** - AI's first pass may need refinement
6. **Extensible** - Can be combined with skills for other content types

## Next Steps

Ready to start using the article-summary workflow?

1. **Try it this week** - Summarize a web article you've been meaning to read
2. **Review quality** - Check your summary against the quality standards
3. **Integrate insights** - Don't just collect, actually use the summaries
4. **Explore advanced usage** - See [Advanced Article Summary with Video](advanced-article-summary-with-video.md) for extending to other content types
5. **Share with others** - Help your team benefit from systematic capture

## Related Resources

- [Article Summary Workflow](../.windsurf/workflows/article-summary.md) - The actual workflow implementation
- [Advanced Article Summary with Video](advanced-article-summary-with-video.md) - Combining workflows with skills for video and other content types
- [Understanding Research Workflow Pattern](understanding-research-workflow-pattern.md) - Deeper dive into research patterns

---

**Remember**: The article-summary workflow is a tool for systematic capture. The real value comes from reviewing, connecting, and integrating the insights into your actual knowledge and work. Keep summaries and synthesis separate, and you'll build knowledge that's genuinely useful.
