#  AI-Powered QA Automation Platform

> End-to-end platform that transforms requirements into executable Playwright tests — zero manual scripting.

---

##  Overview

Built a production-grade platform that eliminates manual QA bottlenecks — from requirement ingestion to CI/CD execution — using AI at every layer of the testing pipeline.

---

##  Automated Pipeline — 9 Stages

| # | Stage | Description |
|---|-------|-------------|
| 01 |  Trigger | User initiates the test generation workflow |
| 02 |  AI Test Case Gen | AI generates structured test cases from requirements |
| 03 |  Sheets Storage | Test cases are stored and tracked in Google Sheets |
| 04 |  Selector Extraction | Playwright crawls the live UI and extracts locators |
| 05 |  Script Generation | AI produces executable Playwright test scripts |
| 06 |  Merge + Commit | Scripts merged with locators and auto-committed to GitHub |
| 07 |  CI/CD Run | GitHub Actions triggered automatically |
| 08 |  Screenshots | Visual evidence captured at execution |
| 09 |  Reports | Pass/fail results surfaced after every run |

---

##  Key Features

### AI Test Case Generation
Automatically generates structured test cases from plain JIRA requirements — no manual authoring.

###  Dynamic Selector Extraction
Uses Playwright to crawl the live UI and extract locators directly from the target application.

###  Automation Script Generation
Creates executable Playwright test scripts end-to-end without human input.

###  CI/CD Integration
Auto-commits generated scripts to GitHub and triggers GitHub Actions for every run.

###  Screenshot Evidence
Captures visual proof at execution — ready for audit trails and bug reports.

###  Automated Reporting
Pass/fail results surfaced immediately after each pipeline run.

---

##  Tech Stack

| Category | Tools |
|----------|-------|
| **Testing** | Playwright, JavaScript |
| **AI / LLM** | OpenAI, Groq, Ollama |
| **Orchestration** | n8n |
| **CI / Storage** | GitHub Actions, Google Sheets |
| **Integrations** | Jira API |

---

##  Workflow
Requirements
 → 
AI Test Case Generation
 → 
Google Sheets (Storage)
 → 
Playwright Selector Extraction
 → 
AI Script Generation
 → 
Locator Merging
 → 
GitHub Auto-Commit
 → 
GitHub Actions Execution
 → 
Screenshots + Reports

---

*Built end-to-end · Requirements → Scripts → CI/CD → Reports · Zero manual scripting*
