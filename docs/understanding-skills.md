# Understanding Skills

Skills are documentation files that teach the AI how to use tools and techniques to extend its capabilities. This guide explains what skills are, how they work, and how to create your own.

## What is a Skill?

A skill is a markdown file that documents how to perform a specific operation. Skills are **knowledge, not code**—they teach the AI through clear instructions and examples.

**Key insight**: You extend AI capabilities by writing documentation, not by writing code. This makes the toolkit accessible to non-developers.

## How Skills Work

When you invoke a workflow, the AI can recall relevant skills to handle specialized tasks. The skill provides:

1. **What** the operation accomplishes
2. **How** to perform it (commands, tools, techniques)
3. **When** to apply it (content types, scenarios)
4. **Why** certain approaches work
5. **Troubleshooting** for common issues

The AI reads this documentation and applies the instructions to accomplish tasks it couldn't do otherwise.

## Example: YouTube Transcript Extraction

The [youtube-transcript-extraction skill](../.windsurf/skills/youtube-transcript-extraction.md) demonstrates teaching the AI to use a command-line utility to expand its capabilities.

### What It Does

Extracts transcripts from YouTube videos using the `yt-dlp` command-line tool, enabling video content summarization without API keys or paid services.

**Source tool**: [yt-dlp on GitHub](https://github.com/yt-dlp/yt-dlp)

### How It Works

The skill documents the complete process:

**1. Command syntax:**
```bash
yt-dlp --skip-download --write-auto-sub --sub-lang en \
  --sub-format vtt --output "transcript" "YOUTUBE_URL"
```

**2. File format handling:**
- VTT files contain timestamps and text
- Need to filter out metadata
- Deduplicate repeated lines
- Extract clean spoken content

**3. Edge cases:**
- Large files require chunked reading
- Missing auto-captions → try manual subtitles
- Private videos → cannot extract

**4. Integration points:**
- Works with article-summary workflow
- Produces text suitable for summarization
- Maintains attribution to video source

### Why This Is Just an Example

**Important**: The YouTube transcript extraction skill is **not a recommended change** to your workflow. It's an **example** of how to teach the AI to use CLI utilities.

**What it demonstrates:**
- How to document a command-line tool
- How to explain file format parsing
- How to handle error cases
- How to integrate with workflows

**What it doesn't mean:**
- You must install yt-dlp
- You should summarize YouTube videos
- This is the "right" way to handle video content
- Everyone needs this specific skill

**The real lesson**: You can teach the AI to use **any** CLI utility by documenting it as a skill.

## The Pattern: Teaching CLI Utilities

The YouTube skill demonstrates a general pattern for teaching the AI to use command-line tools:

### Step 1: Document Prerequisites

```markdown
## Prerequisites
- `tool-name` installed on the system
- Required input (URL, file path, etc.)
```

### Step 2: Show Basic Usage

```markdown
## Basic Usage
command-name --flag1 --flag2 "input" "output"
```

Explain what each flag does and why it's needed.

### Step 3: Explain Output Format

```markdown
## Output Format
The tool produces [format] files containing:
- [Element 1]
- [Element 2]
```

### Step 4: Document Parsing

```markdown
## Parsing Strategies
To extract usable content:
1. Read the output file
2. Filter/clean the content
3. Handle format-specific quirks
```

### Step 5: Cover Error Cases

```markdown
## Troubleshooting
- Issue 1: Solution
- Issue 2: Alternative approach
```

### Step 6: Show Integration

```markdown
## Integration with Workflows
This skill works with [workflow name] by:
1. [Step 1]
2. [Step 2]
```

## Other CLI Utility Examples

The same pattern works for many tools:

### Audio Transcription (Whisper)

**Tool**: OpenAI's Whisper for audio transcription

**Skill would document:**
```bash
whisper audio-file.mp3 --model base --output_format txt
```

**Use case**: Transcribe podcast episodes or meeting recordings

### PDF Text Extraction (pdftotext)

**Tool**: Poppler's pdftotext utility

**Skill would document:**
```bash
pdftotext -layout document.pdf output.txt
```

**Use case**: Extract text from research papers or reports

### Image OCR (Tesseract)

**Tool**: Tesseract OCR engine

**Skill would document:**
```bash
tesseract image.png output --oem 3 --psm 6
```

**Use case**: Extract text from screenshots or scanned documents

### Web Archiving (wget)

**Tool**: wget for downloading web content

**Skill would document:**
```bash
wget --mirror --convert-links --page-requisites "URL"
```

**Use case**: Archive web pages for offline reference

## Creating Your Own Skills

Want to teach the AI to use a tool you need? Follow this process:

### 1. Identify the Need

What capability do you want to add?
- Extract content from a specific format?
- Process data with a specialized tool?
- Automate a repetitive task?

### 2. Find the Right Tool

Research command-line tools that solve your need:
- Search GitHub for relevant projects
- Check package managers (apt, brew, pip)
- Look for well-maintained, documented tools

### 3. Learn the Tool Yourself

Before documenting for the AI, understand:
- How to install it
- Basic usage patterns
- Common flags and options
- Output format
- Error messages

### 4. Document as a Skill

Create a skill file at `.windsurf/skills/[tool-name]-[capability].md`:

```markdown
# [Tool Name] [Capability]

## Overview
[What this skill enables]

## Prerequisites
[Required installation and setup]

## Basic Usage
[Command syntax with examples]

## Output Format
[What the tool produces]

## Parsing Strategies
[How to process the output]

## Troubleshooting
[Common issues and solutions]

## Integration with Workflows
[How this combines with existing workflows]

## Source
[Link to tool's repository or documentation]
```

### 5. Test with a Workflow

Try using the skill with an existing workflow:
```
/workflow-name

[Provide input that requires the new skill]
```

Observe how the AI applies the skill documentation.

### 6. Refine Based on Results

- Did the AI use the correct commands?
- Was output parsing successful?
- Were error cases handled properly?
- What additional details would help?

Update the skill documentation based on what you learn.

## Best Practices

### Keep Skills Focused

Each skill should teach **one capability**:
- ✅ YouTube transcript extraction
- ✅ PDF text extraction
- ✅ Audio transcription
- ❌ "Extract content from any source" (too broad)

### Document Prerequisites Clearly

List exactly what needs to be installed:
```markdown
## Prerequisites
- `yt-dlp` version 2023.03.04 or later
- Python 3.7+ (required by yt-dlp)
- Internet connection for video access
```

### Provide Complete Examples

Show the exact commands, not pseudocode:
```bash
# Good: Exact command
yt-dlp --skip-download --write-auto-sub --sub-lang en \
  --sub-format vtt --output "transcript" "https://youtube.com/watch?v=..."

# Bad: Pseudocode
yt-dlp [options] [url]
```

### Explain the "Why"

Help the AI understand when to apply the skill:
```markdown
## When to Use
- User provides a YouTube URL
- Content is video-based
- Transcript/captions are needed for summarization
```

### Include Error Handling

Document what can go wrong and how to handle it:
```markdown
## Common Issues
- **No captions available**: Try manual subtitles with --write-sub
- **Private video**: Cannot extract, ask user for alternative
- **Rate limiting**: Wait and retry, or use different video
```

### Link to Source Documentation

Always provide the source:
```markdown
## Source
- Tool: [yt-dlp on GitHub](https://github.com/yt-dlp/yt-dlp)
- Documentation: [yt-dlp README](https://github.com/yt-dlp/yt-dlp#readme)
```

## Skills vs. Workflows

Understanding the difference:

### Workflows Define Process
- What steps to take
- When to take them
- How to structure output
- Quality standards

**Example**: article-summary workflow defines how to create summaries

### Skills Define Capability
- How to extract content
- What tools to use
- When to apply techniques
- Why approaches work

**Example**: youtube-transcript-extraction skill teaches how to get video transcripts

### Together They Create Flexibility

**Without skills**: Workflows limited to built-in capabilities

**With skills**: Same workflow handles any content type you teach it

**Key advantage**: Extend by teaching (documentation), not coding (implementation)

## Quality Standards

Good skills have:

- [ ] **Clear overview** - What capability does this enable?
- [ ] **Complete prerequisites** - What needs to be installed?
- [ ] **Exact commands** - Copy-pastable examples
- [ ] **Output explanation** - What does the tool produce?
- [ ] **Parsing instructions** - How to process output
- [ ] **Error handling** - Common issues and solutions
- [ ] **Integration guidance** - How to use with workflows
- [ ] **Source links** - Where to find the tool

## Common Pitfalls

### Pitfall 1: Too Generic

**Problem**: Skill tries to cover too many scenarios

**Solution**: Create focused skills for specific tools/formats

### Pitfall 2: Missing Prerequisites

**Problem**: Skill assumes tools are installed

**Solution**: Explicitly list all requirements

### Pitfall 3: Incomplete Commands

**Problem**: Examples use placeholders instead of real syntax

**Solution**: Show exact commands with all flags

### Pitfall 4: No Error Handling

**Problem**: Skill doesn't explain what to do when things fail

**Solution**: Document common issues and solutions

### Pitfall 5: Unclear Integration

**Problem**: Not obvious how skill works with workflows

**Solution**: Explicitly show integration examples

## Real-World Skill: YouTube Transcript Extraction

See [the complete implementation](../.windsurf/skills/youtube-transcript-extraction.md)

**What it demonstrates:**
- Complete CLI utility documentation
- VTT format parsing instructions
- Error case handling
- Workflow integration
- Source attribution

**What to learn from it:**
- How to structure skill documentation
- Level of detail needed for AI to apply
- Balance between completeness and clarity
- Integration with existing workflows

**Remember**: This is an **example**, not a requirement. Use it as a template for documenting your own CLI utilities.

## Key Takeaways

1. **Skills are documentation** - Teach through clear instructions, not code
2. **CLI utilities are teachable** - Any command-line tool can become a skill
3. **Focus on one capability** - Each skill should do one thing well
4. **Complete examples matter** - Show exact commands, not pseudocode
5. **Error handling is critical** - Document what can go wrong
6. **Integration is key** - Show how skills work with workflows
7. **YouTube skill is an example** - Template for teaching CLI utilities, not a recommendation

## Next Steps

Ready to create your own skills?

1. **Review the example** - Study `.windsurf/skills/youtube-transcript-extraction.md`
2. **Identify a need** - What capability would help your workflow?
3. **Find a tool** - Research CLI utilities that solve your need
4. **Learn it yourself** - Understand the tool before documenting
5. **Create the skill** - Follow the documentation pattern
6. **Test and refine** - Use with workflows and improve based on results

## Related Resources

- [YouTube Transcript Extraction Skill](../.windsurf/skills/youtube-transcript-extraction.md) - Complete example skill
- [Advanced Article Summary with Video](advanced-article-summary-with-video.md) - Using skills with workflows
- [yt-dlp on GitHub](https://github.com/yt-dlp/yt-dlp) - Example CLI utility source

---

**Remember**: Skills make the toolkit extensible without coding. You teach the AI new capabilities by writing clear documentation about tools and techniques. The YouTube transcript extraction skill is just one example—you can teach any CLI utility the same way.
