# Candidate Knowledge Base

Build this before analyzing any JD. Treat it as the working memory for the current job-search task. Refresh it from source materials when new sources are provided or when the user's portfolio may have changed.

## Default Sources

Use any available sources, including:

- Resume files or pasted resume text.
- Personal website or portfolio. For H-Wren's recurring work, default to `https://h-wren.github.io/Website/` unless a newer source is provided; for other users, use only sources they provide or authorize.
- GitHub, LinkedIn, portfolio projects, blog posts, videos, demos, prior interview notes, and user-provided updates.

If a source is a single-page app, inspect rendered page text, linked bundles, metadata, and visible project sections. Do not assume the raw HTML contains all content.

For GitHub profiles or repositories, use public README files, repo descriptions, topics, releases, and commit context when available. Do not infer project depth from repo names alone.

For LinkedIn, do not assume direct browsing will work because login walls are common. Ask the user to paste, export, or screenshot relevant content if it is not accessible.

## Source Handling

- Mark every profile claim with source type: resume, website, GitHub, LinkedIn, user-provided, interview record, or inference.
- Prefer the latest user-provided information over older public pages.
- Do not treat the website as immutable truth. It is a strong long-term memory source, but it may be incomplete or outdated.
- Keep private details out of final outputs unless they are role-relevant.
- Save the knowledge base as a real Markdown file when building or materially refreshing it. Recommended filename: `candidate-knowledge-base_<name>.md`.
- Tell the user to reuse this file in future job-analysis conversations or store it in their project knowledge. Do not describe it as automatic memory.

## Profile Schema

Create a concise candidate profile with:

- Education background.
- Work experience.
- Project experience.
- Technical stack.
- Product experience.
- AI experience.
- Management or coordination experience.
- Industry experience.
- Languages and cross-cultural experience when relevant.
- Career direction and target role assumptions.

## Competitiveness Summary

Summarize:

- Biggest advantages.
- Biggest weaknesses.
- Best-fit role types.
- Roles with higher transition risk.
- Questions the candidate is most likely to be asked.
- Questions or challenges the candidate is most vulnerable to.
- Evidence that should be strengthened before interviewing.
- Resume inconsistencies or ambiguity to fix once, so later JD analysis can reuse cleaner evidence.

## Reusable Project Case Library

For every project or major workstream, create a reusable case:

- Project name:
- Source:
- One-line summary:
- Context:
- Task:
- Actions:
- Result:
- Metrics or evidence:
- Related technologies:
- Related business/domain:
- Product or user insight:
- Failure, tradeoff, or lesson:
- Transferable skills:
- Interview questions this project can answer:
- Missing details to ask the user:

Use STAR when drafting answers, but do not force every project into a rigid STAR format if the available evidence is thin.

Flag weak or ambiguous project entries immediately:

- Activity without outcome or measurable result.
- Unclear ownership or collaboration scope.
- Tool or technical claim without evidence.
- Seniority/title mismatch.
- Timeline gap, overlap, or stale end date.
- Missing stakeholder, user, business, or domain context.
- Missing failure, tradeoff, or lesson learned.

## Matching Rules

- For each JD requirement, first search the knowledge base for direct evidence.
- If direct evidence is missing, look for transferable project cases and state the gap honestly.
- Convert candidate evidence into JD language without exaggerating seniority, ownership, metrics, or technical depth.
- Use the case library to draft interview answers, resume bullets, and recruiter positioning.

## Answer Drafting Rules

For predicted interview questions, produce answer drafts in this format:

- Question:
- Why they may ask:
- Answer draft:
- Evidence used:
- Stronger version if user can provide more data:
- Risk to avoid:

If data is missing, use placeholders such as `[metric needed]`, `[stakeholder needed]`, or `[tool detail needed]`.
