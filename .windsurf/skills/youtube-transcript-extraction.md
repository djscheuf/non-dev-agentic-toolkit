# YouTube Transcript Extraction

## Overview
Extract transcripts from YouTube videos for free using `yt-dlp`, enabling content analysis and summarization without requiring API keys or paid services.

## Prerequisites
- `yt-dlp` installed on the system
- YouTube video URL

## Basic Usage

### Extract Auto-Generated Subtitles
```bash
yt-dlp --skip-download --write-auto-sub --sub-lang en --sub-format vtt --output "transcript" "YOUTUBE_URL"
```

### Parameters Explained
- `--skip-download`: Don't download the video file
- `--write-auto-sub`: Download auto-generated subtitles
- `--sub-lang en`: Specify language (en for English)
- `--sub-format vtt`: WebVTT format (includes timestamps)
- `--output "transcript"`: Output filename prefix

### Output
Creates a `.vtt` file (e.g., `transcript.en.vtt`) containing:
- Timestamps
- Transcript text with word-level timing
- Proper formatting for parsing

## Reading VTT Files

VTT files are text-based and can be read with standard file tools:

```bash
# Read the entire file
cat transcript.en.vtt

# Read specific portions for large files
head -n 100 transcript.en.vtt
tail -n 100 transcript.en.vtt
```

### VTT Format Structure
```
WEBVTT
Kind: captions
Language: en

00:00:00.160 --> 00:00:02.950 align:start position:0%
Your work doesn't speak for itself. It

00:00:02.950 --> 00:00:02.960 align:start position:0%
Your work doesn't speak for itself. It
 
00:00:02.960 --> 00:00:05.670 align:start position:0%
Your work doesn't speak for itself. It
never has. And if you believe it does,
```

## Parsing Strategies

### Extract Clean Text
To get just the spoken content without timestamps:
1. Read the VTT file
2. Filter lines that contain actual text (not timestamps or metadata)
3. Deduplicate repeated lines (VTT format often repeats text across time segments)
4. Join into coherent paragraphs

### Handle Large Files
For videos longer than ~10 minutes, VTT files can be 2000+ lines:
- Use `read_file` with `offset` and `limit` parameters
- Read in chunks (e.g., 800 lines at a time)
- Process sequentially until complete

## Common Use Cases

### 1. Article/Video Summarization
Extract transcript → Feed to LLM → Generate structured summary

### 2. Content Analysis
Extract transcript → Search for specific topics or quotes

### 3. Research Notes
Extract transcript → Create detailed notes with timestamps

### 4. Accessibility
Extract transcript → Provide text version of video content

## Alternative Subtitle Formats

### SRT Format
```bash
yt-dlp --skip-download --write-auto-sub --sub-lang en --sub-format srt --output "transcript" "YOUTUBE_URL"
```

SRT is simpler but less detailed than VTT:
```
1
00:00:00,160 --> 00:00:02,950
Your work doesn't speak for itself.

2
00:00:02,960 --> 00:00:05,670
It never has. And if you believe it does,
```

### JSON Format
```bash
yt-dlp --skip-download --write-auto-sub --sub-lang en --sub-format json3 --output "transcript" "YOUTUBE_URL"
```

JSON provides structured data with more metadata.

## Error Handling

### No Auto-Generated Subtitles
If auto-generated subtitles aren't available:
```bash
# Try manual subtitles instead
yt-dlp --skip-download --write-sub --sub-lang en --sub-format vtt --output "transcript" "YOUTUBE_URL"
```

### Language Detection
If you're unsure of the language:
```bash
# List available subtitles
yt-dlp --list-subs "YOUTUBE_URL"
```

### Private/Restricted Videos
`yt-dlp` respects YouTube's access controls. If a video requires authentication or is region-locked, the tool will fail with an appropriate error.

## Integration with Workflows

### With /article-summary Workflow
1. User provides YouTube URL
2. Extract transcript using `yt-dlp`
3. Read and parse VTT file
4. Analyze content and identify key concepts
5. Generate structured summary following article-summary format
6. Save to `Capture/` with appropriate naming

### Advantages Over Web Scraping
- No API keys required
- No rate limits
- Works with any public YouTube video
- Includes timing information
- Handles multiple languages
- Free and open-source

## Tips and Best practices

1. **Use /tmp for temporary files**: Store extracted transcripts in `/tmp` to avoid cluttering the workspace
2. **Check file size first**: Large transcripts may need chunked reading
3. **Preserve timestamps**: VTT format is useful if you need to reference specific moments
4. **Clean text extraction**: Remove duplicate lines that appear in VTT format
5. **Language specification**: Always specify `--sub-lang` to get the correct language

## Example Complete Workflow

```bash
# 1. Extract transcript
cd /tmp
yt-dlp --skip-download --write-auto-sub --sub-lang en --sub-format vtt --output "transcript" "https://www.youtube.com/watch?v=VIDEO_ID"

# 2. Read the file (in tool)
read_file /tmp/transcript.en.vtt

# 3. Process content (parse, analyze, summarize)
# 4. Create summary document in workspace
# 5. Clean up temporary file (optional)
rm /tmp/transcript.en.vtt
```

## Limitations

- Requires `yt-dlp` to be installed on the system
- Only works with public YouTube videos
- Auto-generated subtitles may have transcription errors
- Very long videos (>2 hours) produce very large files
- Relies on YouTube providing subtitles (most videos have them)

## Related Tools

- `youtube-dl`: Older tool, `yt-dlp` is the maintained fork
- `ffmpeg`: Can extract subtitles from downloaded video files
- YouTube Data API: Requires API key but provides more metadata

## Version History

- 2026-02-16: Initial skill documentation based on successful transcript extraction for video summary workflow
