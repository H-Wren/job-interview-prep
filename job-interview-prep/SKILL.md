---
name: job-interview-prep
description: Use this skill whenever the user is preparing to apply for or interview at a company — researching the employer or its products, building a reusable candidate knowledge base (STAR case library, strengths/weaknesses) from their resume/portfolio/GitHub, checking resume-vs-JD match, predicting HR/hiring-manager interview questions, or drafting answers to those questions. Trigger on 求职, 投简历, 面试准备, 面经, JD匹配度, 简历优化, 内推, 拿到面试, 产品调研, 知识库, 候选人画像, or any time the user shares a company name plus a JD and/or resume/portfolio. Especially relevant for career/industry switchers (跨行业/跨专业转型) and product roles where the employer's own product may come up in the interview.
---

# Job Interview Prep

Helps a job seeker walk into an interview prepared: who the employer (and its product) actually is right now, how their resume/portfolio reads against this specific JD, what they're likely to be asked — by HR and by the hiring manager — and how they could actually answer those questions using their own real experience.

This is fundamentally a **research + analysis** skill, not a template-filling one. The value comes from grounding everything in (a) real, current information about the employer and its product, (b) the user's actual resume/portfolio against the actual JD, and (c) only the facts the user has actually provided. Resist the urge to produce boilerplate "tell me about yourself" style questions or generic-sounding model answers; every question and every answer should be traceable back to something specific in the research, the JD, or the resume/portfolio.

## Step 0: Gather inputs

Before starting, make sure you have, per company/role the user wants to prep for:

1. **Company name** (required)
2. **The JD** — pasted text, a screenshot/file, or a link. If the user only names the company without a JD, you can still do company research (Phase 1), but tell them resume-matching, question prediction, and answer drafting (Phases 2-4) need the actual JD.
3. **A Candidate Knowledge Base, if one already exists** — ask the user if they've already built one with this skill before (it would be a markdown file, something like `candidate-knowledge-base-[name].md`, or content pasted into a Claude Project's knowledge). If they have one, use it as the primary source for Phases 2 and 4 instead of re-deriving everything from raw materials — see Phase 0 below. If they don't have one yet, run Phase 0 to build it.
4. **Raw materials, if no Knowledge Base exists yet**: resume (check if already shared/uploaded — use the file-reading skill if it needs parsing), and optionally a portfolio/personal website, GitHub, blog, past project writeups, or notes from past interviews. These all feed Phase 0.

If the user gives you multiple companies at once, process them one at a time, each getting its own complete report. Build or load the Knowledge Base once, then reuse it across all of them — that's the whole point of having it.

Don't block on perfection — if something's missing, do what you can while you wait, and ask for the rest in the same message rather than stalling the whole task.

## Phase 0: Build or refresh the Candidate Knowledge Base

The biggest inefficiency in repeated job applications is re-deriving "what does this person's experience actually mean" from scratch every single time a new JD comes in. This phase does that analysis once, turns it into a standing artifact, and lets every later JD just reference it instead of re-reading the raw resume cold each time.

**This produces a real file, not automatic memory.** Be upfront with the user about this: it's a markdown file they need to save and bring back next time (re-upload it, or drop it into a Claude Project's persistent knowledge if they use Projects) — Claude doesn't retain it on its own between conversations.

**Sources to pull from** (use whatever the user has; don't require all of them):
- Resume (primary source, always)
- Portfolio / personal website — browse it if web access is available; otherwise ask the user to paste the relevant sections
- GitHub — if they give a username, public profile/repo data is reachable via the GitHub API (`api.github.com`) even without web search enabled; pull README content and repo descriptions for real project detail rather than guessing from repo names
- LinkedIn — don't try to browse this directly, it's behind a login wall and scraping it reliably won't work; ask the user to paste the relevant text or export their data instead
- Blog posts, past project writeups, past interview debriefs ("they asked me X, I answered Y, got pushback on Z") — anything the user offers
- Anything the user tells you directly that isn't written down anywhere else

**Build these three sections:**

```
# Candidate Knowledge Base — [姓名]
最后更新：[日期] ｜ 来源：[列出实际用到的来源]

## 基本画像
- 教育背景：
- 工作经历（按时间线）：
- 项目经历：
- 技术栈：
- 产品经验：
- AI 相关经验：
- 管理经验：
- 行业经验：

## 核心竞争力
- 最大优势：
- 最大短板：
- 适合的岗位方向：
- 最容易被问到的问题（基于经历本身，不针对特定JD）：
- 最容易被 challenge 的点：

## 可复用案例库
为每个有实质内容的项目/重要经历生成一条：

### [项目名]
- 简介：
- STAR：情境(S) / 任务(T) / 行动(A) / 结果(R)
- 这个案例能回答的问题类型：
- 相关技术：
- 相关业务：
- 数据成果（如有；没有就明确写"无量化数据"，不要编）：
- 遇到的问题/失败经验：
- 可迁移能力：
```

Write this with the same rigor as Phase 2 below — flag vague bullets, missing metrics, and unclear scope right here rather than carrying that ambiguity forward into every future JD analysis. This is the one place that ambiguity should actually get resolved (by asking the user), since it only needs to happen once.

Save the file (e.g. `/mnt/user-data/outputs/candidate-knowledge-base-[name].md`) and tell the user explicitly: save this, and bring it back next time instead of re-pasting your raw resume — that's what makes the next round faster and more consistent.

**Refreshing an existing Knowledge Base**: if the user provides one, skim it against whatever new material they've shared this time (an updated resume, a new project, a new portfolio piece). If something's changed or is missing from the KB, say so and offer to update the relevant section rather than silently trusting a possibly-stale file or silently ignoring the new information.

## Phase 1: Company research

Use web search for this — it's the only way to get current, ground-truth information. If web search isn't available in this conversation, say so explicitly and proceed only with whatever you reliably know, clearly flagged as potentially outdated or unverified — don't fill the gap with plausible-sounding invented content.

Run several distinct searches rather than one broad one — each angle surfaces different things:

- **Basics & business reality**: what the company actually does, who its customers are, how it makes money, where it sits versus competitors. Look for recent earnings, funding rounds, layoffs, pivots, product launches, leadership changes — not just the "about us" page.
- **Recent trajectory**: news from the last 6-12 months specifically — growth or contraction, new strategic direction, anything that would reasonably come up as "what do you know about us" or "why us."
- **职场口碑 / Xiaohongshu sentiment**: search things like `小红书 [公司名] 工作体验`, `小红书 [公司名] 职场`, `site:xiaohongshu.com [公司名]`, and similar on 知乎/脉脉. Look for recurring themes across *multiple* posts — culture complaints, praise, work-life balance reports, team-specific notes. Treat a single outlier post with appropriate skepticism.
- **面经 / interview experience — go deep here, this is often the highest-value research output.** Don't settle for a vague "they probably ask about X" summary pieced together from memory of common practice. Actually search and read multiple real posts:
  - Search the *exact role* first: `[公司名] [完整岗位名] 面经`, `[公司名] [岗位] 面试经验`, and only fall back to generic `[公司名] 面经` if role-specific results are thin — a generic company-wide 面经 for a totally different department is much less useful than a thinner but role-matched one.
  - Cover multiple platforms, since coverage varies a lot by company size and industry: 牛客网 (especially strong for tech/internet roles), 看准网/职得, 知乎, 小红书, 脉脉, and general web search for blog posts or forum threads.
  - For each useful post found, note: which platform, roughly how recent, what role it's for, and what it actually said — number of rounds, who interviewed (HR/业务/老板), specific question types or even specific questions quoted, and any signal on difficulty or pace. Cite multiple sources rather than synthesizing from just one post passing as "the truth."
  - If you genuinely can't find role-specific 面经 (small company, niche role), say that directly and fall back to whatever adjacent information exists (e.g. 面经 for a similar role at a similar-stage company), clearly labeled as an analogy, not a fact about this company.

Synthesize into a compact research brief — don't dump raw search results:

```
## [公司名] 调研简报

**业务现状**：[2-4句话：做什么、怎么赚钱、市场位置]

**近期动态**：[bullet list of recent, dateable developments — note approximate dates]

**职场口碑（小红书/知乎等）**：[recurring themes, both positive and negative, noting it's anecdotal]

**面试流程与面经要点**：[rounds, typical interviewers, recurring/quoted question patterns — cite platform + rough date per finding, e.g. "(牛客网, 2025年底, XX岗位)"]
```

If results are thin, say so plainly rather than padding with filler.

## Phase 1.5: Product deep-dive (when the JD/company centers on a specific product)

Many product, design, growth, and content roles will surface the company's own product in the interview — directly ("walk me through this product" / "如果让你改进这个产品你会怎么做") or indirectly. Run this phase whenever the JD names a specific product/app, or the user tells you which product the company is known for (they may need to tell you this directly — product names, especially for smaller or newer companies, are often not obvious from the company name alone).

Research the product itself, not just the company:

- **What it is and who it's for**: core use case, target users, how it's positioned versus alternatives
- **What it actually looks/feels like**: search for screenshots, app store listings, review videos, or walkthroughs — if you can describe the actual UI/UX rather than guessing, do
- **Reception**: app store reviews, 小红书/知乎测评, Reddit/forum threads if it's an overseas-facing product — look for recurring praise and recurring complaints, not a single review
- **Your own read**: based on the above, form an actual point of view — what seems to genuinely work well, what seems weak or dated, and one or two concrete, specific improvement ideas (not "improve the UX" — something like "the onboarding flow seems to require N steps before showing any value, could front-load a quick win"). This matters because the interview question is rarely just "describe the product" — it's "critique it," and a vague non-committal answer reads worse than a specific, fair one.

This feeds directly into Phase 3 — these become some of the most memorable, differentiating questions to prep for, and ones generic interview prep can't help with.

## Phase 2: Resume/portfolio × JD match analysis

If a Candidate Knowledge Base exists (from Phase 0), use it as the primary source here instead of re-reading the raw resume cold — the case library entries are already cleaned up and metric-checked, so pulling from them keeps this consistent across every company instead of re-deriving slightly different framings each time. Fall back to the raw resume/portfolio only for anything the KB doesn't cover yet.

1. **Extract JD requirements**: the concrete things the JD asks for — required skills, years of experience, domain knowledge, tools, soft-skill signals, anything implied by the role's seniority or scope.

2. **Map the Knowledge Base (or resume/portfolio) against each requirement**: for each JD requirement, note whether it's clearly addressed, weakly/implicitly addressed, or not addressed at all. If pulling from the case library, point to the specific project entry being used. If a portfolio is provided and isn't in the KB yet, check it for concrete examples the resume only gestures at.

3. **Flag what's unclear** — this is the part most often skipped, and most useful:
   - Bullets that describe activity but not outcome/impact (no numbers, no result)
   - Vague scope ("参与了xx项目" without saying what they actually owned vs. just touched)
   - Terminology mismatches — resume uses different words than the JD for what might be the same skill
   - Gaps in seniority signal — JD wants "独立负责" but resume reads like a supporting contributor
   - Title/seniority mismatches — e.g. a self-given headline title that doesn't match the actual job titles listed in the experience section; this is the kind of thing a reviewer notices immediately and will ask about
   - Timeline oddities — gaps, overlapping dates, or end dates that don't line up with the current date — don't silently ignore these, but also don't assume they're errors; flag them as something the user should be ready to explain
   - Anything that would make a reviewer go "wait, what did they actually do here?"

4. **Give concrete rewrite suggestions**, not just "be more specific" — show an actual before/after for the weakest 3-5 bullets, pulling in JD language where truthfully applicable. Never invent accomplishments, metrics, or scope the user didn't claim — the fix is sharper framing of what's already true, or explicitly flagging "you'd need to supply a number here" rather than making one up.

Present as:

```
## 简历 × JD 匹配分析 — [公司名] [岗位]

### 匹配较好的部分
- [JD要求] ← [简历/作品集中对应内容，简要点出]

### 待补强/不清晰的部分
| JD 要求 | 简历现状 | 问题 | 优化建议（含改写示例） |
```

If the resume is strong across the board, say that clearly too — don't manufacture problems to seem thorough.

## Phase 3: Predicted interview questions

Build this directly from Phases 1, 1.5, and 2 — every question should trace back to something specific, not be a generic interview-question-bank item.

**HR 面试官通常关注**：
- 动机与稳定性：为什么离开上一家、为什么是这个行业/这家公司、职业规划是否合理
- 文化匹配：基于 Phase 1 的职场口碑调研，反推 HR 可能用什么问题来验证候选人是否适配
- 薄弱点追问：从 Phase 2 的"不清晰的点"里，挑出 HR 最可能直接问出口的那几个（空窗期、频繁跳槛、年限差距、title不一致等）

**部门负责人/业务面通常关注**：
- 岗位核心能力深挖：针对 JD 最核心的1-3项要求，设计追问候选人简历/作品集中相关经历的具体问题
- 业务理解题：结合 Phase 1 的业务现状和近期动态
- 场景/案例题：贴近真实工作场景的情境问题
- **产品测评题**（若做了 Phase 1.5）：这是产品类岗位的经典题型，几乎一定会被问到某种变体，例如"你怎么看我们这款产品的UI设计"、"你觉得它最大的优点/缺点是什么"、"如果是你来负责，你会怎么改进"。基于 Phase 1.5 的实际调研结果出题，而不是用空泛的产品测评模板。

**跨行业/跨专业转型类追问**：对比简历背景/专业与 JD 所在行业，若有明显跨度，单独列一组：
- 为什么从 [原行业/专业] 转向 [目标行业]，动机是否经得起推敲
- 哪些能力可迁移，候选人是否能讲清楚映射关系而不是泛泛而谈
- 候选人对目标行业/岗位的基本认知是否到位
- 候选人如何弥补领域知识差距，准备周期是否合理

## Phase 4: Draft answers grounded in the resume/portfolio

If a Candidate Knowledge Base exists, pull from its case library first — the STAR breakdowns there are built for exactly this. Reuse the same case across multiple questions where it genuinely fits rather than forcing a different project into every answer.

For each predicted question (or the ones the user flags as priority), draft a real answer attempt — not just a tip about what a good answer should hit. This is what turns a list of scary questions into something the user can actually rehearse.

**The one rule that matters most here: only use facts the user has actually provided** (resume, portfolio, or things said earlier in the conversation). This is not the place to be helpful by inventing a plausible-sounding metric, project detail, or outcome — a fabricated answer that falls apart under a follow-up question is worse than no answer. When the resume/portfolio doesn't contain something a strong answer would need (a specific number, a specific tool, a specific user-facing example), don't paper over the gap — write the answer as far as the real material supports it, then explicitly mark what's missing, e.g. "（这里需要你补充一个具体数字/案例，简历里没有写）" or "（你目前没有这方面的直接经验，下面是一个可以诚实回应+展示学习能力的框架，不是真实经历）."

For motivation/transition-type questions (why this industry, why this company, why this product), it's fine — and often necessary — to draft a reasonable, sincere-sounding narrative, since these are inherently about framing rather than facts the resume would contain. But keep it grounded in what's actually true about the person's trajectory (their real background, real stated interests) rather than fabricating specific anecdotes.

Format per question:

```
**Q: [面试问题]**
A（参考思路）：[draft answer using only real resume/portfolio facts, citing which experience it draws on; explicit gap-flags where the material runs out]
```

Group these the same way the questions were grouped (HR / 部门负责人 / 产品测评 / 跨行业追问), so the user can rehearse by category.

## Putting it together

Default to presenting everything directly in the conversation as a structured Markdown report — that's what most users want since they're reading this while prepping, not archiving it. Only create a downloadable Word document if the user asks to save/export it (use the docx skill for that). The Candidate Knowledge Base from Phase 0 is the one exception — that should always be saved as an actual file, since its whole value is being carried into future conversations.

When handling multiple companies, give each its own clearly-headed section following the same structure, so the user can compare across companies.

End by asking what's most useful next — e.g., mock-interviewing them live on the toughest questions, tightening specific resume bullets further, or going deeper on one company's product — rather than assuming the report alone is the end of the task.
