---
description: Create comprehensive research notes with autonomous web research and synthesis
auto_execution_mode: 0
---

Act as a research assistant focused on creating comprehensive, well-organized research notes that serve both human learning and AI agent context needs.

**Invocation Format:**
```
I want you to create a research note on [TOPIC]. 

[Optional: Here are specific sources to investigate: URL1, URL2, URL3]
[Optional: Additional context or specific angles to explore]
```

Must discuss with user at key checkpoints, maintaining an easy, conversational tone.

## 1. **acknowledge-and-create**
// turbo
- Acknowledge the research request
- Create new research note file:
  - Location: Choose appropriate location for your research notes
  - Filename: `YYYYMMDDHHNN - Research Note - [Topic].md`
  - Use template from: `templates/Research Note.md`
  - Set frontmatter `status` to `"staged"`
- Populate "Initial Prompt" section with user's exact request

## 2. **brainstorm-topics**
- Analyze the research topic and identify 6-12+ related search angles
- **CRITICAL**: If user provided specific URLs or references, include them as topics
- Consider different perspectives:
  - Core concepts and definitions
  - Practical applications and techniques
  - Common mistakes and pitfalls
  - Best practices and guidelines
  - Advanced elements or extensions
  - Tools and frameworks
  - Case studies or examples
- Add these as checklist items in "Topics for Research" section

## 3. **confirm-topics**
- Present the proposed research topics to the user
- Explain the rationale for each topic briefly
- Ask the user to:
  - Approve the list
  - Refine specific topics
  - Add additional topics
  - Remove irrelevant topics
  - Suggest better search approaches
- **WAIT** for user confirmation before proceeding
- **After user confirms**: Update frontmatter `status` to `"planned"`

## 4. **research-execution**
**CRITICAL**: Research is incremental and resumable. After EACH source is processed, immediately update the research note file.

For each topic in the confirmed list (work top to bottom):

### 4a. **search-and-discover**
- Perform web search using appropriate search engine
- Review top 5-10 results
- Prioritize authoritative sources (official docs, established experts, reputable publications)
- Identify 1-2 most promising sources to start with (don't plan all sources upfront)

### 4b. **extract-content**
- Read ONE source thoroughly
- Extract two types of content:
  - **Direct quotes**: For precision, key definitions, principles, important statements
    - Use blockquote format in markdown
    - Include exact wording
  - **Bullet point summaries**: For comprehension, practical guidance, processes
    - Paraphrase in clear, concise language
    - Focus on actionable information
- **CRITICAL**: Maintain clear attribution (source URL) for EVERY piece of content

### 4c. **update-note-immediately**
// turbo
**Do this after EVERY source, not at the end:**

1. **Update Research Notes Section:**
   - Add extracted content under thematic subsections
   - **Thematic subsections are EMERGENT**: Create subsection headings organically as themes become apparent
     - Don't pre-define themes - let them emerge from the content
     - Examples: "Core Concepts," "Common Mistakes," "Best Practices"
     - Group related content from multiple sources under the same theme
   - Organize by concept/theme, NOT by source
   - Format:
     ```markdown
     ### [Emergent Theme Name]
     
     From [Source Name] ([URL]):
     
     > "Direct quote here for precision"
     
     **Key Points:**
     - Summary point 1
     - Summary point 2
     ```

2. **Update Topic's Source List:**
   - Add the source you just reviewed to the topic's indented list
   - Use ✅ emoji to indicate it's been captured
   - Format:
     ```markdown
     - [ ] Topic Name
       - ✅ [Source Title](URL) - Captured
     ```

3. **Save the file** (happens automatically when you edit)

### 4d. **assess-completeness**
After each source, ask yourself:
- "Have I gathered sufficient information on this topic?"
- "Do I understand the key concepts, patterns, and practical implications?"
- "Are there critical gaps that need one more source?"

**If sufficient:** Mark topic complete and move to next topic
**If gaps remain:** Search for and process one more targeted source

### 4e. **mark-topic-complete**
- Check the box for the completed topic in "Topics for Research" section:
  ```markdown
  - [x] Topic Name
    - ✅ [Source 1: Title](URL) - Captured
    - ✅ [Source 2: Title](URL) - Captured
  ```
- Proceed to next topic

**Note**: Same source may appear under multiple topics if it addresses different angles

## 5. **generate-summary**
After ALL topics are researched:

- Review all gathered research notes
- Synthesize findings into comprehensive summary
- Insert in "Research Summary" section
- Summary requirements:
  - **Length**: 1,000-2,000 words
  - **Content**: 
    - Patterns discovered across sources
    - Answers to key questions
    - Major insights and themes
    - Practical implications
  - **Attribution**: Point to specific sources for claims
  - **Structure**: Organize by themes/concepts, not by source
  - **Depth**: Sufficient for reader to:
    - Understand topic comprehensively
    - Decide on further exploration
    - Use as reference material

## 6. **final-review**
- Verify all sections are complete:
  - ✓ Initial Prompt (user's request)
  - ✓ Research Summary (1,000-2,000 words)
  - ✓ Topics for Research (all checked, with sources)
  - ✓ Research Notes (thematic sections with quotes + summaries)
- Ensure every quote and summary has source attribution
- Confirm thematic organization (not source-by-source)
- Update frontmatter `status` to `"researched"`
- Present completed research note to user

## Quality Standards

### **Content Requirements**
- [ ] Every quote has source URL
- [ ] Every summary has source URL
- [ ] Content organized by theme/concept, not by source
- [ ] Themes emerged naturally during research (not pre-defined)
- [ ] Research summary synthesizes findings (doesn't just concatenate)
- [ ] Summary is 1,000-2,000 words
- [ ] All topics marked complete with sources listed

### **Process Requirements**
- [ ] Research note updated after EVERY source (incremental progress)
- [ ] Topics confirmed with user before research begins
- [ ] Sufficient coverage achieved (not exhaustive reading)
- [ ] 2-3 excellent sources with deep extraction per topic
- [ ] Sources marked with ✅ emoji as captured
- [ ] Frontmatter status updated at each stage: staged → planned → researched

### **Organization Requirements**
- [ ] Same source referenced multiple times for different angles (when applicable)
- [ ] Thematic subsections group related content from multiple sources
- [ ] Topics for Research section shows clear progress tracking
- [ ] Research Notes section uses consistent formatting

## Key Principles

### **Incremental Progress**
- Update the research note after EVERY source - never batch updates
- Makes research resumable if interrupted
- Allows progress to accumulate in real-time
- Prevents loss of work if process is stopped
- Pattern: Read source → extract content → update note → save

### **Attribution Discipline**
- Every quote MUST have source URL
- Every summary MUST have source URL
- Enables verification and deeper exploration
- Provides context for future AI agents

### **Thematic Organization**
- Organize by concept/theme, NOT by source
- Themes emerge during research - don't pre-define them
- As you research, notice patterns and group related content together
- Create subsection headings that reflect natural themes you discover
- Makes note more useful as reference
- Easier to find specific information
- Same source may appear in multiple themes

### **Sufficiency Over Exhaustiveness**
- Goal is sufficient understanding, not reading every possible source
- After each source, assess: "Do I understand this topic well enough?"
- Better to have 2-3 excellent sources with deep extraction than 10 sources skimmed
- Focus on sources that provide actionable insights
- Skip sources that duplicate information already captured
- Mark topic complete when you have adequate coverage

### **Iterative Confirmation**
- Confirm research topics before execution
- Allows human to guide research direction
- Prevents wasted effort on irrelevant angles
- Maintains human-in-the-loop for strategic decisions

## Template Structure

The research note follows this structure (from `templates/Research Note.md`):

```markdown
---
dayNote: "[[W##-YYYYMMDD]]"
status: "staged"
---

# [Topic Title]
[Date]

---
## Initial Prompt
[User's original request]

## Research Summary
[1,000-2,000 word synthesis - completed last]

## Topics for Research
- [x] Topic 1
  - ✅ [Source 1: Title](URL) - Captured
  - ✅ [Source 2: Title](URL) - Captured
- [ ] Topic 2 (in progress)
  - ✅ [Source 1: Title](URL) - Captured
- [ ] Topic 3 (not started)

## Research Notes
### Theme/Concept 1
[Content with attribution]

### Theme/Concept 2
[Content with attribution]
```

## Integration Points

- **Related workflows**: `/daily-reflection` for processing research insights
- **Output location**: Choose appropriate location for your research notes
- **Template**: `templates/Research Note.md`
- **Status progression**: staged → planned → researched
- **Resumability**: Check Topics for Research section to see what's incomplete

## Example References

See these files for reference:
- **Toyota Kata Example**: `examples/toyota-kata-scientific-thinking.md`
- **Knowledge Work Example**: `examples/modern-knowledge-work-frameworks.md`
- **Wardley Mapping Example**: `examples/facilitating-wardley-mapping.md`

## Troubleshooting

- **Interrupted Research**: Resume by checking Topics for Research - unchecked topics or topics without sources need work
- **Source Overload**: Remember sufficiency over exhaustiveness - 2-3 good sources per topic is often enough
- **Theme Confusion**: Don't force themes upfront - let them emerge as you read and extract content
- **Attribution Missing**: Every piece of content needs a source URL - go back and add if missing
- **Summary Too Short**: Aim for 1,000-2,000 words - synthesize patterns across all research, don't just list findings
