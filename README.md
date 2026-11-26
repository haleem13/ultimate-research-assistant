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

The same workflow can help with MRI segmentation, fastMRI reconstruction and aliasing, EMI removal, and molecular property analysis. See the [research examples](references/examples.md) for how the questions and checks change across tasks.

## Install

### Ask your agent to install it

Open your research project in your agent, copy this repository's URL from GitHub, and paste this prompt with the URL filled in:

```text
Install Ultimate Research Assistant from https://github.com/haleem13/ultimate-research-assistant
for this research project. Use the project-level skills directory for
the agent I am using. Copy SKILL.md and the entire references/ folder
into an ultimate-research-assistant directory there. If a version is
already installed, ask before replacing it. Verify the installed files
and tell me the exact path and how to invoke the skill in a new session.
```

To install it for every project, replace "for this research project" with "for my user account across all projects."

### Install manually

Download the repository from **Code > Download ZIP** on GitHub and extract it, or clone it using the URL under **Code**. Open a terminal in the directory containing `SKILL.md` and `references/`.

| Agent | Install in one research project | Install for all your projects |
| --- | --- | --- |
| Codex | `.agents/skills/` | `~/.agents/skills/` |
| Claude Code | `.claude/skills/` | `~/.claude/skills/` |

Create an `ultimate-research-assistant` folder under the selected destination and copy `SKILL.md` and the entire `references/` folder into it. Project paths are relative to your research project. [Installation path reference](https://developers.openai.com/api/reference/cli)

**Windows PowerShell**

```powershell
$destination = 'C:\path\to\research-project\.agents\skills\ultimate-research-assistant'
New-Item -ItemType Directory -Force -Path $destination | Out-Null
Copy-Item -LiteralPath './SKILL.md', './references' -Destination $destination -Recurse
```

**macOS or Linux**

```sh
destination="/path/to/research-project/.agents/skills/ultimate-research-assistant"
mkdir -p "$destination"
cp -R ./SKILL.md ./references "$destination/"
```

For Claude Code, replace `.agents` with `.claude`. For an all-projects install, use your home directory as the base instead of the research project.

## Use it

Start a new session in your research project. Invoke `$ultimate-research-assistant` in Codex or `/ultimate-research-assistant` in Claude Code. Include the project files you want the agent to inspect and the choices you have already made.

```text
Review the project files and relevant primary papers for this experiment.
Tell me which scientific choices are settled and which need my input.
Recommend options with tradeoffs and show the inputs, outputs, and checks
for every stage. Wait for my answers before implementing anything.
```

Once the open choices are resolved, authorize the agreed work. The agent should report what it verified and suggest a creative follow-up with a small test that could change your interpretation.

If the skill does not appear, check that `SKILL.md` is directly inside the installed `ultimate-research-assistant` folder and start a new session. Literature lookup and experiment execution depend on the tools and permissions available in your agent.

## Skill files

- [SKILL.md](SKILL.md) contains the workflow and decision rules.
- [Research examples](references/examples.md) shows how to apply them across research tasks.
