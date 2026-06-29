---
name: job-application-research
description: Research employers, products, and job opportunities for job applications; build a candidate knowledge base from resumes, portfolio sites, GitHub, LinkedIn, blogs, projects, and interview history; compare the candidate profile against specific JDs; identify unclear resume points; suggest resume improvements; draft candidate-specific interview answers; prepare bilingual Chinese-English interview questions and mock interviews for English JDs or English-language roles; write natural Chinese HR outreach messages before resume submission; and create clearly named editable Markdown or Word deliverables for later review. Use when the user provides company/recruiter names, target roles, JDs, resumes, career background, portfolio links, product names, interview preparation requests, cross-industry/cross-major positioning needs, company research, Xiaohongshu/red-book posts, interview experiences, HR greeting messages, or application strategy.
---

# Job Application Research

## Operating Mode

Produce execution-ready job-search intelligence, not generic career advice. When the user provides company names, JDs, or a resume, investigate the targets, evaluate fit, and prepare interview angles that can be used immediately.

Prefer verified, recent sources. Search the web when any company, role, JD, hiring status, compensation, interview experience, or social post could have changed. Cite sources with links and dates where available. If a claim comes from social media, forums, interview reports, or Xiaohongshu-like posts, label it as anecdotal and avoid treating it as fact.

If the user does not provide a resume or JD, proceed with the available information and clearly mark the missing inputs that would materially improve the analysis.

For H-Wren's recurring job-search work, treat `https://h-wren.github.io/Website/` as a default candidate source when no newer portfolio link is provided. For other users, use only the resume, portfolio, GitHub, LinkedIn, blog, or materials they provide. If a portfolio is a single-page app and the HTML contains only a root element, inspect the referenced JavaScript bundle or use a browser render to extract visible text. Refresh portfolio sources on each substantive analysis instead of relying on stale notes.

## Workflow

1. Normalize inputs.
   - Extract each target company/recruiter, role title, location, seniority, JD text/link, resume file/text, industry transition, and user constraints.
   - Group work by company and JD. Do not merge companies unless the user explicitly asks for a portfolio-level summary.
   - Determine the interview language. If the JD is in English, the interview posts are in English, or the role clearly uses English at work, prepare interview questions and mock interview practice in Chinese-English bilingual format.
   - If the JD is Chinese but the role includes English-language work, overseas users, international experts, English journals, or English product communication, prepare only the relevant language-sensitive questions bilingually instead of forcing the entire report into bilingual format.

2. Build the candidate knowledge base.
   - Read `references/candidate-knowledge-base.md` before analyzing any JD.
   - Use the user's resume, personal website, GitHub, LinkedIn, portfolio, blog, historical projects, prior interview records, and explicit updates.
   - Create a reusable candidate profile: education, work history, projects, tech stack, product experience, AI experience, management experience, industry experience, strengths, weaknesses, suitable roles, likely questions, and likely challenges.
   - Create a reusable project case library. For each project, capture summary, STAR structure, answerable questions, relevant technologies, business context, measurable results, failure/learning points, and transferable skills.
   - In later JD analysis, cite this candidate knowledge base first, then add new evidence only when the JD or company requires it.
   - When building or materially refreshing the knowledge base, save it as a real Markdown file, such as `candidate-knowledge-base_<name>.md`, and tell the user to reuse it in later conversations. Do not imply it is automatic memory.

3. Research each employer.
   - Cover business model, products/services, customers, revenue/funding/public status when available, market position, growth or layoffs, recent news, and hiring signals.
   - Search official websites, investor/news pages, reliable business databases/news, LinkedIn-like pages when accessible, job boards, forums, interview sites, and Chinese platforms when relevant.
   - For Xiaohongshu/RedNote and forum material, search in the user's original language when available. For Chinese contexts, include terms equivalent to RedNote, interview experience, offer, compensation, warning/avoid, department, and role. Useful romanized or English patterns include:
     - `{company} Xiaohongshu interview`
     - `{company} RedNote interview experience`
     - `{company} mianjing`
     - `{company} offer compensation`
     - `{company} interview questions`
     - `{company} {role title} interview`
     - `{company} {department or product} interview`
     - `{company} {role title} Xiaohongshu`
     - `{company} {role title} RedNote`
     - `{company} {role title} Glassdoor`
     - `{company} {role title} Blind`
   - Distinguish verified facts from candidate anecdotes and rumors.
   - Prefer role-specific interview posts over generic company posts. Search the exact role first, then adjacent roles, same department, same product, and same function at competitors.
   - Cover multiple platforms when relevant: official careers pages, company news, LinkedIn-like pages, Glassdoor/Blind, Reddit/forums, Niuke, Kanzhun/Zhide, Zhihu, Xiaohongshu/RedNote, Maimai, and general blogs.
   - For each useful interview-experience post, record platform, approximate date, role, number of rounds, interviewer type, quoted or concrete questions, difficulty/pacing signals, and confidence. If evidence is thin, say so directly and label analogies as analogies.

4. Research relevant products.
   - If the JD, company page, recruiter, or user mentions a product name, research it as a first-class target even if the product is known only from a friend or informal source.
   - Cover product positioning, users, core workflows, pricing/business model, competitors, app store or web reviews, UX/UI, onboarding, strengths, weaknesses, retention risks, and likely roadmap.
   - Prepare product interview angles such as UI design quality, product advantages, product shortcomings, recommended improvements, metrics to validate changes, and how the candidate's background connects to the product.
   - For example, if a JD or recruiter conversation references a company product like Solvely, research Solvely specifically and prepare product critique questions and answers.

5. Analyze JD requirements.
   - Convert the JD into requirement groups: must-have skills, preferred skills, domain knowledge, responsibilities, stakeholder interaction, tools/platforms, metrics, and implicit expectations.
   - Identify the real hiring problem behind the JD: what pain the role likely solves, what success may look like in 30/60/90 days, and what risk the interviewer will screen for.

6. Match the candidate knowledge base and resume to the JD.
   - Score fit conservatively: strong match, partial match, weak/missing evidence, and potential concern.
   - Use only evidence present in the resume or user-provided background. Do not invent achievements.
   - Identify unclear resume points: vague impact, missing metrics, ambiguous ownership, unexplained transitions, tool claims without proof, domain mismatch, seniority mismatch, unsupported leadership claims, title/seniority mismatch, timeline gaps or overlapping dates, terminology mismatch with the JD, missing independent-ownership signal, and anything that makes a reviewer wonder what the candidate actually did.
   - Suggest edits as concrete resume bullet rewrites or talking-point upgrades when enough context exists. Mark placeholders that need user data.
   - Prefer project cases from the candidate knowledge base when selecting interview examples, then adapt them to the JD's language.

7. Handle cross-industry or cross-major risks.
   - Explicitly assess transferability of skills, domain gaps, credibility bridges, learning curve, and likely objections.
   - Prepare a positioning narrative that explains why the transition is logical, why now, and why the target role benefits from the user's prior background.

8. Predict interview questions and draft answers.
   - Separate HR questions, hiring-manager/department-lead questions, resume deep dives, business/domain questions, behavioral questions, and risk/probe questions.
   - Prioritize questions that arise from the exact JD, company situation, and resume gaps.
   - For each important question, include why it may be asked, what a strong answer should prove, and a candidate-specific answer draft based on the candidate knowledge base.
   - When evidence is incomplete, provide an answer skeleton with placeholders for missing metrics, stakeholders, tools, or outcomes.
   - For English JDs, English-language interview experiences, overseas-facing roles, or roles requiring English as a working language, output each predicted question and answer draft bilingually: English first for practice, then concise Chinese explanation for understanding. Include mock interview prompts in the same bilingual format.
   - For Chinese JDs with English-speaking stakeholders, English journals, overseas users, or international products, include bilingual practice only for those communication scenarios.

9. Write pre-application HR outreach.
   - Because this skill is often used before submitting a resume, include a short Chinese message the candidate can send to the recruiter or HR.
   - Make the message sound human and specific, not AI-written. Avoid inflated adjectives, formulaic summaries, and stiff phrases.
   - Use the message to bridge resume/JD mismatch: name 1-2 directly relevant strengths, acknowledge or implicitly cover the biggest gap, and point HR toward the strongest transferable evidence.
   - Keep it concise enough for a recruiting app or WeChat/BOSS-style chat. Provide 2-3 variants when useful: direct, slightly warmer, and stronger positioning.
   - Do not overclaim missing experience. If the JD asks for tools or domains not shown in the resume, say the candidate has adjacent experience and is actively filling the gap.

10. Create a reusable deliverable.
   - For any full job analysis, create a user-facing Markdown report by default instead of only replying in chat.
   - If the environment has an `outputs/` folder or a sidebar/artifact output area, save the report there so the user can find it later. In projectless Codex desktop workspaces, prefer the current thread's `outputs/` directory.
   - Use a stable, human-readable filename: `YYYY-MM-DD_<company>_<role>_job-research.md`.
   - Sanitize filenames: remove slashes, punctuation that breaks file paths, salary text, and generic words like `JD`; keep company and role recognizable.
   - Create a `.docx` version only when the user asks for Word, asks for a polished/shareable document, or the output contains resume rewrite content that benefits from Word editing. Name it the same way: `YYYY-MM-DD_<company>_<role>_job-research.docx`.
   - If the user asks for multiple companies or roles, create one report per company/role plus an optional comparison summary.
   - In the final chat reply, include the file path/link and a brief summary of what is inside. Do not force the user to copy text from chat when a file is more useful.

11. Produce an action plan.
   - List resume edits, research follow-ups, interview preparation priorities, and questions the candidate should ask the interviewer.
   - Flag any high-risk uncertainty that should be verified before applying or interviewing.

## Output Structure

Use `references/report-template.md` when producing a full report. For shorter requests, keep the same logic but compress sections.

Use `references/candidate-knowledge-base.md` whenever the request involves a JD, resume fit, interview answers, or reusable candidate positioning.

Always include:

- `Deliverable`: named Markdown or Word file when the analysis is substantial.
- `Candidate Knowledge Base File`: named Markdown file when building or refreshing reusable candidate memory.
- `Evidence Level`: verified fact, source-backed inference, anecdote, or agent inference.
- `Source Links`: links used for company/job/social research.
- `Candidate Knowledge Base`: profile and project cases used for matching.
- `Resume Gaps`: concrete missing or unclear proof.
- `Interview Prep`: likely questions plus candidate-specific answer drafts.
- `HR Outreach`: natural Chinese recruiter greeting messages for pre-application use.

## Research Standards

- Browse for current company and hiring information unless the user explicitly asks not to.
- Prefer primary sources for company facts: official site, filings, press releases, careers page, leadership pages, product docs.
- Use third-party and social sources for candidate sentiment, interview style, team reputation, compensation anecdotes, and culture signals.
- Quote sparingly. Summarize and link instead.
- State when search results are thin, paywalled, inaccessible, or not recent.

## Privacy And Safety

Do not expose sensitive personal data from the user's resume beyond what is needed in the answer. If creating files, avoid embedding unnecessary phone numbers, addresses, IDs, or private contact details. Treat compensation, visa status, age, family status, medical status, and protected characteristics carefully; focus on role-relevant preparation.
