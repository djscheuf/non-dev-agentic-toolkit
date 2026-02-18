---
description: Create InfoBits from Daily Notes
---

# InfoBits Creation Workflow

Generate a weekly InfoBits document from your daily notes, tailored for specific audiences using customer profiles. This workflow builds the document section by section for better quality and control.

## Prerequisites

- Have daily notes for the week in `⏰ 3-Rhythm/Daily/notes/`
- Know which week you're creating InfoBits for
- Customer profiles exist in `_prompts/info-bit-customers/`

## Steps

### Phase 1: Setup and Discovery

1. **Determine target week**
   - Ask user which week to create InfoBits for (e.g., "W03" for week 3)
   - Get current date if creating for current week: `date +%Y-%m-%d`
   - Calculate week number and date range

2. **Locate all daily notes for the target week**
   - Check `⏰ 3-Rhythm/Daily/notes/` folder for files in the week's date range
   - Pattern: `YYYY-MM-DD-HHMM-daily-notes.md`
   - List all matching files chronologically
   - Confirm with user if the file list looks correct

3. **Load customer profiles**
   - Read `_prompts/info-bit-customers/index.md` to get list of active customers
   - For each customer in the index, read their profile file
   - Store customer names and profile paths for later use

4. **Read all daily notes for the week**
   - Load each daily notes file found in step 2
   - Review content from all entries to understand the week's activities
   - Note progression and connections between entries

### Phase 2: Create Base Document Structure

5. **Create the InfoBits file with base structure**
   - Generate filename: `YYYYMMDDHHMMSS - [W]WW Infobits.md` (e.g., `202601211430 - W03 Infobits.md`)
   - Save to `⏰ 3-Rhythm/Logs/` folder
   - Create document with frontmatter and all section headers:
     ```markdown
     ---
     dayNote: "[[W##-YYYYMMDD]]"
     up: "[[YYYY-MM-W##]]"
     ---
     # W## InfoBits
     YYYYMMDD
     
     ---
     ## Carry Over ToDos
     
     ## Infobits
     - M
     - T
     - W
     - H
     - F
     
     ## Communications
     ## To [Customer1]
     ## To [Customer2]
     ```
   - Leave sections empty for now - they'll be filled in subsequent steps

### Phase 3: Fill Content Day by Day

6. **Process Monday (M)**
   - Review daily notes from Monday
   - Extract relevant information for all customers
   - Update the "- M" section with bullet points
   - Save the file

7. **Process Tuesday (T)**
   - Review daily notes from Tuesday
   - Extract relevant information for all customers
   - Update the "- T" section with bullet points
   - Save the file

8. **Process Wednesday (W)**
   - Review daily notes from Wednesday
   - Extract relevant information for all customers
   - Update the "- W" section with bullet points
   - Save the file

9. **Process Thursday (H)**
   - Review daily notes from Thursday
   - Extract relevant information for all customers
   - Update the "- H" section with bullet points
   - Save the file

10. **Process Friday (F)**
    - Review daily notes from Friday
    - Extract relevant information for all customers
    - Update the "- F" section with bullet points
    - Save the file

11. **Add Carry Over ToDos**
    - Review all daily notes for incomplete tasks
    - Identify tasks that carry over to next week
    - Update "## Carry Over ToDos" section
    - Format as checkboxes with context
    - Save the file

### Phase 4: Generate Customer Communications

12. **For each customer in the index, generate their communication section**
    - Read the customer's profile from `_prompts/info-bit-customers/[customer].md`
    - Read the InfoBits generation prompt from `_prompts/generate-infobits-summary.md`
    - Review the week's InfoBits content (M, T, W, H, F sections)
    - Synthesize a communication summary based on:
      - Customer's focus areas
      - Customer's exclusions
      - Customer's communication style
      - Relevant information from the week
    - **Format requirements**:
      - Target length: ~500 words maximum
      - Favor bullet points over expanded explanations
      - Use clear section headers for easy scanning
      - Keep it concise and focused on business impact
    - Highlight key points and action items
    - Update the "## To [Customer]" section
    - Save the file

### Phase 5: Review and Finalize

13. **Review and refine**
    - Ask if any edits are needed
    - Check if information is appropriately filtered for each customer
    - Verify week number and dates are correct
    - Confirm all customer sections are complete
    - Final save

## InfoBits Format

```markdown
---
dayNote: "[[W##-YYYYMMDD]]"
up: "[[YYYY-MM-W##]]"
---
# W## InfoBits
YYYYMMDD

---
## Carry Over ToDos
- [ ] [Incomplete task from week]
- [ ] [Another incomplete task]

## Infobits
- M
	- [Monday updates]
	- [ ] [Monday action items]
- T
	- [Tuesday updates]
- W
	- [Wednesday updates]
- H
	- [Thursday updates]
- F
	- [Friday updates]

## Communications
## To [Customer1]

**[Section Header]**
- [Bullet point with key information]
  - [Supporting detail if needed]
- [Another key point]

**[Another Section Header]**
- [Concise updates focused on business impact]

## To [Customer2]

**[Section Header]**
- [Bullet point format]
- [~500 words maximum per customer]
```

## Customer Profiles

Customer-specific filtering guidelines are maintained in `_prompts/info-bit-customers/`:
- **Index**: `_prompts/info-bit-customers/index.md` - Lists all active customers
- **Profiles**: Individual files for each customer (e.g., `robyn.md`, `kara.md`)

Each profile contains:
- Customer name and role
- Focus areas (what to include)
- Exclusions (what to filter out)
- Communication style preferences

### Adding New Customers

1. Create a new profile file in `_prompts/info-bit-customers/[customer-name].md`
2. Follow the template structure from existing profiles
3. Add the customer to the index file
4. Run the InfoBits workflow - it will automatically include the new customer

## Review Checklist

Before finalizing, confirm:
- [ ] Is the week number correct?
- [ ] Are all daily notes for the week included?
- [ ] Have all customer profiles been loaded from the index?
- [ ] Is information appropriately filtered for each customer based on their profile?
- [ ] Are action items clearly marked with checkboxes?
- [ ] Are Communications sections ~500 words each with bullet-point format?
- [ ] Are Communications sections written per customer style?
- [ ] Have I removed information excluded by customer profiles?
- [ ] Have I filtered out working details (test improvements, requirement simplifications, etc.)?
- [ ] Is the file saved to `⏰ 3-Rhythm/Logs/`?
- [ ] Does each day (M/T/W/H/F) have relevant content?
- [ ] Are Carry Over ToDos identified and formatted correctly?

## Workflow Execution Notes

### Section-by-Section Generation
- Build the document incrementally, not all at once
- Create base structure first, then fill in content
- Process one day at a time (M → T → W → H → F)
- Generate customer communications last, after all daily content is complete
- Save after each major section to preserve progress

### Customer Profile System
- Customer profiles are in `_prompts/info-bit-customers/`
- The index file lists all active customers
- Each customer has their own profile with specific filtering rules
- The workflow automatically loops through all customers in the index
- Adding a new customer requires only creating a profile and updating the index

### Quality Guidelines
- InfoBits are weekly summaries, not daily
- Focus on outcomes and impact, not just activities
- Different audiences need different levels of detail
- Keep technical details minimal unless they explain business/customer impact
- Use the daily notes as source material, but synthesize and filter appropriately
- Reference the generation prompt (`_prompts/generate-infobits-summary.md`) for detailed extraction guidance

### Communication Length and Format
- **Target**: ~500 words per customer communication section
- **Format**: Favor bullet points over paragraphs for easier scanning
- **Structure**: Use bold section headers to organize content
- **Focus**: Business impact over working details
- **Filter aggressively**: Customer profiles specify what to exclude - use them
- **Examples of working details to exclude**:
  - Requirement simplification discoveries (internal optimization)
  - Test infrastructure improvements (unless affects delivery)
  - Personal development activities not relevant to customer
  - Trust Pod insights (unless directly applicable to customer context)
  - Mentoring activities with non-relevant parties
