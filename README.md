<div align="center">

#  AI-Powered QA Automation Platform

**End-to-end platform that transforms requirements into executable Playwright tests — zero manual scripting.**

![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)

</div>

---

##  What This Project Does

Most QA teams spend 60–70% of their time **writing and maintaining test scripts**. This platform eliminates that entirely.

Feed it a requirement → it generates test cases, extracts real UI selectors, writes Playwright scripts, commits them to GitHub, runs them in CI/CD, and delivers a screenshot-backed report.

**Fully automated. No manual scripting. End to end.**

---

##  Architecture

```text
User Trigger ("Generate Tests")
        │
        ▼
┌──────────────────────┐
│  AI Requirement      │  ← OpenAI (prod) / Groq + Ollama (dev)
│  Analysis            │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  AI Test Case        │  ← Structured test cases generated
│  Generation          │    from plain requirements
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  Google Sheets       │  ← Test cases stored & tracked
│  Storage             │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  Playwright Selector │  ← Live UI crawled for real locators
│  Extraction          │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  AI Script           │  ← Executable Playwright JS generated
│  Generation          │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  Locator Merge       │  ← Generated logic + real selectors
│  Engine              │    combined for reliability
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  GitHub Auto-Commit  │  ← Scripts pushed automatically
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  GitHub Actions      │  ← CI/CD triggered on every commit
│  Execution           │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│  Reports &           │  ← Screenshots + pass/fail results
│  Screenshots         │
└──────────────────────┘
```

---

##  Workflow

### Agent 1 — Test Case Generation

![Test Case Generation Agent](testcase-generation-agent.png)

Accepts a natural language requirement, processes it through an AI model (Groq/Ollama in dev, OpenAI in prod), generates structured test cases, and stores them in Google Sheets.

---

### Agent 2 — Automation Generation

![Automation Generation Workflow](automation-generation-workflow.png)

Reads stored test cases, extracts live UI selectors via Playwright, generates automation scripts, merges scripts with real locators, commits to GitHub, and triggers CI/CD execution.

---

##  Execution Evidence

### AI-Generated Playwright Script
![Generated Playwright Script](generated-playwright-script.png)
> Playwright automation code built dynamically — no human wrote this.

### GitHub Actions Run
![GitHub Actions Run](github-actions-run.png)
> Fully automated CI/CD execution triggered on every generated commit.

### Playwright Report
![Playwright Report Generation](Playwright%20Report%20generation.png)
> Automated test reporting and execution tracking.

### Reports Overview
![Reports Overview](reports-overview.png)
> Centralized execution monitoring and test result visibility.

### Execution Result
![Playwright Execution Result](playwright-execution-result%20.png)
> Automated execution evidence with screenshot capture.

---

##  End-to-End Pipeline

| # | Stage | What Happens |
|---|-------|-------------|
| 1 |  Trigger | User initiates generation |
| 2 |  Requirement Analysis | AI parses and understands requirements |
| 3 |  Test Case Generation | Structured test cases created by AI |
| 4 |  Storage | Test cases saved to Google Sheets |
| 5 |  Selector Extraction | Playwright discovers real UI locators |
| 6 |  Script Generation | AI writes executable Playwright code |
| 7 |  Locator Merge | Generated logic + real selectors combined |
| 8 |  GitHub Commit | Scripts pushed automatically |
| 9 |  CI/CD Execution | GitHub Actions runs all tests |
| 10 |  Reporting | Screenshots + results generated |

---

##  Key Features

### AI Test Case Generation
Generates structured, consistent test cases from plain requirements — no manual documentation effort.
- Faster QA cycles
- Consistent coverage across requirements
- Works with Groq/Ollama locally, OpenAI in production

### Dynamic Selector Extraction
Playwright crawls the live application and extracts real locators — not guessed ones.
- Higher script reliability
- Reduced selector maintenance
- Real-world UI validation built in

### AI Script Generation
Creates executable, ready-to-run Playwright JavaScript automatically.
- Eliminates manual scripting entirely
- Scales to any number of test cases
- Consistent code quality across all generated scripts

### GitHub Integration
Scripts are auto-committed with full version history.
- Full traceability of every generated test
- Team collaboration ready
- Rollback support built in

### CI/CD Execution
GitHub Actions triggered on every commit — no manual runs.
- Continuous validation after every generation
- Immediate pass/fail feedback
- Zero manual intervention required

### Screenshot Evidence
Screenshots captured at every execution step.
- Audit-ready visual proof
- Easier debugging without manual reproduction
- Evidence attached directly to reports

---

##  Technical Challenges Solved

### Challenge 1 — Selector Reliability
**Problem:** AI-generated selectors are often brittle and break on UI changes.  
**Solution:** Implemented a Playwright-based live extraction engine that pulls real selectors directly from the running application — not hallucinated ones.

### Challenge 2 — Script Accuracy
**Problem:** AI-generated scripts may reference elements that don't match the actual UI.  
**Solution:** Built a locator merge engine that injects extracted real-world selectors into AI-generated script logic before execution.

### Challenge 3 — Continuous Validation
**Problem:** Generated tests need automated verification without manual trigger.  
**Solution:** Integrated GitHub Actions to automatically execute every committed script and report results immediately.

---

##  Tech Stack

| Category | Technologies |
|----------|-------------|
| **Testing** | Playwright, JavaScript |
| **AI / LLM** | OpenAI, Groq, Ollama |
| **Orchestration** | n8n |
| **CI/CD** | GitHub Actions |
| **Storage** | Google Sheets |
| **Integrations** | Jira API, GitHub API |
| **Version Control** | GitHub |

---

##  Business Impact

| Before | After |
|--------|-------|
| Manual test case writing |  AI-generated testcases from requirements |
| Manual selector inspection | Playwright auto-extraction |
| Manual script development |  AI-generated Playwright code |
| Manual GitHub commits |  Auto-committed on generation |
| Manual CI/CD trigger |  Auto-triggered on every commit |
| Manual result tracking |  Screenshots + reports auto-generated |

**Result:** A QA engineer can go from requirement to executed, evidence-backed test — without writing a single line of code manually.

---

##  Future Enhancements

- [ ] Self-healing locators
- [ ] API automation generation
- [ ] Visual regression testing
- [ ] Cross-browser execution
- [ ] AI-based defect categorization
- [ ] Automatic bug creation in Jira

---

##  Author

**Sirol Varshini**  
*QA Engineer · Automation Engineer*

**Specializations**
- AI-Powered Playwright Automation
- Test Automation Frameworks
- Workflow Automation with n8n
- CI/CD Pipeline Integration
- Quality Engineering

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/your-username)
