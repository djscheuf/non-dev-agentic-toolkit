# Using the InfoBits Workflow

## What are InfoBits?

InfoBits is a communication technique developed by Jade Rubick for improving information flow across an organization. Instead of sending generic weekly updates to everyone, InfoBits helps you:

- **Track** what happens throughout your week in a daily log
- **Filter** that information based on each stakeholder's specific needs
- **Communicate** tailored updates that help each person do their job better

The result is better information flow, stronger relationships, and more effective collaboration.

**Learn more about the technique**: https://www.rubick.com/infobits-for-information-flow/

## Overview of the Workflow

The [InfoBits workflow](../.windsurf/workflows/create-infobits.md) automates the process of creating weekly InfoBits summaries from your daily notes. This document explains why the workflow is valuable and how it makes professional communication more effective and less time-consuming.

## The Challenge: Information Overload vs. Information Gaps

Most knowledge workers face a communication paradox:

**Too much information**: Everyone is drowning in messages, emails, and notifications
**Not enough relevant information**: People don't know what they need to know when they need to know it

Traditional approaches don't solve this:
- **Generic weekly emails**: Everyone gets the same information, most of which isn't relevant to them
- **Ad-hoc messaging**: Important updates get lost in chat streams
- **Status meetings**: Time-consuming and often cover irrelevant details for most attendees

**The problem**: You either overwhelm people with everything or leave critical gaps in communication. There's no easy way to tailor information to each stakeholder's needs.

## The Solution: Audience-Specific Communication

The InfoBits workflow solves this by:

1. **Capturing** your daily activities in timestamped notes throughout the week
2. **Organizing** those activities by day (M/T/W/H/F) in a single document
3. **Filtering** the information based on customer/stakeholder profiles
4. **Generating** tailored summaries that give each person exactly what they need to know

Instead of spending hours crafting individual updates, the AI:
- Reviews all your daily notes for the week
- Understands each stakeholder's focus areas and exclusions
- Synthesizes relevant information into concise, targeted summaries
- Formats everything consistently with clear structure

## Understanding the Value: Better Relationships Through Better Communication

### What InfoBits Gives You

**Improved information flow**:
- Stakeholders get updates tailored to their needs
- No more "I didn't know about that" surprises
- People can do their jobs better because they have the context they need

**Stronger relationships**:
- Shows you understand what matters to each person
- Demonstrates professionalism and consideration
- Builds trust through consistent, relevant communication

**Time efficiency**:
- Capture once, communicate many times
- AI handles the filtering and synthesis
- Consistent format reduces cognitive load

**Career benefits**:
- Your work becomes more visible
- Stakeholders perceive you as more effective
- Creates a record of your accomplishments

### Real Impact

From Jade Rubick's experience with InfoBits:

> **Surprise #1**: I started receiving thank you notes. Lots of little email responses like this: "I like these write-ups. This is a good model to use. I definitely appreciate these!"
>
> **Surprise #2**: Suddenly everyone seemed to think I and my team were doing better work than we had been doing previously.
>
> **Surprise #3**: Infobits also help build important business relationships. People really appreciate it when you are helping them to do their job better.

## Real-World Application

### When to Use This Workflow

**Good fits:**
- You work with multiple stakeholders who need different information
- You want to improve communication with your manager
- You're managing relationships with clients or partners
- You need to keep cross-functional teams informed
- You want a record of your weekly accomplishments

**Less suitable:**
- You only have one or two stakeholders (simpler approaches work fine)
- Your work doesn't vary much week to week
- You don't keep daily notes or logs

### Who Benefits from InfoBits

**Your manager**: Gets visibility into your work without micromanaging
**Clients**: Stay informed about progress without constant check-ins
**Cross-functional partners**: Know when your work affects them
**Skip-level managers**: Understand your impact without detailed status meetings
**Future you**: Have a record of what you accomplished and when

## Getting Started

### Prerequisites

1. **Daily note-taking habit**: You need to capture your activities throughout the week
2. **Stakeholder profiles**: Know who needs what information (the workflow helps you create these)
3. **Time commitment**: 
   - Daily: 5-10 minutes capturing activities
   - Weekly: 30-45 minutes for AI to generate InfoBits (mostly automated)

### Setting Up Customer Profiles

Before your first InfoBits generation, you'll need to create stakeholder profiles. These tell the AI what to include and exclude for each person.

**Profile location**: Store in your PKM under `_prompts/info-bit-customers/`

**Profile structure**:
```markdown
# [Stakeholder Name]

## Role
[Their role and relationship to you]

## Focus Areas
What to include:
- [Category 1: e.g., Client deliverables]
- [Category 2: e.g., Team development]
- [Category 3: e.g., Strategic initiatives]

## Exclusions
What to filter out:
- [Category 1: e.g., Technical implementation details]
- [Category 2: e.g., Internal process improvements]
- [Category 3: e.g., Personal development activities]

## Communication Style
- [Preference 1: e.g., Bullet points over paragraphs]
- [Preference 2: e.g., Focus on business impact]
- [Preference 3: e.g., ~500 words maximum]
```

**Example profiles** (from the workflow):
- **Manager**: Focus on client engagement, strategic initiatives, team development; exclude technical details
- **Client Product Owner**: Focus on feature delivery, blockers, requirement clarifications; exclude internal initiatives
- **Cross-functional Partner**: Focus on dependencies, timeline impacts, decisions affecting them; exclude unrelated work

### Example Scenario

**Situation**: You're a consultant working with a client while also managing internal initiatives. You need to keep your manager informed about business development and your client's product owner informed about delivery progress.

**Without InfoBits**:
- You send the same weekly email to both
- Your manager gets buried in technical details they don't need
- Your client doesn't see the strategic context they care about
- You spend an hour crafting a compromise that satisfies neither

**With InfoBits**:
1. Throughout the week, you capture activities in daily notes (5-10 min/day)
2. Friday afternoon, you invoke the workflow: `/create-infobits for W08`
3. The AI:
   - Reviews all your daily notes from Monday-Friday
   - Creates day-by-day bullets (M/T/W/H/F) in the InfoBits document
   - Reads your manager's profile: focus on client relationships, speaking engagements, business development
   - Generates a summary for your manager highlighting those areas
   - Reads your client's profile: focus on feature delivery, blockers, sprint progress
   - Generates a separate summary for your client highlighting delivery progress
4. You review both summaries, make minor edits if needed
5. You send each person their tailored update

**Result**: 
- Your manager sees: "Delivered HCSS conference presentation, 3+ meaningful conversations, KAA accepted talk proposal"
- Your client sees: "Completed E2E test suite (40 tests), fixed validation bug, sprint review revealed display issues - systematic fixes implemented"
- Both get exactly what they need, neither is overwhelmed with irrelevant details
- Total time: ~45 minutes including review

### What to Expect

The workflow will:
1. Ask which week you're creating InfoBits for
2. Locate all your daily notes for that week
3. Create an InfoBits document with the base structure
4. Process each day (M/T/W/H/F) and extract relevant information
5. Read all your customer profiles
6. Generate tailored summaries for each stakeholder
7. Ask if you want to make any edits

### Tips for Success

**Capture consistently**: The quality of your InfoBits depends on the quality of your daily notes. Capture activities as they happen, not at the end of the week.

**Be specific in profiles**: The more specific your stakeholder profiles, the better the AI can filter. "Focus on client deliverables" is vague; "Focus on feature completion, blockers, and requirement clarifications" is specific.

**Start with 2-3 stakeholders**: Don't try to create profiles for everyone at once. Start with your most important relationships and expand over time.

**Review before sending**: The AI does the heavy lifting, but you should always review the summaries to ensure accuracy and tone.

**Iterate on profiles**: After a few weeks, you'll learn what works. Update profiles based on feedback and what resonates with each stakeholder.

## The InfoBits Document Structure

### Daily Capture Section

```markdown
## Infobits
- M
	- [Monday activities and outcomes]
	- [ ] [Monday action items]
- T
	- [Tuesday activities and outcomes]
- W
	- [Wednesday activities and outcomes]
- H
	- [Thursday activities and outcomes]
- F
	- [Friday activities and outcomes]
```

This section is your raw material - everything that happened during the week.

### Customer Communication Sections

```markdown
## Communications
## To [Stakeholder 1]

**[Theme from Focus Areas]**
- [Synthesized update combining related work]
- [Another related update]
- [ ] [Action item if applicable]

**[Another Theme]**
- [Updates grouped by theme, not by day]

## To [Stakeholder 2]

**[Different Theme for This Person]**
- [Information relevant to their focus areas]
```

Each stakeholder gets a tailored summary based on their profile.

## Workflow Execution Pattern

The workflow follows a deliberate section-by-section approach:

### Phase 1: Setup
- Determine target week
- Locate daily notes
- Load customer profiles

### Phase 2: Base Structure
- Create the InfoBits file
- Set up frontmatter and headers
- Leave sections empty initially

### Phase 3: Daily Content
- Process Monday → update M section → save
- Process Tuesday → update T section → save
- Process Wednesday → update W section → save
- Process Thursday → update H section → save
- Process Friday → update F section → save

### Phase 4: Customer Summaries
- For each customer:
  - Read their profile
  - Review all daily content
  - Filter and synthesize
  - Generate their section
  - Save

This incremental approach ensures quality and allows you to see progress as the document builds.

## Complementary Workflows

- [Research workflow](../.windsurf/workflows/research.md): Use to research communication best practices or stakeholder management
- [Decision facilitation workflow](../.windsurf/workflows/decision-facilitation.md): Use when InfoBits reveal decisions that need stakeholder input
- [Active partner rule](../.windsurf/rules/active-partner.md): Ensures the AI asks clarifying questions about stakeholder needs

## Related Documentation

- [InfoBits workflow file](../.windsurf/workflows/create-infobits.md)
- [InfoBits template](../templates/InfoBits.md)
- [Project context and audience](project-context-and-audience.md)

## References

- Jade Rubick's InfoBits article: https://www.rubick.com/infobits-for-information-flow/
- Original concept credit: Bjorn Freeman-Benson

## Conclusion

The InfoBits workflow transforms weekly communication from a time-consuming chore into a systematic practice that strengthens relationships and improves information flow. By capturing once and communicating many times with tailored content, you:

- **Save time** while improving communication quality
- **Build stronger relationships** through relevant, considerate updates
- **Increase your visibility** and perceived effectiveness
- **Create a record** of your accomplishments and impact

The workflow handles the mechanical work of filtering and synthesis, letting you focus on the strategic work of understanding what each stakeholder needs and maintaining those important relationships.
