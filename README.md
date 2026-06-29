# job-interview-prep

一个可复用的求职准备 AI Skill：从候选人知识库出发，调研公司、产品和面经，分析简历与 JD 的匹配度，预测 HR/业务面试问题，生成基于真实经历的回答，并提供投递前可直接发给 HR 的自然话术。

## 这是什么

`job-interview-prep` 不是通用面试题库，而是一套面向真实投递场景的研究与准备流程。它适合在投简历前或面试前使用，尤其适合：

- 想快速了解某家公司、岗位和产品的人
- 需要判断简历和 JD 是否匹配的人
- 正在跨行业、跨专业、跨岗位转型的人
- 产品、内容、AI、教育、出海、出版等需要业务理解和案例表达的岗位
- 想给 HR 发一句自然、不像模板的开场话术的人

核心流程包括：

- **候选人知识库**：从简历、个人网站、GitHub、作品集、LinkedIn、博客、历史项目和以往面试记录中整理候选人画像与 STAR 案例库。
- **公司与岗位调研**：搜索公司背景、发展现状、招聘信号、职场口碑、小红书/知乎/脉脉等帖子，以及角色相关面经。
- **产品深度调研**：当 JD 或招聘方提到具体产品时，单独分析产品定位、用户、UI/UX、优缺点、改进建议和可能被问到的产品题。
- **简历 × JD 匹配**：逐条拆解岗位要求，判断简历证据强弱，找出不清晰、不匹配或容易被 challenge 的点。
- **面试问题预测与回答**：预测 HR、部门负责人、业务、产品测评、跨行业转型等问题，并基于候选人真实经历起草回答。
- **中英双语准备**：英文 JD、英文面经、海外岗位或英文工作场景下，生成中英对照的面试题和模拟面试材料。
- **HR 打招呼话术**：在投递前生成中文、自然、具体、不像 AI 模板的 HR 开场消息，用来吸引注意并补齐简历可能没写清楚的匹配点。
- **可编辑交付物**：默认生成命名清晰的 Markdown 报告，必要时也可以生成 Word 文档，方便后续修改和复用。

## 仓库结构

```text
.
├── job-interview-prep/
│   └── SKILL.md                         # Claude Skill 源文件
├── job-interview-prep.skill             # Claude Skill 打包文件
├── codex-skill/
│   └── job-application-research/
│       ├── SKILL.md                     # Codex Skill 源文件
│       ├── agents/
│       │   └── openai.yaml
│       └── references/
│           ├── candidate-knowledge-base.md
│           └── report-template.md
└── README.md
```

## Codex 版

Codex 版位于：

```text
codex-skill/job-application-research/
```

它是当前更完整的版本，增加了：

- 投递前 HR 打招呼话术
- 可编辑 Markdown/Word 交付物要求
- 英文 JD/英文岗位的中英对照面试准备
- 更严格的产品调研与产品测评题
- 更完整的候选人知识库和项目案例库
- 对简历不清晰点的系统识别：title、年限、工具、数据、职责边界、跨行业解释等

使用方式：把 `codex-skill/job-application-research/` 放到你的 Codex skills 目录中，或按 Codex 当前版本支持的 skill 安装方式导入。

示例调用：

```text
Use $job-application-research to research this company and JD, assess my resume fit, prepare likely interview questions and answers, and write HR outreach messages before I apply.
```

## Claude 版

Claude 版位于：

```text
job-interview-prep/
job-interview-prep.skill
```

它保留了原始 Claude Skill 工作流，适合在 Claude Code、Claude Projects 或支持 Claude Skills 的环境中使用。

## 推荐输入

效果最好时，建议提供：

- 公司名称
- 岗位 JD 文本、截图或链接
- 简历 PDF/Word/文本
- 个人网站、GitHub、LinkedIn、作品集或博客
- 已知产品名
- 过往面试记录或你担心被问到的问题

材料不完整也可以使用。Skill 会继续分析，并明确标注哪些结论是已验证事实、来源支持推断、社交平台传闻，或只是基于现有材料的判断。

## 输出示例

完整分析通常会生成：

```text
YYYY-MM-DD_<公司>_<岗位>_job-research.md
candidate-knowledge-base_<姓名>.md
```

报告会包含：

- 公司/岗位/产品调研
- 面经与职场口碑摘要
- 简历与 JD 匹配表
- 简历不清晰点与优化建议
- HR 与业务面试预测题
- 基于真实经历的参考回答
- 产品测评问题与回答
- 跨行业/跨专业解释框架
- HR 打招呼话术
- 后续行动清单

## GitHub About

推荐仓库 About：

```text
Reusable AI skill for company research, resume-JD matching, interview prep, candidate knowledge bases, product deep-dives, and natural HR outreach messages.
```

推荐 Topics：

```text
job-search, interview-prep, resume, jd-matching, career, ai-skill, claude-skill, codex-skill, candidate-knowledge-base, hr-outreach, product-research
```

## 已知限制

- 公司、产品、面经和社交平台信息需要联网搜索；如果搜索不可用，输出应明确标注信息可能过时。
- 小红书、脉脉、Glassdoor、Blind、LinkedIn 等平台可能有登录墙或抓取限制，需要用户手动提供内容。
- 候选人知识库是一个实际文件，不是模型自动记忆。跨对话复用时，需要重新上传或放入项目知识库。
- Skill 不应编造候选人经历、数据或项目结果。材料不足时，应使用占位提示用户补充。

## License

MIT，见 [LICENSE](./LICENSE)。
