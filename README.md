# 📈 Financial Researcher - Multi-Agent Company Research & Report System

A multi-agent AI research pipeline built with CrewAI that performs web research on a company and produces a structured financial/market analysis report in Markdown.

![CrewAI](https://img.shields.io/badge/CrewAI-000000?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

## ✨ Features

- **Two-Agent Workflow**: Researcher gathers sources; Analyst synthesizes insights
- **Web Search Tooling**: Uses SerperDevTool for fast, targeted web research
- **Report Generation**: Produces a polished Markdown report with clear headings and an executive summary
- **Config-Driven**: Agents and tasks defined in YAML for quick customization

## 🏗️ Architecture

The system uses a **CrewAI** framework with two specialized agents:

- **Researcher Agent**
  - Uses `SerperDevTool` to collect relevant sources and facts about `{company}`
  - Organizes findings into structured sections (status, performance, news, outlook)

- **Analyst Agent**
  - Reviews the research context
  - Produces a comprehensive report with analysis, trends, and a market outlook disclaimer

## 📋 Prerequisites

- Python >=3.10 <3.13
- [UV](https://docs.astral.sh/uv/) package manager
- API keys required by configured tools/models

## 🛠️ Installation

1. Install UV:
```bash
pip install uv
```

2. Install dependencies:
```bash
crewai install
```

3. Create a `.env` file in the project root (typical setup):
```env
OPENAI_API_KEY=your_key_here
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

## 🎯 Usage

Run from project root:
```bash
crewai run
```

The default company is set in `src/financial_researcher/main.py` (e.g., "Perpetua Resources Corp").

## ⚙️ Configuration

- **Agents**: `src/financial_researcher/config/agents.yaml`
- **Tasks**: `src/financial_researcher/config/tasks.yaml`
- **Company input**: Edit `src/financial_researcher/main.py`
- **Crew workflow**: `src/financial_researcher/crew.py`

## 📁 Project Structure

```text
financial_researcher/
├── src/financial_researcher/
│   ├── main.py
│   ├── crew.py
│   ├── config/
│   │   ├── agents.yaml
│   │   └── tasks.yaml
│   └── tools/
├── knowledge/
├── output/
└── pyproject.toml
```

## 📤 Output

Final report is saved to `output/report.md`.

## 🛠️ Technologies

CrewAI, Python, SerperDevTool, OpenAI GPT-4o-mini, Groq (Llama 3.3 70B)
