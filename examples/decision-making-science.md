# Example: Decision Making Science Article Summary

This example demonstrates the basic article-summary workflow applied to a web article, showing how the AI extracts key concepts, organizes them thematically, and creates a structured summary with proper attribution.

## The Request

```
/article-summary

I want to summarize this article about decision-making science:
https://www.nytimes.com/2018/09/01/opinion/sunday/how-make-big-decision.html
```

## The Process

### 1. URL Provided

The user provided a direct link to a web article from the New York Times.

### 2. Content Extraction

The AI used `read_url_content` to fetch the article directly from the web.

### 3. Content Analysis

The AI:
- Identified the core thesis about evidence-based decision-making
- Extracted key research findings from multiple studies
- Organized four distinct techniques into a comparison table
- Found connections to related decision-making concepts
- Generated proper metadata (author, date, tags)

### 4. Summary Generation

Following the article-summary workflow, the AI:
- Captured the core thesis in 2 sentences
- Organized research findings thematically (not by source)
- Used a table for comparing the four techniques
- Included the value model framework details
- Explained why these tools work
- Made connections to existing knowledge

### 5. File Creation

The summary was saved to `Capture/Research/202602081356 - Summary - Decision Making Science.md`

**Time investment:** ~8 minutes of guided conversation

## The Result

---

**title:** "How to Make a Big Decision - Summary"

**tags:** decision-making, cognitive-science, critical-thinking, premortem, scenario-planning

**source:** https://www.nytimes.com/2018/09/01/opinion/sunday/how-make-big-decision.html

**author:** Steven Johnson

**dateCreated:** 2018-09-01

---

### Core Thesis

Decades of multidisciplinary research has evolved beyond Darwin's simple pros-and-cons list, providing evidence-based tools for making complex decisions with long-term consequences. While no algorithm guarantees perfect choices, these techniques help you see situations from new perspectives and weigh options more sophisticatedly.

### Key Research Findings

**The Alternative Generation Problem**

Paul Nutt's organizational decision studies (1980s) revealed a striking pattern: only 15-29% of decision makers actively sought alternatives beyond initial options. Yet decisions involving multiple alternatives succeeded two-thirds of the time, while single-option "whether or not" decisions failed over 50% of the time.

**Key insight**: Transform "whether or not" questions into "which one" questions with multiple paths.

**Diversity Improves Decision Quality**

Samuel Sommers' mock jury research showed racially diverse groups:
- Considered more interpretations of evidence
- Remembered information more accurately  
- Engaged with more rigor and persistence
- Were more likely to reach correct conclusions
- Were paradoxically less confident (more open to being wrong)

Homogeneous groups settle on conclusions too quickly and don't question assumptions.

### Four Evidence-Based Techniques

| Technique | Purpose | How It Works |
|-----------|---------|--------------|
| **Generate Alternatives** | Expand option pool | Diversify decision-making group; actively seek new options beyond initial choices |
| **Scenario Planning** | Test robustness | Create three stories per alternative: things get better, worse, and weird |
| **Premortem Analysis** | Surface blind spots | Imagine the decision failed; work backward to identify causes (30% better at identifying risks) |
| **Value Model** | Systematic evaluation | Weight core values (0-1), grade each scenario (1-100), multiply and sum scores |

### The Value Model Framework

Darwin's approach updated for systematic evaluation:

1. **List core values** (e.g., freedom, companionship, having children, career growth)
2. **Weight each value** (0-1 scale based on importance to you)
3. **Grade each scenario** (1-100) on how well it addresses each value
4. **Calculate**: Multiply grade × weight for each value, sum totals
5. **Compare**: Highest score indicates best alignment with your values

### The Premortem Advantage

Gary Klein's premortem technique leverages "prospective hindsight" - imagining failure has already occurred increases risk identification by 30%. By assuming failure and working backward, teams surface blind spots that forward-thinking planning misses. The technique provides psychological safety for raising concerns and combats hindsight bias.

### Why These Tools Work

The fundamental limitation of pros-and-cons lists: they merely transcribe existing understanding without generating fresh perspectives. As Thomas Schelling observed, "One thing a person cannot do, no matter how rigorous his analysis or heroic his imagination, is to draw up a list of things that would never occur to him."

Complex decisions require imaginative leaps to discover new paths and outcomes. These tools help you see each unique constellation of variables more clearly from multiple angles.

### Connections

This research directly supports several existing frameworks:

- Decision frameworks - The value model provides systematic evaluation methods
- Decision velocity - Understanding decision quality complements velocity metrics
- Advanced thinking frameworks - Premortem analysis and scenario planning align with inversion thinking and second-order thinking

### Related Reading

- Paul Nutt's organizational decision research (1984, later studies)
- Samuel Sommers' jury diversity studies  
- Katherine Phillips' management research on diverse groups (2008)
- Gary Klein's premortem technique
- Steven Johnson's book *Farsighted: How We Make the Decisions That Matter the Most*

## What Made This Work

### Workflow Provided Structure
The article-summary workflow ensured:
- Core thesis captured upfront (1-2 sentences)
- Key points organized thematically, not by source
- Tables used for technique comparisons
- Proper metadata and attribution
- Consistent formatting and quality

### No Skills Required
This was a straightforward web article:
- Standard web scraping worked
- No special tools needed
- No transcript extraction required
- Direct content access

### Quality Standards Met
The summary achieved:
- Clear core thesis
- Research findings with attribution
- Organized comparison table
- Practical frameworks explained
- Connections to related concepts
- 85 lines (within 50-120 target)

## Key Takeaways

1. **Basic workflow handles web articles** - No skills or special tools needed
2. **Thematic organization** - Content organized by concept, not by source
3. **Tables for comparisons** - Four techniques presented clearly
4. **Proper attribution** - Author, source URL, publication date included
5. **Time efficient** - 8 minutes vs. reading and manual note-taking
6. **Quality output** - Professional summary ready for knowledge base

## Related Resources

- [Using the Article Summary Workflow](../docs/using-article-summary-workflow.md) - Basic usage guide
- [Article Summary Workflow](../.windsurf/workflows/article-summary.md) - Workflow implementation
- [Advanced Article Summary with Video](../docs/advanced-article-video-summary.md) - Extending with skills for other content types
