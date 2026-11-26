# Ultimate Research Assistant

**Make every research step explicit before the AI writes code or runs an experiment.**

Ultimate Research Assistant is an [Agent Skill](https://agentskills.io/) for researcher-led work. It helps an AI agent learn your project, investigate relevant literature, surface decisions you still need to make, and verify the work you authorize.

## Try it with a real request

> Use the Ultimate Research Assistant skill. I want to segment MRI scans in this project. Review the available data and relevant papers, recommend models that fit our labels and compute, and ask me to resolve any open decisions before implementation.

A useful first response might be:

> I found two candidate datasets in the project. Which should we use, and are we training on your annotations or running pretrained inference? I'll compare model options against that choice and show the proposed workflow, including preprocessing, evaluation, and checks, before writing code.

## How it works

| Stage | What the agent does |
| --- | --- |
| **Learn** | Inspect the project and read the relevant parts of primary papers and official dataset documentation. Reuse verified context and keep the search focused. |
| **Clarify** | Ask about open scientific decisions, including the data, method, inputs, parameters, and evaluation. Explain the tradeoffs and recommend options when the evidence supports them. |
| **Plan** | Show each step's inputs, operations, settings, expected outputs, and verification checks. Wait for answers whenever the procedure is unclear. |
| **Implement and verify** | Follow the agreed procedure and inspect the actual inputs and saved outputs at each stage. Check independently which samples were used for fitting, prediction, and evaluation. |
| **Report and advise** | Explain what ran, what was verified, and what remains uncertain. Offer creative follow-up ideas with the smallest informative test and explain how its outcomes could change your interpretation. You decide which ideas to pursue. |

The same workflow can help with MRI segmentation, fastMRI reconstruction and aliasing, EMI removal, and molecular property analysis. See the [research examples](ultimate-research-assistant/references/examples.md) for how the questions and checks change across tasks.

## Get started

1. Download or clone this repository.
2. Copy the [ultimate-research-assistant](ultimate-research-assistant/) folder into a skills directory supported by your agent. For project-level use with Codex, place it at `.agents/skills/ultimate-research-assistant/` in your research project.
3. Invoke `$ultimate-research-assistant` in Codex, or ask a compatible agent to use the skill for your task. Point it to the project files and share any scientific decisions you've already made.

The skill is Markdown. Literature lookup and experiment execution use the tools and permissions available in your agent.

## Repository contents

- [Ultimate Research Assistant](ultimate-research-assistant/SKILL.md) is the general-purpose skill.
- [Verify Intent and Data Flow](verify-intent-and-data-flow/SKILL.md) is the original MRI-specific skill, with detailed checks for EMI subtraction and reconstruction.
