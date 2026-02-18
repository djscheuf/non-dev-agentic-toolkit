# Advanced Article Summary: Combining Workflows with Skills

This guide demonstrates how to extend the article-summary workflow by combining it with skills. You'll learn how skills teach the AI new capabilities without modifying workflows, creating a flexible and extensible pattern for capturing different content types.

## The Core Concept: Workflows + Skills

The power of the agentic toolkit comes from separating **process** (workflows) from **capability** (skills):

**Workflows define the process:**
- What steps to take
- When to take them
- How to structure output
- Quality standards to maintain

**Skills define capabilities:**
- How to extract content from new sources
- What tools to use
- When to apply specific techniques
- Why certain approaches work

**Together they create flexibility**: You extend what the AI can do by teaching it new skills, not by rewriting workflows.

## Why This Matters

### Without Skills
The article-summary workflow only handles web articles that can be scraped directly.

### With Skills
The same workflow can handle:
- **YouTube videos** (with youtube-transcript-extraction skill)
- **Meeting recordings** (with VTT file processing skill)
- **Podcasts** (with audio transcription skill)
- **PDFs** (with PDF extraction skill)
- **Any content type** you teach it to extract

### The Key Insight
Skills are **knowledge, not code**. They're documentation that teaches the AI how to perform new operations. This means non-developers can extend AI capabilities by writing clear instructions.

**Learn more**: See [Understanding Skills](understanding-skills.md) for a complete guide to creating your own skills.

## Example: YouTube Video Summaries

Let's walk through a complete example of combining the article-summary workflow with the youtube-transcript-extraction skill.

**Important**: This YouTube skill is **an example** of teaching the AI to use a CLI utility, **not a recommended change** to your workflow. It demonstrates the pattern you can apply to any command-line tool.

### The Skill: YouTube Transcript Extraction (Example)

The [youtube-transcript-extraction skill](../.windsurf/skills/youtube-transcript-extraction.md) demonstrates how to teach the AI to use a command-line utility.

**What it teaches:**
- How to use `yt-dlp` ([source](https://github.com/yt-dlp/yt-dlp)) to extract video transcripts
- How to parse VTT (WebVTT) format files
- How to handle large text files efficiently
- How to clean and deduplicate extracted text

**The pattern it demonstrates:**
```bash
# Example command syntax documentation
yt-dlp --skip-download --write-auto-sub --sub-lang en \
  --sub-format vtt --output "transcript" "YOUTUBE_URL"
```

**Why this example matters:**
- Shows how to document CLI tool usage
- Demonstrates file format parsing instructions
- Illustrates error handling documentation
- No code required—just clear instructions

**Learn more**: See [Understanding Skills](understanding-skills.md) for the complete pattern of teaching CLI utilities to the AI.

### The Workflow: Article Summary

The [article-summary workflow](../.windsurf/workflows/article-summary.md) defines:

**Process steps:**
1. Collect article URL from user
2. Extract content
3. Generate structured summary
4. Create metadata
5. Save to `Capture/Research/`
6. Validate and review

**Quality standards:**
- Core thesis in 1-2 sentences
- Key points organized thematically
- Tables for comparisons
- Proper attribution and metadata
- 50-120 lines target length

### Combined in Action: Batman Productivity Protocols

**User request:**
```
/article-summary

I want to summarize this YouTube video about productivity systems:
https://www.youtube.com/watch?v=iIhqRxyTLkE
```

**What happens behind the scenes:**

1. **AI recognizes the content type**
   - Sees YouTube URL
   - Recalls youtube-transcript-extraction skill
   - Knows it needs to extract transcript first

2. **AI extracts the transcript**
   ```bash
   cd /tmp
   yt-dlp --skip-download --write-auto-sub --sub-lang en \
     --sub-format vtt --output "transcript" "YOUTUBE_URL"
   ```

3. **AI reads and parses the VTT file**
   - Reads transcript in chunks (handles large files)
   - Filters out timestamps and metadata
   - Deduplicates repeated lines
   - Extracts clean spoken content

4. **AI applies article-summary workflow**
   - Identifies core thesis from transcript
   - Extracts key frameworks and techniques
   - Organizes into structured sections
   - Creates comparison tables
   - Generates proper metadata

5. **AI creates the summary file**
   - Saves to `Capture/Research/`
   - Uses timestamp naming convention
   - Includes video attribution
   - Maintains quality standards

**Result:**
A structured summary at `Capture/Research/202602161612 - Summary - Batman Productivity Protocols.md` containing:
- Core thesis on systems over motivation
- Six productivity protocols organized clearly
- Implementation examples in table format
- Connections to related concepts
- Proper video attribution

**Time investment:** ~12 minutes (includes transcript extraction)

**View the complete example:** See [the Batman Productivity Protocols example](../examples/batman-productivity-protocols.md)

## The Pattern in Detail

### Step 1: Skill Teaches Extraction

The skill documentation explains how to get content from a specific source type:

```markdown
## Basic Usage
Extract Auto-Generated Subtitles:
yt-dlp --skip-download --write-auto-sub --sub-lang en...

## Reading VTT Files
VTT files are text-based and can be read with standard file tools...

## Parsing Strategies
To get just the spoken content without timestamps:
1. Read the VTT file
2. Filter lines that contain actual text
3. Deduplicate repeated lines
4. Join into coherent paragraphs
```

### Step 2: Workflow Provides Structure

The workflow defines how to process any content into a summary:

```markdown
## 3. **summary-generation**
- Create a succinct summary following established patterns:
  - **Core Thesis**: 1-2 sentences capturing the main argument
  - **Key Points**: Main findings organized with tables
  - **Related Reading**: Capture links to resources
  - **Relevance**: Connect to specific existing files

## 4. **metadata-creation**
- Generate YAML frontmatter with:
  - title, tags, source, author, dateCreated
```

### Step 3: AI Combines Both

When invoked, the AI:
1. Recognizes the content type (YouTube video)
2. Applies the relevant skill (transcript extraction)
3. Follows the workflow process (summary generation)
4. Maintains quality standards (review and validation)

**No workflow modification needed** - the skill extends capability while the workflow maintains consistency.

## Extending to Other Content Types

The same pattern works for any content type you can extract. These are **examples** of what's possible, not recommendations:

**Note**: Each example below would require teaching the AI to use a specific CLI utility, just like the YouTube example demonstrates.

### Meeting Recordings with VTT Files

**Scenario:** You have VTT files from recorded meetings and want to summarize them.

**Example skill needed:** VTT file processing (similar to YouTube example, but reads local files)

**What you'd teach:** How to read and parse local VTT files, not download from YouTube

**Process:**
```
/article-summary

I have a VTT file from our team meeting at /path/to/meeting.vtt
Please summarize the key decisions and action items.
```

**What happens:**
1. AI reads the local VTT file
2. Parses and cleans the transcript
3. Applies article-summary workflow
4. Creates structured summary with meeting metadata

**Result:** Same quality summary, different source type.

### Podcast Episodes

**Scenario:** You want to summarize podcast episodes.

**Example skill needed:** Audio transcription using a CLI tool like Whisper

**What you'd teach:** How to run Whisper CLI to transcribe audio files

**Process:**
```
/article-summary

Summarize this podcast episode:
[podcast URL or audio file path]
```

**What happens:**
1. AI extracts/transcribes audio
2. Processes transcript
3. Applies article-summary workflow
4. Creates structured summary

**Result:** Consistent format across all content types.

### PDF Documents

**Scenario:** You want to summarize research papers or reports.

**Example skill needed:** PDF text extraction using a CLI tool like pdftotext

**What you'd teach:** How to use pdftotext to extract text from PDF files

**Process:**
```
/article-summary

Summarize this research paper:
/path/to/paper.pdf
```

**What happens:**
1. AI extracts text from PDF
2. Identifies structure (abstract, sections, conclusions)
3. Applies article-summary workflow
4. Creates structured summary

**Result:** Same quality standards, different source.

## Creating Your Own Skills

Want to extend to a new content type? Here's how to create a skill.

**Full guide**: See [Understanding Skills](understanding-skills.md) for complete documentation on creating skills.

**Quick overview:**

### 1. Identify the Content Type

What source do you want to summarize?
- Video platform (Vimeo, Loom, etc.)
- Audio format (MP3, WAV, etc.)
- Document format (DOCX, EPUB, etc.)
- Web service (Notion, Confluence, etc.)

### 2. Research Extraction Methods

How can you get the content as text?
- Command-line tools
- APIs
- File parsing libraries
- Web scraping techniques

### 3. Document as a Skill

Create `.windsurf/skills/[content-type]-extraction.md`:

```markdown
# [Content Type] Extraction

## Overview
[What this skill enables]

## Prerequisites
[Required tools or access]

## Basic Usage
[Step-by-step extraction process]

## Parsing Strategies
[How to clean and process the extracted content]

## Common Use Cases
[When to use this skill]

## Integration with Workflows
[How this combines with article-summary]
```

### 4. Test with Article-Summary

Try it out:
```
/article-summary

[Provide content of the new type]
```

The AI will read your skill documentation and apply it.

### 5. Refine Based on Results

- Did extraction work correctly?
- Was parsing clean enough?
- Did it integrate smoothly with the workflow?
- What edge cases need handling?

Update the skill documentation based on what you learn.

## Best Practices

### 1. Keep Skills Focused

Each skill should teach **one capability**:
- ✅ YouTube transcript extraction
- ✅ VTT file processing
- ✅ PDF text extraction
- ❌ "Extract content from any source" (too broad)

### 2. Document Prerequisites Clearly

List what needs to be installed or configured:
```markdown
## Prerequisites
- `yt-dlp` installed on the system
- YouTube video URL (must be public)
```

### 3. Provide Complete Examples

Show the exact commands or process:
```bash
yt-dlp --skip-download --write-auto-sub --sub-lang en \
  --sub-format vtt --output "transcript" "YOUTUBE_URL"
```

### 4. Explain the "Why"

Help the AI understand when to apply the skill:
```markdown
## When to Use
- User provides a YouTube URL
- Content is video-based
- Auto-generated captions are available
```

### 5. Include Error Handling

Document common issues and solutions:
```markdown
## Troubleshooting
- No auto-generated subtitles: Try manual subtitles
- Private video: Cannot extract, ask for alternative
- Very long video: Process in chunks
```

## Quality Standards

When combining skills with workflows, maintain these standards:

### Content Quality
- [ ] Core thesis accurately captured from source
- [ ] Key points organized logically
- [ ] Tables used for comparisons
- [ ] Proper attribution to original source
- [ ] Connections to existing knowledge (when relevant)

### Technical Quality
- [ ] Extraction successful and complete
- [ ] Parsing clean (no artifacts or duplicates)
- [ ] Metadata accurate (source URL, author, date)
- [ ] File saved in correct location
- [ ] Naming convention followed

### Process Quality
- [ ] User confirms before extraction
- [ ] Progress visible during processing
- [ ] Review step before saving
- [ ] Error handling graceful
- [ ] Time investment reasonable

## Troubleshooting

### Issue: Skill Not Applied

**Problem:** AI doesn't use the skill even though content type matches.

**Solution:**
- Explicitly mention the content type: "This is a YouTube video"
- Reference the skill directly: "Use the youtube-transcript-extraction skill"
- Check that skill file exists and is readable

### Issue: Extraction Fails

**Problem:** Tool or command doesn't work as expected.

**Solution:**
- Verify prerequisites are installed
- Check file permissions
- Test command manually first
- Update skill documentation with correct syntax

### Issue: Poor Quality Summary

**Problem:** Summary doesn't meet quality standards.

**Solution:**
- Review extraction - is content complete?
- Check parsing - are there artifacts?
- Refine workflow invocation - be more specific about focus
- Iterate on the summary before saving

### Issue: Inconsistent Format

**Problem:** Summaries from different sources look different.

**Solution:**
- Workflow defines format, not skill
- Ensure workflow is being followed
- Review quality standards checklist
- Update workflow if standards need adjustment

## Key Takeaways

1. **Separation of concerns** - Workflows define process, skills define capability
2. **Extensibility** - Add new content types by creating skills, not modifying workflows
3. **Consistency** - Same quality standards across all content types
4. **Teachability** - Skills are documentation, not code
5. **YouTube is an example** - Demonstrates teaching CLI utilities, not a recommendation
6. **Pattern is reusable** - Same approach works for any command-line tool
7. **No coding required** - Extend capabilities by writing clear instructions

## Next Steps

Ready to extend your capabilities?

1. **Try the YouTube example** - Summarize a video using the existing skill
2. **Identify a need** - What content type do you want to summarize?
3. **Create a skill** - Document how to extract that content type
4. **Test the combination** - Use with article-summary workflow
5. **Refine and iterate** - Improve based on results
6. **Share your skill** - Help others benefit from your work

## Related Resources

- [Understanding Skills](understanding-skills.md) - Complete guide to creating skills and teaching CLI utilities
- [Using the Article Summary Workflow](using-article-summary-workflow.md) - Basic usage guide
- [YouTube Transcript Extraction Skill](../.windsurf/skills/youtube-transcript-extraction.md) - Example skill documentation
- [Batman Productivity Protocols Example](../examples/batman-productivity-protocols.md) - Complete worked example
- [Article Summary Workflow](../.windsurf/workflows/article-summary.md) - Workflow implementation
- [yt-dlp on GitHub](https://github.com/yt-dlp/yt-dlp) - Example CLI utility source

---

**Remember**: The YouTube transcript extraction skill is **an example** of teaching the AI to use CLI utilities, not a recommended change. The real value is understanding the pattern so you can teach the AI to use **any** command-line tool you need. See [Understanding Skills](understanding-skills.md) for the complete guide.
