# Claude Skills Collection

אוסף הסקילים של Claude Code (סקילים אישיים + Anthropic + פלאגינים), כפי שנאספו מהמחשב. כל סקיל הוא תיקייה עם `SKILL.md`.

## שימוש

העתק תיקיית סקיל אל `~/.claude/skills/<name>/` (או פלאגין שלם לפי הצורך).

## skills/

| Skill | Description |
|---|---|
| [algorithmic-art](skills/algorithmic-art) | Creating algorithmic art using p5.js with seeded randomness and interactive parameter exploration. Use this when users request creating art using code, gener... |
| [brainstorming](skills/brainstorming) | You MUST use this before any creative work - creating features, building components, adding functionality, or modifying behavior. Explores user intent, requi... |
| [brand-guidelines](skills/brand-guidelines) | Applies Anthropic's official brand colors and typography to any sort of artifact that may benefit from having Anthropic's look-and-feel. Use it when brand co... |
| [canvas-design](skills/canvas-design) | Create beautiful visual art in .png and .pdf documents using design philosophy. You should use this skill when the user asks to create a poster, piece of art... |
| [design-md](skills/design-md) | Use when the user wants a UI, page or app styled like a known brand (\"make it look like Stripe / Linear / Apple / Notion…\"), or asks for a DESIGN.md / desi... |
| [doc-coauthoring](skills/doc-coauthoring) | Guide users through a structured workflow for co-authoring documentation. Use when user wants to write documentation, proposals, technical specs, decision do... |
| [docs](skills/docs) | docs (editable docs people share and comment on; the default for any document, named as a doc or not: a document, report, proposal, resume, cover letter, let... |
| [docx](skills/docx) | Use this skill whenever the user wants to create, read, edit, or manipulate Word documents (.docx) or Word templates (.dotx). Triggers include: any mention o... |
| [frontend-design](skills/frontend-design) | Guidance for distinctive, intentional visual design when building new UI or reshaping an existing one. Helps with aesthetic direction, typography, and making... |
| [fullstack-app](skills/fullstack-app) | Build and deploy a complete fullstack web application through interactive conversation. Use when a user wants to create a web app, build a website, make an a... |
| [google-workspace](skills/google-workspace) | Read this before the first Google Drive, Docs, Sheets or Slides connector call whenever the task creates or changes a Google file. Use this skill whenever th... |
| [import-memory](skills/import-memory) | Import a memory export from another AI assistant into Claude's memory — conversationally, additively, and with the content treated as data. |
| [internal-comms](skills/internal-comms) | A set of resources to help me write all kinds of internal communications, using the formats that my company likes to use. Claude should use this skill whenev... |
| [learn](skills/learn) | / |
| [match-music-to-audio](skills/match-music-to-audio) | Fit a music track to a voice/audio file: loop or trim it to length, balance loudness, auto-duck under speech, fades, and export the mix (ffmpeg). |
| [mcp-builder](skills/mcp-builder) | Guide for creating high-quality MCP (Model Context Protocol) servers that enable LLMs to interact with external services through well-designed tools. Use whe... |
| [mengto-3d](skills/mengto-3d) | Use for 3D scene rendering quality in Three.js: sky, sun rays, falling leaves, seasons, high-poly models, PBR textures, Retina/HiDPI rendering, virtual tours... |
| [mengto-game-dev](skills/mengto-game-dev) | Use when building, tuning, testing or shipping a Three.js / web game: mobile controls, camera, combat, enemies, AI, VFX, audio, levels, inventory, performanc... |
| [mengto-ui](skills/mengto-ui) | Use as a quality gate whenever creating, reviewing or prompting for UI: prevent and audit generic AI design slop, and write design-first UI prompts. Index of... |
| [mengto-web-design](skills/mengto-web-design) | Use for any landing page, website, hero, section, background, WebGL/Three.js visual, GSAP/scroll animation, CSS effect, design system or UI polish task. Inde... |
| [mobile-app-design-pro](skills/mobile-app-design-pro) | Professional mobile app design rules (single-file PWA/HTML, native Android, iOS): design tokens, Hebrew RTL, typography, touch, navigation, states, and profe... |
| [morning](skills/morning) | Render the user's morning brief as a styled HTML artifact, or set it up as a recurring weekday task. Use only when the user explicitly asks to run, see, or s... |
| [openstoryline](skills/openstoryline) | Install, run and drive FireRed-OpenStoryline — a self-hosted AI video-editing agent (clip splitting, media search, script, TTS voiceover, subtitles, render) ... |
| [pdf](skills/pdf) | Use this skill whenever the user wants to do anything with PDF files. This includes reading or extracting text/tables from PDFs, combining or merging multipl... |
| [pptx](skills/pptx) | Use this skill any time a .pptx or .potx file is involved in any way — as input, output, or both. This includes: creating slide decks, pitch decks, or presen... |
| [remotion-motion-graphics](skills/remotion-motion-graphics) | Create and edit professional motion graphics videos with Remotion (React video): intros, logo stings, Reels/Shorts, promo/launch videos, text animations, cap... |
| [skill-creator](skills/skill-creator) | Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to create a skill from scratch, edit, or optimize a... |
| [skill-installer](skills/skill-installer) | התקנת סקילים ופלאגינים חדשים מהאינטרנט או מהמחשב. השתמש כשמשתמש רוצה להתקין סקיל או פלאגין, מדביק קישור, נותן נתיב לקובץ מקומי, אומר 'תתקין סקיל', 'install s... |
| [slack-gif-creator](skills/slack-gif-creator) | Knowledge and utilities for creating animated GIFs optimized for Slack. Provides constraints, validation tools, and animation concepts. Use when users reques... |
| [systematic-debugging](skills/systematic-debugging) | Use when encountering any bug, test failure, or unexpected behavior, before proposing fixes |
| [test-driven-development](skills/test-driven-development) | Use when implementing any feature or bugfix, before writing implementation code |
| [theme-factory](skills/theme-factory) | Toolkit for styling artifacts with a theme. These artifacts can be slides, docs, reportings, HTML landing pages, etc. There are 10 pre-set themes with colors... |
| [verification-before-completion](skills/verification-before-completion) | Use when about to claim work is complete, fixed, or passing, before committing or creating PRs - requires running verification commands and confirming output... |
| [video-use](skills/video-use) | Edit real video footage by conversation — transcribe, cut talking heads/montages/tutorials, color grade, overlay animations, burn subtitles — and make Manim ... |
| [webapp-testing](skills/webapp-testing) | Toolkit for interacting with and testing local web applications using Playwright. Supports verifying frontend functionality, debugging UI behavior, capturing... |
| [web-artifacts-builder](skills/web-artifacts-builder) | Suite of tools for creating elaborate, multi-component claude.ai HTML artifacts using modern frontend web technologies (React, Tailwind CSS, shadcn/ui). Use ... |
| [writing-plans](skills/writing-plans) | Use when you have a spec or requirements for a multi-step task, before touching code |
| [xlsx](skills/xlsx) | Use this skill any time a spreadsheet file is the primary input or output. This means any task where the user wants to: open, read, edit, or fix an existing ... |

## plugins/bio-research

| Skill | Description |
|---|---|
| [instrument-data-to-allotrope](plugins/bio-research/skills/instrument-data-to-allotrope) | Convert laboratory instrument output files (PDF, CSV, Excel, TXT) to Allotrope Simple Model (ASM) JSON format or flattened 2D CSV. Use this skill when scient... |
| [nextflow-development](plugins/bio-research/skills/nextflow-development) | Run nf-core bioinformatics pipelines (rnaseq, sarek, atacseq) on sequencing data. Use when analyzing RNA-seq, WGS/WES, or ATAC-seq data—either local FASTQs o... |
| [scientific-problem-selection](plugins/bio-research/skills/scientific-problem-selection) | This skill should be used when scientists need help with research problem selection, project ideation, troubleshooting stuck projects, or strategic scientifi... |
| [scvi-tools](plugins/bio-research/skills/scvi-tools) | Deep learning for single-cell analysis using scvi-tools. This skill should be used when users need (1) data integration and batch correction with scVI/scANVI... |
| [single-cell-rna-qc](plugins/bio-research/skills/single-cell-rna-qc) | Performs quality control on single-cell RNA-seq data (.h5ad or .h5 files) using scverse best practices with MAD-based filtering and comprehensive visualizati... |
| [start](plugins/bio-research/skills/start) | Set up your bio-research environment and explore available tools. Use when first getting oriented with the plugin, checking which literature, drug-discovery,... |

## plugins/cowork-plugin-management

| Skill | Description |
|---|---|
| [cowork-plugin-customizer](plugins/cowork-plugin-management/skills/cowork-plugin-customizer) | Customize a Claude Code plugin for a specific organization's tools and workflows. Use when: customize plugin, set up plugin, configure plugin, tailor plugin,... |
| [create-cowork-plugin](plugins/cowork-plugin-management/skills/create-cowork-plugin) | Guide users through creating a new plugin from scratch in a cowork session. Use when users want to create a plugin, build a plugin, make a new plugin, develo... |

## plugins/customer-support

| Skill | Description |
|---|---|
| [customer-escalation](plugins/customer-support/skills/customer-escalation) | Package an escalation for engineering, product, or leadership with full context. Use when a bug needs engineering attention beyond normal support, multiple c... |
| [customer-research](plugins/customer-support/skills/customer-research) | Multi-source research on a customer question or topic with source attribution. Use when a customer asks something you need to look up, investigating whether ... |
| [draft-response](plugins/customer-support/skills/draft-response) | Draft a professional customer-facing response tailored to the situation and relationship. Use when answering a product question, responding to an escalation ... |
| [kb-article](plugins/customer-support/skills/kb-article) | Draft a knowledge base article from a resolved issue or common question. Use when a ticket resolution is worth documenting for self-service, the same questio... |
| [ticket-triage](plugins/customer-support/skills/ticket-triage) | Triage and prioritize a support ticket or customer issue. Use when a new ticket comes in and needs categorization, assigning P1-P4 priority, deciding which t... |

## plugins/data

| Skill | Description |
|---|---|
| [analyze](plugins/data/skills/analyze) | Answer data questions -- from quick lookups to full analyses. Use when looking up a single metric, investigating what's driving a trend or drop, comparing se... |
| [build-dashboard](plugins/data/skills/build-dashboard) | Build an interactive HTML dashboard with charts, filters, and tables. Use when creating an executive overview with KPI cards, turning query results into a sh... |
| [create-viz](plugins/data/skills/create-viz) | Create publication-quality visualizations with Python. Use when turning query results or a DataFrame into a chart, selecting the right chart type for a trend... |
| [data-context-extractor](plugins/data/skills/data-context-extractor) | Generate or improve a company-specific data analysis skill by extracting tribal knowledge from analysts.\nBOOTSTRAP MODE - Triggers: \"Create a data context ... |
| [data-visualization](plugins/data/skills/data-visualization) | Create effective data visualizations with Python (matplotlib, seaborn, plotly). Use when building charts, choosing the right chart type for a dataset, creati... |
| [explore-data](plugins/data/skills/explore-data) | Profile and explore a dataset to understand its shape, quality, and patterns. Use when encountering a new table or file, checking null rates and column distr... |
| [sql-queries](plugins/data/skills/sql-queries) | Write correct, performant SQL across all major data warehouse dialects (Snowflake, BigQuery, Databricks, PostgreSQL, etc.). Use when writing queries, optimiz... |
| [statistical-analysis](plugins/data/skills/statistical-analysis) | Apply statistical methods including descriptive stats, trend analysis, outlier detection, and hypothesis testing. Use when analyzing distributions, testing f... |
| [validate-data](plugins/data/skills/validate-data) | QA an analysis before sharing -- methodology, accuracy, and bias checks. Use when reviewing an analysis before a stakeholder presentation, spot-checking calc... |
| [write-query](plugins/data/skills/write-query) | Write optimized SQL for your dialect with best practices. Use when translating a natural-language data need into SQL, building a multi-CTE query with joins a... |

## plugins/design

| Skill | Description |
|---|---|
| [accessibility-review](plugins/design/skills/accessibility-review) | Run a WCAG 2.1 AA accessibility audit on a design or page. Trigger with "audit accessibility", "check a11y", "is this accessible?", or when reviewing a desig... |
| [design-critique](plugins/design/skills/design-critique) | Get structured design feedback on usability, hierarchy, and consistency. Trigger with "review this design", "critique this mockup", "what do you think of thi... |
| [design-handoff](plugins/design/skills/design-handoff) | Generate developer handoff specs from a design. Use when a design is ready for engineering and needs a spec sheet covering layout, design tokens, component p... |
| [design-system](plugins/design/skills/design-system) | Audit, document, or extend your design system. Use when checking for naming inconsistencies or hardcoded values across components, writing documentation for ... |
| [research-synthesis](plugins/design/skills/research-synthesis) | Synthesize user research into themes, insights, and recommendations. Use when you have interview transcripts, survey results, usability test notes, support t... |
| [user-research](plugins/design/skills/user-research) | Plan, conduct, and synthesize user research. Trigger with "user research plan", "interview guide", "usability test", "survey design", "research questions", o... |
| [ux-copy](plugins/design/skills/ux-copy) | Write or review UX copy — microcopy, error messages, empty states, CTAs. Trigger with "write copy for", "what should this button say?", "review this error me... |

## plugins/engineering

| Skill | Description |
|---|---|
| [architecture](plugins/engineering/skills/architecture) | Create or evaluate an architecture decision record (ADR). Use when choosing between technologies (e.g., Kafka vs SQS), documenting a design decision with tra... |
| [code-review](plugins/engineering/skills/code-review) | Review code changes for security, performance, and correctness. Trigger with a PR URL or diff, "review this before I merge", "is this code safe?", or when ch... |
| [debug](plugins/engineering/skills/debug) | Structured debugging session — reproduce, isolate, diagnose, and fix. Trigger with an error message or stack trace, "this works in staging but not prod", "so... |
| [deploy-checklist](plugins/engineering/skills/deploy-checklist) | Pre-deployment verification checklist. Use when about to ship a release, deploying a change with database migrations or feature flags, verifying CI status an... |
| [documentation](plugins/engineering/skills/documentation) | Write and maintain technical documentation. Trigger with "write docs for", "document this", "create a README", "write a runbook", "onboarding guide", or when... |
| [incident-response](plugins/engineering/skills/incident-response) | Run an incident response workflow — triage, communicate, and write postmortem. Trigger with "we have an incident", "production is down", an alert that needs ... |
| [standup](plugins/engineering/skills/standup) | Generate a standup update from recent activity. Use when preparing for daily standup, summarizing yesterday's commits and PRs and ticket moves, formatting wo... |
| [system-design](plugins/engineering/skills/system-design) | Design systems, services, and architectures. Trigger with "design a system for", "how should we architect", "system design for", "what's the right architectu... |
| [tech-debt](plugins/engineering/skills/tech-debt) | Identify, categorize, and prioritize technical debt. Trigger with "tech debt", "technical debt audit", "what should we refactor", "code health", or when the ... |
| [testing-strategy](plugins/engineering/skills/testing-strategy) | Design test strategies and test plans. Trigger with "how should we test", "test strategy for", "write tests for", "test plan", "what tests do we need", or wh... |

## plugins/enterprise-search

| Skill | Description |
|---|---|
| [digest](plugins/enterprise-search/skills/digest) | Generate a daily or weekly digest of activity across all connected sources. Use when catching up after time away, starting the day and wanting a summary of m... |
| [knowledge-synthesis](plugins/enterprise-search/skills/knowledge-synthesis) | Combines search results from multiple sources into coherent, deduplicated answers with source attribution. Handles confidence scoring based on freshness and ... |
| [search](plugins/enterprise-search/skills/search) | Search across all connected sources in one query. Trigger with "find that doc about...", "what did we decide on...", "where was the conversation about...", o... |
| [search-strategy](plugins/enterprise-search/skills/search-strategy) | Query decomposition and multi-source search orchestration. Breaks natural language questions into targeted searches per source, translates queries into sourc... |
| [source-management](plugins/enterprise-search/skills/source-management) | Manages connected MCP sources for enterprise search. Detects available sources, guides users to connect new ones, handles source priority ordering, and manag... |

## plugins/finance

| Skill | Description |
|---|---|
| [audit-support](plugins/finance/skills/audit-support) | Support SOX 404 compliance with control testing methodology, sample selection, and documentation standards. Use when generating testing workpapers, selecting... |
| [close-management](plugins/finance/skills/close-management) | Manage the month-end close process with task sequencing, dependencies, and status tracking. Use when planning the close calendar, tracking close progress, id... |
| [financial-statements](plugins/finance/skills/financial-statements) | Generate financial statements (income statement, balance sheet, cash flow) with period-over-period comparison and variance analysis. Use when preparing a mon... |
| [journal-entry](plugins/finance/skills/journal-entry) | Prepare journal entries with proper debits, credits, and supporting detail. Use when booking month-end accruals (AP, payroll, prepaid), recording depreciatio... |
| [journal-entry-prep](plugins/finance/skills/journal-entry-prep) | Prepare journal entries with proper debits, credits, and supporting documentation for month-end close. Use when booking accruals, prepaid amortization, fixed... |
| [reconciliation](plugins/finance/skills/reconciliation) | Reconcile accounts by comparing GL balances to subledgers, bank statements, or third-party data. Use when performing bank reconciliations, GL-to-subledger re... |
| [sox-testing](plugins/finance/skills/sox-testing) | Generate SOX sample selections, testing workpapers, and control assessments. Use when planning quarterly or annual SOX 404 testing, pulling a sample for a co... |
| [variance-analysis](plugins/finance/skills/variance-analysis) | Decompose financial variances into drivers with narrative explanations and waterfall analysis. Use when analyzing budget vs. actual, period-over-period chang... |

## plugins/human-resources

| Skill | Description |
|---|---|
| [comp-analysis](plugins/human-resources/skills/comp-analysis) | Analyze compensation — benchmarking, band placement, and equity modeling. Trigger with "what should we pay a [role]", "is this offer competitive", "model thi... |
| [draft-offer](plugins/human-resources/skills/draft-offer) | Draft an offer letter with comp details and terms. Use when a candidate is ready for an offer, assembling a total comp package (base, equity, signing bonus),... |
| [interview-prep](plugins/human-resources/skills/interview-prep) | Create structured interview plans with competency-based questions and scorecards. Trigger with "interview plan for", "interview questions for", "how should w... |
| [onboarding](plugins/human-resources/skills/onboarding) | Generate an onboarding checklist and first-week plan for a new hire. Use when someone has a start date coming up, building the pre-start task list (accounts,... |
| [org-planning](plugins/human-resources/skills/org-planning) | Headcount planning, org design, and team structure optimization. Trigger with "org planning", "headcount plan", "team structure", "reorg", "who should we hir... |
| [people-report](plugins/human-resources/skills/people-report) | Generate headcount, attrition, diversity, or org health reports. Use when pulling a headcount snapshot for leadership, analyzing turnover trends by team, pre... |
| [performance-review](plugins/human-resources/skills/performance-review) | Structure a performance review with self-assessment, manager template, and calibration prep. Use when review season kicks off and you need a self-assessment ... |
| [policy-lookup](plugins/human-resources/skills/policy-lookup) | Find and explain company policies in plain language. Trigger with "what's our PTO policy", "can I work remotely from another country", "how do expenses work"... |
| [recruiting-pipeline](plugins/human-resources/skills/recruiting-pipeline) | Track and manage recruiting pipeline stages. Trigger with "recruiting update", "candidate pipeline", "how many candidates", "hiring status", or when the user... |

## plugins/legal

| Skill | Description |
|---|---|
| [brief](plugins/legal/skills/brief) | Generate contextual briefings for legal work — daily summary, topic research, or incident response. Use when starting your day and need a scan of legal-relev... |
| [compliance-check](plugins/legal/skills/compliance-check) | Run a compliance check on a proposed action, product feature, or business initiative, surfacing applicable regulations, required approvals, and risk areas. U... |
| [legal-response](plugins/legal/skills/legal-response) | Generate a response to a common legal inquiry using configured templates, with built-in escalation checks for situations that shouldn't use a templated reply... |
| [legal-risk-assessment](plugins/legal/skills/legal-risk-assessment) | Assess and classify legal risks using a severity-by-likelihood framework with escalation criteria. Use when evaluating contract risk, assessing deal exposure... |
| [meeting-briefing](plugins/legal/skills/meeting-briefing) | Prepare structured briefings for meetings with legal relevance and track resulting action items. Use when preparing for contract negotiations, board meetings... |
| [review-contract](plugins/legal/skills/review-contract) | Review a contract against your organization's negotiation playbook — flag deviations, generate redlines, provide business impact analysis. Use when reviewing... |
| [signature-request](plugins/legal/skills/signature-request) | Prepare and route a document for e-signature — run a pre-signature checklist, configure signing order, and send for execution. Use when a contract is finaliz... |
| [triage-nda](plugins/legal/skills/triage-nda) | Rapidly triage an incoming NDA and classify it as GREEN (standard approval), YELLOW (counsel review), or RED (full legal review). Use when a new NDA arrives ... |
| [vendor-check](plugins/legal/skills/vendor-check) | Check the status of existing agreements with a vendor across all connected systems — CLM, CRM, email, and document storage — with gap analysis and upcoming d... |

## plugins/marketing

| Skill | Description |
|---|---|
| [brand-review](plugins/marketing/skills/brand-review) | Review content against your brand voice, style guide, and messaging pillars, flagging deviations by severity with specific before/after fixes. Use when check... |
| [campaign-plan](plugins/marketing/skills/campaign-plan) | Generate a full campaign brief with objectives, audience, messaging, channel strategy, content calendar, and success metrics. Use when planning a product lau... |
| [competitive-brief](plugins/marketing/skills/competitive-brief) | Research competitors and generate a positioning and messaging comparison with content gaps, opportunities, and threats. Use when building sales battlecards, ... |
| [content-creation](plugins/marketing/skills/content-creation) | Draft marketing content across channels — blog posts, social media, email newsletters, landing pages, press releases, and case studies. Use when writing any ... |
| [draft-content](plugins/marketing/skills/draft-content) | Draft blog posts, social media, email newsletters, landing pages, press releases, and case studies with channel-specific formatting and SEO recommendations. ... |
| [email-sequence](plugins/marketing/skills/email-sequence) | Design and draft multi-email sequences with full copy, timing, branching logic, exit conditions, and performance benchmarks. Use when building onboarding, le... |
| [performance-report](plugins/marketing/skills/performance-report) | Build a marketing performance report with key metrics, trend analysis, wins and misses, and prioritized optimization recommendations. Use when wrapping a cam... |
| [seo-audit](plugins/marketing/skills/seo-audit) | Run a comprehensive SEO audit — keyword research, on-page analysis, content gaps, technical checks, and competitor comparison. Use when assessing a site's SE... |

## plugins/operations

| Skill | Description |
|---|---|
| [capacity-plan](plugins/operations/skills/capacity-plan) | Plan resource capacity — workload analysis and utilization forecasting. Use when heading into quarterly planning, the team feels overallocated and you need t... |
| [change-request](plugins/operations/skills/change-request) | Create a change management request with impact analysis and rollback plan. Use when proposing a system or process change that needs approval, preparing a cha... |
| [compliance-tracking](plugins/operations/skills/compliance-tracking) | Track compliance requirements and audit readiness. Trigger with "compliance", "audit prep", "SOC 2", "ISO 27001", "GDPR", "regulatory requirement", or when t... |
| [process-doc](plugins/operations/skills/process-doc) | Document a business process — flowcharts, RACI, and SOPs. Use when formalizing a process that lives in someone's head, building a RACI to clarify who owns wh... |
| [process-optimization](plugins/operations/skills/process-optimization) | Analyze and improve business processes. Trigger with "this process is slow", "how can we improve", "streamline this workflow", "too many steps", "bottleneck"... |
| [risk-assessment](plugins/operations/skills/risk-assessment) | Identify, assess, and mitigate operational risks. Trigger with "what are the risks", "risk assessment", "risk register", "what could go wrong", or when the u... |
| [runbook](plugins/operations/skills/runbook) | Create or update an operational runbook for a recurring task or procedure. Use when documenting a task that on-call or ops needs to run repeatably, turning t... |
| [status-report](plugins/operations/skills/status-report) | Generate a status report with KPIs, risks, and action items. Use when writing a weekly or monthly update for leadership, summarizing project health with gree... |
| [vendor-review](plugins/operations/skills/vendor-review) | Evaluate a vendor — cost analysis, risk assessment, and recommendation. Use when reviewing a new vendor proposal, deciding whether to renew or replace a cont... |

## plugins/pdf-viewer

| Skill | Description |
|---|---|
| [view-pdf](plugins/pdf-viewer/skills/view-pdf) | Interactive PDF viewer. Use when the user wants to open, show, or view a PDF and collaborate on it visually — annotate, highlight, stamp, fill form fields, p... |

## plugins/productivity

| Skill | Description |
|---|---|
| [memory-management](plugins/productivity/skills/memory-management) | Two-tier memory system that makes Claude a true workplace collaborator. Decodes shorthand, acronyms, nicknames, and internal language so Claude understands r... |
| [start](plugins/productivity/skills/start) | Initialize the productivity system and open the dashboard. Use when setting up the plugin for the first time, bootstrapping working memory from your existing... |
| [task-management](plugins/productivity/skills/task-management) | Simple task management using a shared TASKS.md file. Reference this when the user asks about their tasks, wants to add/complete tasks, or needs help tracking... |
| [update](plugins/productivity/skills/update) | Sync tasks and refresh memory from your current activity. Use when pulling new assignments from your project tracker into TASKS.md, triaging stale or overdue... |

## plugins/product-management

| Skill | Description |
|---|---|
| [competitive-brief](plugins/product-management/skills/competitive-brief) | Create a competitive analysis brief for one or more competitors or a feature area. Use when informing product strategy or feature prioritization, building sa... |
| [metrics-review](plugins/product-management/skills/metrics-review) | Review and analyze product metrics with trend analysis and actionable insights. Use when running a weekly, monthly, or quarterly metrics review, investigatin... |
| [product-brainstorming](plugins/product-management/skills/product-brainstorming) | Brainstorm product ideas, explore problem spaces, and challenge assumptions as a thinking partner. Use when exploring a new opportunity, generating solutions... |
| [roadmap-update](plugins/product-management/skills/roadmap-update) | Update, create, or reprioritize your product roadmap. Use when adding a new initiative and deciding what moves to make room, shifting priorities after new in... |
| [sprint-planning](plugins/product-management/skills/sprint-planning) | Plan a sprint — scope work, estimate capacity, set goals, and draft a sprint plan. Use when kicking off a new sprint, sizing a backlog against team availabil... |
| [stakeholder-update](plugins/product-management/skills/stakeholder-update) | Generate a stakeholder update tailored to audience and cadence. Use when writing a weekly or monthly status for leadership, announcing a launch, escalating a... |
| [synthesize-research](plugins/product-management/skills/synthesize-research) | Synthesize user research from interviews, surveys, and feedback into structured insights. Use when you have a pile of interview notes, survey responses, or s... |
| [write-spec](plugins/product-management/skills/write-spec) | Write a feature spec or PRD from a problem statement or feature idea. Use when turning a vague idea or user request into a structured document, scoping a fea... |

## plugins/sales

| Skill | Description |
|---|---|
| [account-context](plugins/sales/skills/account-context) | 360-degree view of an account - CRM data, recent email threads, docs, transcripts, and internal chat chatter, synthesized into one brief. Use when the user a... |
| [account-plan](plugins/sales/skills/account-plan) | Build or refresh a strategic account plan - current state, goals, stakeholder coverage, opportunity map, risks, and the action plan - written to a doc and ke... |
| [account-research](plugins/sales/skills/account-research) | Research a target company and optionally a specific contact - company overview, recent news, likely priorities, and fit against your ICP. Cross-references ex... |
| [account-tiering](plugins/sales/skills/account-tiering) | Score and tier a list of accounts (or your full book) against ICP fit and engagement signals to prioritize where to spend time. Use when the user asks to "ti... |
| [call-prep](plugins/sales/skills/call-prep) | Pre-call brief for an upcoming meeting - attendees, account history, prior call context from transcripts, open opportunity status, and suggested discovery qu... |
| [call-summary](plugins/sales/skills/call-summary) | Turn a call transcript or call notes into a customer follow-up email draft, an internal chat summary, and proposed CRM updates. Use when the user says "call ... |
| [close-plan](plugins/sales/skills/close-plan) | Build the business case and mutual action plan for a deal - the why-buy/why-now story, the ROI framing, and the dated step-by-step path to signature shared w... |
| [competitive-intelligence](plugins/sales/skills/competitive-intelligence) | Competitive analysis two ways - the in-deal play against a named competitor, and win/loss patterns, competitor mentions, and battlecards across the book. Use... |
| [create-an-asset](plugins/sales/skills/create-an-asset) | Build a customer deck, one-pager or leave-behind from your account data, call notes and approved materials, with no made-up numbers. Use when the user asks f... |
| [crm-hygiene-check](plugins/sales/skills/crm-hygiene-check) | Read-only audit of your CRM opportunities for missing fields, stale dates, and stage mismatches - outputs a fix checklist to apply by hand or through update-... |
| [customer-health](plugins/sales/skills/customer-health) | Health check on a customer account and QBR-ready prep - relationship strength, engagement trend, risk signals, value delivered, and the agenda that makes the... |
| [customer-voice](plugins/sales/skills/customer-voice) | Surface what customers are actually saying - direct attributed quotes on a topic across call transcripts and email, across your accounts. Use when the user a... |
| [daily-briefing](plugins/sales/skills/daily-briefing) | Morning rundown - today's meetings with account context, opps closing soon with stale flags, waiting customer emails, and the day's top actions. Use when the... |
| [deal-advance-gap](plugins/sales/skills/deal-advance-gap) | Forward-looking gap check on one opportunity - exactly what is missing to advance it to the next stage and to close, with who does what by when. Use when the... |
| [deal-review](plugins/sales/skills/deal-review) | Deep-dive on a single opportunity - signal-adjusted health score, risks, gaps in qualification, and recommended next actions. Use when the user asks "review ... |
| [deal-signals](plugins/sales/skills/deal-signals) | Proactive watch over your book - deals gone quiet, close dates slipping into view, champion changes, renewal windows opening, competitor mentions - surfaced ... |
| [deal-slip-scenario](plugins/sales/skills/deal-slip-scenario) | Model what happens to your number if a deal slips, shrinks, or dies - quota impact, coverage ratio change, and the substitute pipeline needed to stay on plan... |
| [draft-outreach](plugins/sales/skills/draft-outreach) | Draft a personalized outreach email or multi-touch sequence to a prospect, create it as an email draft for review, and add the contact to a sequence in your ... |
| [end-of-day](plugins/sales/skills/end-of-day) | The closing beat of the day - every call processed or explicitly skipped, the CRM brought current, commitments captured, and tomorrow's top three teed up. Us... |
| [expansion-whitespace](plugins/sales/skills/expansion-whitespace) | Find the expansion whitespace in an account or a book - what they own vs. what they could own, the evidence for each play, and the open opps to create. Use w... |
| [forecast](plugins/sales/skills/forecast) | Generate the commit / best-case / pipeline narrative for a forecast call or a 1:1 with your manager - what's closing, what's at risk, what changed since last... |
| [handle-objection](plugins/sales/skills/handle-objection) | Work through a live objection or competitive threat - what's really being said, the response that has worked before, and the proof points to use, grounded in... |
| [inbox-sweep](plugins/sales/skills/inbox-sweep) | Batch-process unread customer emails - classify, prioritize, and draft replies. Use when the user asks "sweep my inbox", "what customer emails need a reply",... |
| [lead-triage](plugins/sales/skills/lead-triage) | Score and route an inbound lead, or rank a backlog of leads, against your ICP and qualification framework, then recommend a priority and next action. Use whe... |
| [log-activity](plugins/sales/skills/log-activity) | Log a call, meeting, or email exchange to the CRM after the fact as a completed activity on the right account, opportunity, and contact - drafted from your d... |
| [pipeline-review](plugins/sales/skills/pipeline-review) | Stage-by-stage pipeline health check - coverage, aging, conversion, and at-risk deals - from CRM opportunity data. Use when the user asks "review my pipeline... |
| [renewal-radar](plugins/sales/skills/renewal-radar) | Upcoming renewals with timing, risk, and uplift potential - and the renewal opportunity records to keep them honest. Use when the user asks "what renewals ar... |
| [rep-context](plugins/sales/skills/rep-context) | Leader's prep on a single rep before a 1:1 - their pipeline, recent activity, what they've been working on per chat and calendar, and where they might need h... |
| [route-lead](plugins/sales/skills/route-lead) | Decide who owns an unrouted lead or opportunity and manage the handoff - deterministic routing by the org's own rules, a routing card the human router accept... |
| [schedule-meeting](plugins/sales/skills/schedule-meeting) | Find a time, draft the invite, and book the meeting on Google Calendar or Outlook - then log it to the CRM as an event on the right account and opportunity. ... |
| [setup](plugins/sales/skills/setup) | First-run setup - checks which tools are connected, shows what's connected and what each one unlocks, learns how you write from your sent email, and renders ... |
| [stakeholder-map](plugins/sales/skills/stakeholder-map) | Map the people in a deal or account - roles, influence, sentiment, who's missing, and your best access path to the people you haven't reached. Use when the u... |
| [team-pipeline](plugins/sales/skills/team-pipeline) | Leader view - roll up a team's pipeline by rep and stage, flag at-risk deals, and surface coaching moments. Use when the user asks "show my team's pipeline",... |
| [update-opportunity](plugins/sales/skills/update-opportunity) | Guided updates to an opportunity - push the stage, move the close date, set next steps, fix amount or forecast category. Shows the before/after, writes what ... |
| [weekly-wrap](plugins/sales/skills/weekly-wrap) | End-of-week summary for a rep or leader - what closed, what moved, what slipped, and what's on deck Monday. Optionally drafts a chat post to the team channel... |
| [win-loss-review](plugins/sales/skills/win-loss-review) | Analyze recently closed opportunities to find patterns in what wins and what loses - stage of loss, common objections from transcripts, deal characteristics.... |

## plugins/small-business

| Skill | Description |
|---|---|
| [ad-manager](plugins/small-business/skills/ad-manager) | The ads consultant that becomes an ads agent. Reads paid-ad performance natively through the TikTok Ads connector, or via a build-connector Zapier connection... |
| [ap-processor](plugins/small-business/skills/ap-processor) | Works the bill pile end to end: reads bills and vendor statements out of the AP inbox or from uploaded PDFs and phone photos, pulls out vendor, amount, due d... |
| [brand-style](plugins/small-business/skills/brand-style) | Sets and updates the owner's brand look and output preferences, which every page and document the plugin produces then follows automatically. Captures the br... |
| [build-agent](plugins/small-business/skills/build-agent) | Turns a task the owner keeps doing by hand into a named, reusable skill they can trigger by name or put on a schedule. Watches them do it once or listens to ... |
| [build-connector](plugins/small-business/skills/build-connector) | Gets Claude talking to a tool nobody built an official connector for. Works out what the system is, checks the Claude connector directory for an existing con... |
| [business-pulse](plugins/small-business/skills/business-pulse) | Produces a one-page cross-functional business snapshot for SMB owners — cash position (the ledger: MYOB, NetSuite, QuickBooks, Xero, or Zoho Books), sales tr... |
| [call-list](plugins/small-business/skills/call-list) | Builds today's call list. Runs lead-triage to rank the top-5 leads most worth calling, supplies talking points from email history, blocks time on the calenda... |
| [canva-creator](plugins/small-business/skills/canva-creator) | Takes an approved content brief and executes a campaign end-to-end: builds the posting calendar, generates Canva designs for social posts, drafts caption and... |
| [cash-flow-snapshot](plugins/small-business/skills/cash-flow-snapshot) | Reads AR/AP, historical cash timing, and known fixed costs from the ledger (MYOB, NetSuite, QuickBooks, Xero, or Zoho Books) or from PayPal, Square, or Strip... |
| [close-month](plugins/small-business/skills/close-month) | Closes the books and turns them into a decision as a three-link chain — month-end-prep reconciles the ledger against every connected payment processor and wr... |
| [content-strategy](plugins/small-business/skills/content-strategy) | Analyzes sales data from PayPal and QuickBooks to find top performers and slow movers, layers in seasonality, and produces a prioritized 30-day content brief... |
| [contract-review](plugins/small-business/skills/contract-review) | Lightweight NDA, MSA, and vendor contract review for SMBs without legal on staff. Reads contracts from local files, mail attachments (Gmail or M365), a conne... |
| [crm-autopilot](plugins/small-business/skills/crm-autopilot) | Keeps the CRM current without the owner ever opening it. Creates and updates contacts and deals from email, calendar, and call transcripts; logs activity aut... |
| [grant-rfp-writer](plugins/small-business/skills/grant-rfp-writer) | Finds grant and solicitation opportunities the organization actually qualifies for, runs a hard go/no-go before anyone starts writing, drafts the application... |
| [grow-pipeline](plugins/small-business/skills/grow-pipeline) | Fills the funnel end to end without the owner babysitting it — reads the market and the competition for context, builds a ranked list of named prospects with... |
| [growth-pulse](plugins/small-business/skills/growth-pulse) | Answers one question for an SMB owner — is the growth engine actually working? Pulls sales trend by channel, funnel conversion, campaign return, best and wor... |
| [hiring-screener](plugins/small-business/skills/hiring-screener) | Takes a pile of applications and turns it into a ranked shortlist, scored only against the job's stated rubric, with drafted replies to every candidate, sche... |
| [inbox-manager](plugins/small-business/skills/inbox-manager) | Turns a full inbox into a short, ranked list of what actually needs the owner. Reads the mail, sorts it into needs-you, drafted-and-waiting, and handled, wri... |
| [inventory-planner](plugins/small-business/skills/inventory-planner) | Works out what to reorder and when, from what is actually selling: pulls sales history and stock on hand from Shopify, Square, NetSuite, or an uploaded CSV, ... |
| [invoice-chase](plugins/small-business/skills/invoice-chase) | Drafts overdue-invoice reminder emails from the ledger (MYOB, NetSuite, QuickBooks, Xero, or Zoho Books) plus PayPal, Stripe, and Airwallex data, matched to ... |
| [job-post-builder](plugins/small-business/skills/job-post-builder) | Builds end-to-end hiring packets — job post, structured interview guide with scoring rubric, and offer letter template — from a hiring brief. Triggers on: \"... |
| [lead-finder](plugins/small-business/skills/lead-finder) | Builds a ranked list of prospects worth contacting. Works out the owner's ideal customer profile from the customers they already have, finds look-alike compa... |
| [lead-triage](plugins/small-business/skills/lead-triage) | Scores inbound HubSpot leads by engagement signals, company fit, and urgency markers, ranks the ones worth a call today with talking points, drafts the follo... |
| [marketing-monday](plugins/small-business/skills/marketing-monday) | Delivers the weekly growth briefing as one merged read — whether the growth engine is working, what customers are saying in public and private, what competit... |
| [monday-brief](plugins/small-business/skills/monday-brief) | Runs the owner's Monday morning briefing as a two-link chain — business-pulse for the cross-connector snapshot of cash, sales, and pipeline, and report-build... |
| [month-end-prep](plugins/small-business/skills/month-end-prep) | Reconciles the accounting ledger (MYOB, NetSuite, QuickBooks, Xero, or Zoho Books) against PayPal, Shopify, Square, and Stripe settlements, flags transaction... |
| [outreach-composer](plugins/small-business/skills/outreach-composer) | Writes prospect outreach and follow-up sequences that sound like the owner wrote them, not like an AI did. Learns a voice profile from the owner's own sent m... |
| [payroll-prep](plugins/small-business/skills/payroll-prep) | Gets payroll ready to run without anyone getting shorted: pulls timesheets from Gusto, QuickBooks Payroll, or an uploaded spreadsheet, totals regular, overti... |
| [pay-the-bills](plugins/small-business/skills/pay-the-bills) | Works the bill pile from the AP inbox all the way to a staged payment run — reads and codes every bill, then checks the cash position before a dollar is comm... |
| [plan-payroll](plugins/small-business/skills/plan-payroll) | Runs the payroll-confidence chain end to end — forecasts cash across the payroll window with cash-flow-snapshot, ranks and drafts overdue-invoice reminders w... |
| [proposal-builder](plugins/small-business/skills/proposal-builder) | Turns whatever came out of a discovery conversation — a call transcript, a voice memo, jobsite photos, an RFP document, a set of drawings, or scrappy notes —... |
| [reactivate](plugins/small-business/skills/reactivate) | Wins back customers who have quietly stopped buying — finds the ones whose gap has stretched past their own normal rhythm or who are showing churn signals, r... |
| [report-builder](plugins/small-business/skills/report-builder) | Turns a plain-English description of a recurring report into a real, repeatable report — defines the metrics, pulls them from whatever data sources are conne... |
| [report-pack](plugins/small-business/skills/report-pack) | Delivers the owner's custom recurring report pack on a set cadence — runs the saved report definition from report-builder, wraps it in a business-pulse snaps... |
| [restock](plugins/small-business/skills/restock) | Turns what is actually selling into a reorder decision and gets it all the way into the books — computes sales velocity and conservative stockout dates per i... |
| [review-reputation](plugins/small-business/skills/review-reputation) | Watches what customers are saying in public and in private, then does something about it. Aggregates Google, Yelp, and Facebook reviews alongside disputes, t... |
| [seo-ai-visibility](plugins/small-business/skills/seo-ai-visibility) | Audits and fixes both halves of being found — classic search and AI answers. Search side: rankings, site structure, page speed, titles and descriptions, and ... |
| [smb-onboard](plugins/small-business/skills/smb-onboard) | Claude as the trainer. Walks an SMB owner through connecting their first two tools, runs one recipe to prove immediate value, interviews them about their bus... |
| [smb-router](plugins/small-business/skills/smb-router) | The front door to the Small Business plugin. Listens to what the owner needs right now — vague or specific — and routes them to the best skill or slash comma... |
| [social-content-engine](plugins/small-business/skills/social-content-engine) | Runs the owner's content operation as a standing thing rather than a one-off: keeps a rolling posting calendar, learns the owner's voice, generates on-brand ... |
| [speed-to-lead](plugins/small-business/skills/speed-to-lead) | Makes sure no inbound lead goes unanswered. Watches web forms, the shared inbox, and the CRM for new inquiries, qualifies each one against the owner's criter... |
| [tax-prep](plugins/small-business/skills/tax-prep) | Prepares tax materials as a two-link chain — month-end-prep confirms the books are closed and reconciled first, then tax-season-organizer calculates the quar... |
| [tax-season-organizer](plugins/small-business/skills/tax-season-organizer) | Prepares tax-season materials for the owner's accountant, not tax advice. US federal tax; a non-US business gets its closed-books packet instead. Two modes: ... |
| [ticket-deflector](plugins/small-business/skills/ticket-deflector) | Reads a forwarded customer email or ticket, pulls order and refund status from a payments connector (PayPal, Square, or Stripe) or Shopify, account history f... |

## Built-in (לא כלולים כקבצים)

סקילים מובנים באפליקציה שאין להם קבצים על הדיסק: code-review, simplify, loop, schedule, claude-api, update-config, keybindings-help, fewer-permission-prompts, workflow-authoring, run, plugin-authoring, init, security-review, dataviz, artifact-design, artifact-diagramming, artifact-capabilities.

## הערה

חלק מהתוכן שייך ל-Anthropic ולספקי פלאגינים; בדוק רישוי לפני פרסום ציבורי.
