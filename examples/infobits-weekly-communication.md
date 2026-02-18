# Example: Weekly InfoBits Communication

This example demonstrates how InfoBits transforms daily activity logs into tailored stakeholder communications.

## Context

**Role**: Technical consultant working with a client ([sic]) while managing internal initiatives and business development activities.

**Stakeholders**:
- (Manager): Focuses on client engagement, strategic initiatives, business development
- (Client Product Owner): Focuses on feature delivery, sprint progress, blockers

**Week**: W07 (February 10-14, 2025)

## Source Material: Daily Notes

Throughout the week, activities were captured in timestamped daily notes:

### Monday (2/10)
- Completed E2E test suite refactor - 40 tests passing
- Fixed validation bug on create page
- [sic] conference prep - dry run completed
- Drafted 3-4 blog posts from idea backlog

### Tuesday (2/11)
- Continued CoPilot experiment for SQL to C# conversion
- Generated test cases with AI guidance
- Extracted 3-4 more query conversions
- Networking: Scheduled lunch with [sic]

### Wednesday (2/12)
- Sprint demo and retrospective
- Promoted [sic]'s work on LinkedIn - good engagement
- Personal: Ripped [sic] series into Plex

### Thursday (2/13)
- Day of freeze, kids in school
- Sprint planning session
- Lunch with [sic] (networking)
- Completed 5/5 update conversions, unit tests passing
- Found integration test issue with data assumptions

### Friday (2/14)
- Podcast recording with [sic]
- Lunch with [sic]
- [sic] content creation

## Generated InfoBits Document

```markdown
---
dayNote: "[[W07-20250210]]"
up: "[[2025-02-W07]]"
---
# W07 InfoBits
20250210

---
## Carry Over ToDos
- [ ] Resolve integration test data assumption issue
- [ ] Complete remaining [sic] SPROC refactor stories (4 of 5 remaining)

## Infobits
- M
	- **[sic] Work**: Completed E2E test suite refactor - 40 tests passing, merged to main
	- **Bug Fix**: Fixed validation bug preventing submission from proofing on create page
	- **[sic] Conference**: Completed dry run for Tuesday presentation
	- **Content Pipeline**: Drafted 3-4 blog posts from idea backlog
- T
	- **AI Experimentation**: Tested CoPilot for SQL to C# conversion - mixed results
		- Useful for generating test case scaffolding
		- Struggles with query breakdown and method usage
	- **[sic] Progress**: Extracted 3-4 more query conversions, nearing story completion
	- **Networking**: Scheduled lunch with [sic] for next week
- W
	- **Sprint Activities**: Demo and retrospective completed
	- **Networking**: Created LinkedIn promotion for [sic] - strong engagement
- H
	- **Sprint Planning**: Completed planning for next sprint
	- **[sic] Work**: Finished 5/5 update conversions, unit tests passing
		- Discovered integration test issue: data assumption problems
		- Need to incorporate into testing pattern
	- **Networking**: Lunch with [sic] - catching up, trading war stories
- F
	- **Networking**: Podcast recording with [sic]
	- **Client Engagement**: Lunch with [sic]
	- **Build in Public**: Content creation session

## Communications
## To [Manager]

**1 Big Thing - GenAI to Convert SQL to C# Still Needs Work**

Context:
- After getting into the [sic] SPROC refactor, we split the remaining work into 5 stories (each ~5 points)
- Tested several CoPilot prompt variations to speed up the process - none were promising
- CoPilot struggled to effectively break down queries and understand well-named method behavior
- Some struggle stems from the interwoven nature of update statements (getting new values + filtering impacted records)

In the Background:
- Chief concern: Instead of centralizing knowledge in [sic], we're centralizing in me
- First of 5 stories already complete, targeting second story completion by Friday
- CoPilot remains useful for rapidly setting up test suites (behaviors are similar, data differs)
- Recent usage data shows whole data sets that SPROC modifies go unused unless directly read from DB (e.g., [sic])
- Complex [sic] computations with CTEs will be wrapped in sub-sproc rather than fully refactored (not apparently used)

**Client Engagement & Networking**:
- [sic] conference presentation prep completed Monday
- Networking lunches: [sic] (scheduled), [sic] (Thursday), [sic] (Friday)
- Podcast recording with [sic] on Friday
- LinkedIn promotion for [sic] generated strong engagement

**Build in Public Progress**:
- Content pipeline: Drafted 3-4 blog posts from backlog
- Friday session focused on content creation

## To [Client PO]

**Sprint Progress**:
- Completed E2E test suite refactor: 40 tests passing, merged to main
- Fixed validation bug: Users can now submit from proofing on create page
- Finished 5/5 update conversions with unit tests passing
- Sprint demo and retrospective completed Wednesday
- Sprint planning completed Thursday

**In Progress - [sic] SPROC Refactor**:
- First of 5 stories complete
- Working on second story, targeting Friday completion
- Extracted 3-4 more query conversions Tuesday

**Blockers & Technical Challenges**:
- Discovered integration test issue: Data assumption problems in test setup
- Need to incorporate fix into testing pattern
- AI-assisted conversion (CoPilot) not effective for complex query breakdown
	- Useful for test scaffolding
	- Manual conversion remains more reliable for core logic

**Technical Insights**:
- Usage data analysis reveals unused data modifications in SPROC
- Planning to wrap complex [sic] computations in sub-sproc (simpler than full refactor)
- [ ] Review integration test pattern to prevent data assumption issues
```

## Analysis: How Filtering Works

### For Manager

**Included**:
- Strategic concern about knowledge centralization
- Client engagement activities (lunches, networking)
- Business development (Build in Public, content creation)
- High-level technical context (what the challenge is, not how to solve it)

**Excluded**:
- Detailed technical implementation (test suite specifics, query conversion details)
- Sprint mechanics (demo/retro mentioned only in context)
- Personal activities ([sic], kids)

**Communication Style**:
- "1 Big Thing" format for primary concern
- Bullet points with clear categories
- Focus on business impact and risk
- ~300 words

### For Client Product Owner

**Included**:
- Feature delivery and completion
- Sprint progress and velocity
- Blockers and technical challenges affecting delivery
- Action items requiring attention

**Excluded**:
- Non-client work ([sic], networking, Build in Public)
- Internal initiatives and business development
- Personal activities

**Communication Style**:
- Sprint-focused organization
- Clear sections: Progress, In Progress, Blockers
- Technical detail appropriate for product decisions
- Action items with checkboxes
- ~250 words

## Key Takeaways

1. **Same raw material, different outputs**: Both summaries draw from the same daily notes but emphasize completely different aspects

2. **Audience-appropriate detail**: Manager gets strategic context; Client PO gets delivery details

3. **Saves time**: Instead of writing two separate updates from scratch, the workflow filters and synthesizes automatically

4. **Maintains relationships**: Each person gets information that helps them do their job better

5. **Creates a record**: The daily capture section preserves a complete record of the week's activities

## Time Investment

- **Daily capture**: 5-10 minutes per day (25-50 minutes/week)
- **AI generation**: 10-15 minutes (mostly automated)
- **Review and edit**: 10-15 minutes
- **Total**: ~45-80 minutes per week

**Compare to**: Writing two separate weekly updates from scratch (60-90 minutes each = 120-180 minutes)

**Time saved**: 40-100 minutes per week while improving communication quality
