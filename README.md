# 个人项目包装与面试备战 (Project Showcase Enhancer)

> 将 Demo 级个人项目推演为商用级完整产品，生成可用于简历网站 / GitHub 的项目展示文档，并结合 JD + 简历输出项目相关的面试备考手册。

---

## 目录

- [中文文档](#中文文档)
  - [这是什么](#这是什么)
  - [为什么需要它](#为什么需要它)
  - [核心特性](#核心特性)
  - [适用人群](#适用人群)
  - [安装](#安装)
  - [使用方法](#使用方法)
  - [工作流程：四阶段闭环](#工作流程四阶段闭环)
  - [内置脚本](#内置脚本)
  - [混合架构](#混合架构)
  - [模型要求](#模型要求)
  - [目录结构](#目录结构)
  - [输出示例](#输出示例)
  - [常见问题](#常见问题)
  - [许可证](#许可证)
- [English](#english)
  - [What it is](#what-it-is)
  - [Why you need it](#why-you-need-it)
  - [Key features](#key-features)
  - [Who it is for](#who-it-is-for)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Workflow: four-stage loop](#workflow-four-stage-loop)
  - [Bundled scripts](#bundled-scripts)
  - [Hybrid architecture](#hybrid-architecture)
  - [Model requirements](#model-requirements)
  - [Directory layout](#directory-layout)
  - [Example output](#example-output)
  - [FAQ](#faq)
  - [License](#license)

---

# 中文文档

## 这是什么

**个人项目包装与面试备战** 是一个 WorkBuddy 技能（Skill），面向开发者，解决一个具体问题：

> 你有一个能跑的个人项目 / Demo，但不知道怎么把它**讲清楚、写专业、准备面试**。

它不是"扫一遍代码吐模板"的工具，而是一套**人机协作的工作流**：先读懂你的代码与原始意图，再和你一起把 Demo 推演成商用级产品方案，最后产出两份可直接使用的文档——**项目展示文档**和**面试备考手册**。

## 为什么需要它

个人开发者在整理项目时常遇到三件事：

1. **看不懂自己的项目该写什么**：代码能跑，但项目说明只会写"基于 React + Node 做的博客"，提炼不出亮点和架构思维。
2. **Demo 离商用差得远却说不清差在哪**：缺权限、缺异常处理、缺测试、架构粗糙，但不知道优先级。
3. **面试官一追问就露怯**：简历写了"主导开发 XX 项目"，被问技术选型理由、最大挑战、重来会改什么，答不上来。

本技能把这三件事一次性解决：分析代码 → 推演商用 → 生成展示文档 → 预测面试题。

## 核心特性

- **真实读懂代码**：先用脚本做确定性扫描，再由大模型阅读关键源文件，理解业务逻辑、模块划分、数据流，而不是靠文件名猜。
- **Demo 到商用的推演**：结合你的产品愿景，列出功能 / 工程化 / 运维三方面的差距，给出分阶段演进路线图（MVP → 完善 → 商用）。
- **项目展示文档**：按模板生成亮点、功能模块、技术栈选型理由、架构设计、部署说明，排版精良，直接可放简历网站或作为 README。
- **面试备考手册**：结合 JD 和简历，预测 15 道项目相关面试题（必问 / 针对性 / 追问三类），每题给考察点、答题策略和 STAR 框架。
- **混合架构**：脚本做快而稳的扫描，大模型做深而准的推理，兼顾速度与质量，也不浪费 token。

## 适用人群

- 准备求职面试、需要把个人项目写进简历的开发者
- 维护作品集网站 / 技术博客，希望项目介绍更专业的人
- 想把练手 Demo 升级为可展示、可部署产品的全栈工程师
- 需要结合目标岗位 JD 预判面试官会追问什么的技术候选人

## 安装

本技能以目录形式存放，复制到 WorkBuddy 的用户级技能目录即可，无需编译或安装依赖。

**方式一：从 GitHub 克隆**

```bash
# 克隆到用户级技能目录（Windows 示例，使用 Git Bash）
git clone https://github.com/whishi47/project-showcase-enhancer.git \
  "$HOME/.workbuddy/skills/project-showcase-enhancer"
```

**方式二：从压缩包解压**

1. 下载 `project-showcase-enhancer.zip`
2. 解压到 `$HOME/.workbuddy/skills/project-showcase-enhancer/`
3. 确保目录下直接包含 `SKILL.md`

**方式三：SkillHub 安装**

在 SkillHub 市场搜索 `project-showcase-enhancer` 并安装。

> `$HOME` 在 Windows 上通常是 `C:\Users\你的用户名`。技能目录也可能是 `.codebuddy\skills`，以你使用的客户端为准。

安装后，在 WorkBuddy 对话中直接用自然语言触发即可（见"使用方法"）。

## 使用方法

在 WorkBuddy 对话里说下面任意一句，技能就会启动：

- "分析一下我的项目"
- "帮我把这个项目推演到商用"
- "生成一份项目展示文档"
- "结合我的 JD 准备这个项目的面试"

首次触发时，技能会一次性问你四件事（不用逐条回答）：

1. **项目路径**：要分析的项目在哪个目录？
2. **使用场景**：个人简历 / 面试 / GitHub 展示 / 作品集网站？
3. **目标岗位方向**（可选）：前端 / 后端 / 全栈 / 架构等，用于面试题的针对性。
4. **特别说明**（可选）：你对这个项目的原始想法、想突出的点。

如果你同时提供了简历文件（PDF / DOCX / TXT），技能会先解析成纯文本，供面试准备阶段使用。

## 工作流程：四阶段闭环

### 阶段 0：项目定位

收集项目路径、使用场景、目标岗位、原始意图。如有简历文件，运行 `scripts/parse_file.py` 解析。

### 阶段 1：深度代码理解

**1.1 快速扫描（脚本层）**——运行 `scripts/scan_project.js`，秒级输出结构化 JSON，包含技术栈、依赖、目录树（带职责标注）、入口文件、配置文件、README 原文。

**1.2 深度阅读（大模型层）**——基于扫描结果，阅读关键源文件，分析：

- 每个关键依赖的用途、版本是否合理、有无替代方案
- 模块划分与数据流
- 入口文件的启动流程、路由、中间件
- 配置文件里的部署环境与第三方服务
- 从 README 提取的产品原始意图

**1.3 代码质量评估**——对 8 个维度打分（1–10）并给出具体证据（文件名 + 行号）：

| 维度 | 维度 |
|------|------|
| 代码组织与模块化 | 错误处理 |
| 类型安全 | 测试覆盖 |
| 安全性 | 性能设计 |
| 可部署性 | 文档完整度 |

**1.4 现状总结**——用一段话描述项目当前状态，和你确认后进入下一阶段。

### 阶段 2：商用推演对话

**2.1 理解愿景**——通过对话了解目标用户、核心卖点、商业模式（可选）、上线紧迫度与 MVP 范围。

**2.2 差距分析**——列出三类差距：

```
【功能差距】缺失的功能点 + 优先级(P0/P1/P2) + 说明
【工程化差距】缺失的工程实践 + 为什么需要 + 建议方案
【运维差距】缺失的运维能力 + 为什么需要 + 建议方案
```

**2.3 演进路线图**——分三阶段（MVP → 完善 → 商用），每阶段列关键任务。

**2.4 确认**——展示完整差距分析与路线图，确认后进入下一阶段。

### 阶段 3：生成交付物

**3.1 项目展示文档**——读取 `assets/showcase-template.md` 填充：

- 核心亮点（5 个，每个有代码或架构证据）
- 功能模块（按业务领域组织）
- 技术栈（每项说明选型理由）
- 架构设计（整体架构 + 数据流 + 核心决策）
- 演进记录、部署说明

输出文件：`{项目名称}-展示文档.md`

**3.2 面试备考手册**——读取 `assets/interview-prep-template.md`，生成 15 道题：

- 必问题（5 题）：介绍项目、负责部分、最大挑战、技术选型理由、重来会改什么
- 针对性题（5 题）：关联代码低分维度或差距项
- 追问题（5 题）：关联具体代码文件或设计决策

每题结构：题目 → 考察点 → 答题策略 → STAR 框架。

输出文件：`{项目名称}-面试备考手册.md`

**3.3 最终确认**——展示两份文档摘要，确认准确性与格式。

## 内置脚本

### `scripts/scan_project.js`

硬编码字典扫描项目，输出结构化 JSON。不调用大模型，速度快、确定性强。

```bash
# 用法
node scripts/scan_project.js <项目目录>

# 示例：分析当前目录
node scripts/scan_project.js ./my-project
```

输出 JSON 字段：

| 字段 | 内容 |
|------|------|
| `techStack` | 按 runtime / framework / build / css / test / orm / deploy 分类的技术栈 |
| `dependencies` | 完整依赖列表 |
| `directoryStructure` | 带职责标注的目录树 |
| `entryFiles` | 检测到的入口文件 |
| `configFiles` | 配置文件清单 |
| `readmeContent` | README 原文（最多 5000 字符） |
| `packageJson` | 项目元信息 |
| `fileStats` | 文件统计 |

### `scripts/parse_file.py`

把简历 PDF / DOCX / TXT 解析为纯文本，供面试准备阶段使用。

```bash
# 用法
python scripts/parse_file.py <简历文件路径>

# 示例
python scripts/parse_file.py ./resume.pdf
```

依赖：`pdfplumber` 或 `pypdf`（PDF）、`python-docx`（DOCX）。未安装时脚本会提示安装命令。

## 混合架构

本技能同时用脚本和大模型，而不是只用其中一种：

- **确定性扫描层（脚本）**：`scan_project.js` 覆盖 60+ 技术栈标志文件、40+ 目录职责映射、入口与配置文件自动检测、package.json 依赖全量提取，秒级产出 JSON。稳定、可重复、不消耗 token。
- **语义推理层（大模型）**：在扫描结果之上做真正的代码语义理解与推演，避免纯字典匹配的模板化缺陷。

两者结合，扫描给大模型一份"地图"，大模型在地图上做深度分析。

## 模型要求

本技能依赖高推理能力的大模型。**推荐在高推理模型下使用**：

- Claude Opus 4.6
- DeepSeek v4 Pro
- GPT-5.6（或同等级别）

低推理模型可能导致：代码理解肤浅、商用推演模板化、面试题预测质量差。技能启动时会在阶段 0 提示你确认当前模型，若不满足建议切换后再用。

## 目录结构

```
project-showcase-enhancer/
├── SKILL.md                          # 技能主文件（工作流定义）
├── README.md                         # 本文档
├── scripts/
│   ├── scan_project.js               # 项目扫描器：字典匹配 → JSON
│   └── parse_file.py                 # 简历解析器：PDF/DOCX/TXT → 文本
└── assets/
    ├── showcase-template.md          # 项目展示文档模板
    └── interview-prep-template.md    # 面试备考手册模板
```

## 输出示例

**项目展示文档**片段：

```markdown
## 核心亮点
1. 基于 WebSocket 的实时协作：在 `src/server/ws.js` 用单 Room 管理连接，
   支持 200+ 并发不掉线（压测证据见 deploy/load-test.md）。
2. 类型安全的端到端数据流：前后端共享 `types/` 下的 TS 接口，减少 80% 接口联调错误。
...
```

**面试备考手册**片段：

```markdown
### 必问题 3：项目遇到的最大技术挑战是什么？
- 考察点：解决问题的深度与复盘能力
- 答题策略：用 STAR 讲一个具体困难，突出你的决策
- STAR：
  - Situation：实时同步在弱网下频繁冲突
  - Task：保证多端数据一致
  - Action：引入 CRDT（具体见 src/sync/crdt.ts）
  - Result：冲突率从 12% 降到 0.3%
```

## 常见问题

**Q：一定要用高推理模型吗？**
A：不是必须，但建议。低推理模型仍能用，只是分析和推演的质量会下降。

**Q：我的项目不是 Web 应用，能用吗？**
A：能。扫描脚本覆盖多种技术栈标志文件，大模型也能理解非 Web 项目（CLI 工具、库、脚本等）。

**Q：简历文件必须是 PDF 吗？**
A：支持 PDF、DOCX、TXT。没有简历文件也能用，只是面试备考会少一份 JD 匹配的输入。

**Q：输出的文档会乱编内容吗？**
A：不会。技能约束：展示文档的亮点必须有代码或架构依据，面试题必须关联项目中的具体文件。

## 许可证

本项目以 MIT 许可证开源。详见 [LICENSE](./LICENSE)。

---

# English

## What it is

**Project Showcase Enhancer** is a WorkBuddy skill for developers. It solves one concrete problem:

> You have a working personal project or demo, but you do not know how to **explain it clearly, write it professionally, or prepare for interviews about it.**

It is not a "scan the code and emit a template" tool. It is a **human-in-the-loop workflow**: first it reads your code and your original intent, then it works with you to evolve the demo into a commercial-grade product plan, and finally it produces two ready-to-use documents — a **project showcase document** and an **interview prep guide**.

## Why you need it

Individual developers hit three problems when organizing their projects:

1. **They cannot write about their own project.** The code runs, but the project description says only "a blog built with React + Node," with no way to surface the highlights or the architectural thinking.
2. **They cannot say what separates a demo from a shippable product.** Permissions, error handling, tests, and a rough architecture are all missing, but the priorities are unclear.
3. **They freeze when an interviewer follows up.** The resume says "led development of project X," but they cannot answer why a technology was chosen, what the hardest challenge was, or what they would change.

This skill handles all three in one pass: analyze code → evolve to commercial → generate showcase doc → predict interview questions.

## Key features

- **Real code comprehension:** a script does a deterministic scan, then the model reads the key source files to understand business logic, module boundaries, and data flow — not guesswork from file names.
- **Demo-to-commercial evolution:** given your product vision, it lists gaps across functionality, engineering, and operations, then gives a phased roadmap (MVP → polish → commercial).
- **Project showcase document:** fills a template with highlights, feature modules, tech-stack rationale, architecture design, and deployment steps, formatted to drop straight into a portfolio site or README.
- **Interview prep guide:** given a JD and a resume, it predicts 15 project-specific interview questions (must-ask / targeted / follow-up), each with the point being tested, an answer strategy, and a STAR framework.
- **Hybrid architecture:** a script does the fast, stable scan; the model does the deep, accurate reasoning — balancing speed and quality while saving tokens.

## Who it is for

- Developers preparing for job interviews who need to put personal projects on a resume
- People maintaining a portfolio site or tech blog who want more professional project write-ups
- Full-stack engineers who want to upgrade a practice demo into a presentable, deployable product
- Technical candidates who need to predict, from a target JD, what an interviewer will ask

## Installation

The skill ships as a directory. Copy it into WorkBuddy's user-level skills directory. No build step or dependency install is required.

**Option 1: Clone from GitHub**

```bash
# Clone into the user-level skills directory (Windows example, Git Bash)
git clone https://github.com/whishi47/project-showcase-enhancer.git \
  "$HOME/.workbuddy/skills/project-showcase-enhancer"
```

**Option 2: Extract from the zip**

1. Download `project-showcase-enhancer.zip`
2. Extract it to `$HOME/.workbuddy/skills/project-showcase-enhancer/`
3. Make sure `SKILL.md` sits directly inside that directory

**Option 3: Install from SkillHub**

Search for `project-showcase-enhancer` on SkillHub and install it.

> On Windows, `$HOME` is usually `C:\Users\your-username`. The skills directory may also be `.codebuddy\skills` depending on your client.

After installation, trigger the skill with plain language in a WorkBuddy conversation (see Usage).

## Usage

Say any of the following in a WorkBuddy conversation to start the skill:

- "Analyze my project"
- "Help me evolve this project to commercial grade"
- "Generate a project showcase document"
- "Prepare me for an interview on this project using my JD"

On first trigger, the skill asks four things at once (answer them together, not one by one):

1. **Project path:** which directory holds the project to analyze?
2. **Use case:** personal resume / interview / GitHub showcase / portfolio site?
3. **Target role** (optional): frontend / backend / full-stack / architecture — used to target the interview questions.
4. **Notes** (optional): your original idea for the project, or points you want emphasized.

If you also provide a resume file (PDF / DOCX / TXT), the skill parses it to plain text first for the interview-prep stage.

## Workflow: four-stage loop

### Stage 0: Project scoping

Collect the project path, use case, target role, and original intent. If a resume file is provided, run `scripts/parse_file.py` to parse it.

### Stage 1: Deep code comprehension

**1.1 Quick scan (script):** run `scripts/scan_project.js` to emit a structured JSON in seconds — tech stack, dependencies, directory tree (with role annotations), entry files, config files, and the README text.

**1.2 Deep reading (model):** using the scan, read the key source files and analyze:

- the purpose of each key dependency, whether its version is reasonable, and alternatives
- module boundaries and data flow
- the entry file's startup flow, routing, and middleware
- deployment environment and third-party services from config files
- the original product intent extracted from the README

**1.3 Code quality assessment:** score 8 dimensions (1–10) with concrete evidence (file name + line number):

| Dimension | Dimension |
|-----------|-----------|
| Code organization & modularity | Error handling |
| Type safety | Test coverage |
| Security | Performance design |
| Deployability | Documentation completeness |

**1.4 Status summary:** describe the project's current state in a paragraph, confirm with the user, then move on.

### Stage 2: Commercial evolution dialogue

**2.1 Understand the vision:** through dialogue, learn the target users, core selling point, business model (optional), launch urgency, and MVP scope.

**2.2 Gap analysis:** list three kinds of gaps:

```
[Functional gaps] missing feature + priority (P0/P1/P2) + note
[Engineering gaps] missing practice + why needed + suggested fix
[Operations gaps] missing capability + why needed + suggested fix
```

**2.3 Evolution roadmap:** three phases (MVP → polish → commercial), each with key tasks.

**2.4 Confirm:** show the full gap analysis and roadmap, confirm, then move on.

### Stage 3: Produce deliverables

**3.1 Project showcase document** — read `assets/showcase-template.md` and fill it:

- Core highlights (5, each backed by code or architecture evidence)
- Feature modules (grouped by business domain)
- Tech stack (with rationale per choice)
- Architecture design (overall + data flow + key decisions)
- Evolution record and deployment steps

Output file: `{project-name}-展示文档.md`

**3.2 Interview prep guide** — read `assets/interview-prep-template.md` and generate 15 questions:

- Must-ask (5): introduce the project, your part, the hardest challenge, why a technology was chosen, what you would change
- Targeted (5): tied to low-scoring code dimensions or gap items
- Follow-up (5): tied to specific code files or design decisions

Each question: prompt → what is tested → answer strategy → STAR framework.

Output file: `{project-name}-面试备考手册.md`

**3.3 Final confirmation:** show a summary of both documents and confirm accuracy and format.

## Bundled scripts

### `scripts/scan_project.js`

Scans a project with a hard-coded dictionary and emits structured JSON. It does not call a model, so it is fast and deterministic.

```bash
# Usage
node scripts/scan_project.js <project-directory>

# Example: analyze the current directory
node scripts/scan_project.js ./my-project
```

JSON fields:

| Field | Content |
|-------|---------|
| `techStack` | Tech stack grouped by runtime / framework / build / css / test / orm / deploy |
| `dependencies` | Full dependency list |
| `directoryStructure` | Directory tree with role annotations |
| `entryFiles` | Detected entry files |
| `configFiles` | Config file list |
| `readmeContent` | README text (up to 5000 chars) |
| `packageJson` | Project metadata |
| `fileStats` | File statistics |

### `scripts/parse_file.py`

Parses a resume PDF / DOCX / TXT into plain text for the interview-prep stage.

```bash
# Usage
python scripts/parse_file.py <resume-file-path>

# Example
python scripts/parse_file.py ./resume.pdf
```

Dependencies: `pdfplumber` or `pypdf` (PDF), `python-docx` (DOCX). The script prints the install command if a dependency is missing.

## Hybrid architecture

The skill uses both a script and a model, not one alone:

- **Deterministic scan layer (script):** `scan_project.js` covers 60+ tech-stack marker files, 40+ directory-role mappings, automatic entry/config detection, and full package.json dependency extraction, producing JSON in seconds. It is stable, repeatable, and uses no tokens.
- **Semantic reasoning layer (model):** on top of the scan, it performs real code comprehension and evolution, avoiding the template-filling weakness of pure dictionary matching.

Together, the scan gives the model a map, and the model does the deep analysis on that map.

## Model requirements

The skill depends on a high-reasoning model. **Use one of these:**

- Claude Opus 4.6
- DeepSeek v4 Pro
- GPT-5.6 (or equivalent)

A low-reasoning model may still run, but code comprehension will be shallow, commercial evolution generic, and interview predictions weak. At Stage 0 the skill prompts you to confirm the current model and suggests switching if it does not meet the bar.

## Directory layout

```
project-showcase-enhancer/
├── SKILL.md                          # Skill definition (workflow)
├── README.md                         # This document
├── scripts/
│   ├── scan_project.js               # Project scanner: dictionary match → JSON
│   └── parse_file.py                 # Resume parser: PDF/DOCX/TXT → text
└── assets/
    ├── showcase-template.md          # Project showcase document template
    └── interview-prep-template.md    # Interview prep guide template
```

## Example output

**Project showcase document** excerpt:

```markdown
## Core highlights
1. WebSocket-based real-time collaboration: src/server/ws.js manages connections
   in a single Room and holds 200+ concurrent users without drops (see deploy/load-test.md).
2. Type-safe end-to-end data flow: frontend and backend share TS interfaces in types/,
   cutting integration errors by 80%.
```

**Interview prep guide** excerpt:

```markdown
### Must-ask 3: What was the hardest technical challenge?
- Tested: depth of problem-solving and retrospection
- Strategy: use STAR to tell one concrete difficulty and highlight your decision
- STAR:
  - Situation: real-time sync collided often on weak networks
  - Task: keep multi-client data consistent
  - Action: adopted CRDT (see src/sync/crdt.ts)
  - Result: conflict rate dropped from 12% to 0.3%
```

## FAQ

**Q: Must I use a high-reasoning model?**
A: No, but it is recommended. A low-reasoning model still works, only with lower quality analysis and evolution.

**Q: My project is not a web app. Will it work?**
A: Yes. The scanner covers many tech-stack markers, and the model understands non-web projects (CLI tools, libraries, scripts).

**Q: Does the resume have to be a PDF?**
A: PDF, DOCX, and TXT are supported. The skill works without a resume; the prep guide just loses one JD-matching input.

**Q: Will the output fabricate content?**
A: No. The skill constrains highlights to code or architecture evidence, and interview questions to specific files in the project.

## License

Released under the MIT License. See [LICENSE](./LICENSE).
