# Assignment 4 — Building Your AI Team

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will build and configure a set of specialized AI subagents inside your project. You will learn how different models and tool permissions define agent behavior, and you will trigger two real agent delegations to analyze security and cost aspects of your Terraform infrastructure.

---

# Task 1 — Create the Agents Folder and Add Files

## Goal

Create the `.claude/agents/` directory and add all required agent files.

### Evidence

#### Screenshot 1 — VS Code sidebar showing `.claude/agents/` with all 3 files

![Screenshot 1](screenshots\4th_assignment\1st_screensort.png)

---

# Task 2 — Compare the Agent Configurations

## Goal

Analyze the configuration differences between the three agents and demonstrate understanding of model and tool selection.

### Written Answers

#### 1. Why does the cost optimizer use Haiku instead of Sonnet?

  Haiku is chosen because it is significantly cheaper and faster, making it ideal for scanning large amounts of billing data or  resource logs. Since the logic (e.g., "downsize underutilized instances") is relatively simple, the advanced reasoning power of Sonnet isn't needed, and using it would ironically increase the cost of the optimization process itself.

---

#### 2. Why does the security auditor NOT have Write in its tools list?

The security auditor lacks the Write tool to enforce the Principle of Least Privilege.

By remaining read-only, the auditor can identify vulnerabilities without the risk of accidentally introducing new bugs or  security holes. This ensures a separation of concerns, forcing a human or a separate "fixer" agent to review and approve any changes, maintaining a clean audit trail and preventing unauthorized modifications to the codebase.

---

#### 3. Why does the tf-writer use `inherit` instead of a specific model?

The tf-writer uses inherit to ensure consistency and flexibility.

By inheriting the model, it automatically uses whatever model the parent agent or user has selected for the session. This  prevents "model mismatch" and allows the user to upgrade the intelligence of the entire pipeline (e.g., switching from Haiku to Sonnet) in one place without having to manually update every individual agent definition.

---

### Evidence

#### Screenshot 2 — `security-auditor.md` frontmatter showing model and tools configuration

![Screenshot 2](screenshots\4th_assignment\2nd_screensort.png)
---

#### Screenshot 3 — `cost-optimizer.md` frontmatter showing the model and tools configuration

![Screenshot 3](screenshots\4th_assignment\3rd_screensort.png)

---

# Task 3 — Run the Security Auditor

## Goal

Trigger the security auditor agent and analyze the generated security report for your Terraform infrastructure.

### Evidence

#### Screenshot 4 — The delegation message showing Claude launched the security-auditor

![Screenshot 4](screenshots\4th_assignment\4th_screensort.png)

---

#### Screenshot 5 — Security audit report output

![Screenshot 4](screenshots\4th_assignment\4th_screensort.png)
![Screenshot 5](screenshots\4th_assignment\5th_screensort.png)
---

# Task 4 — Run the Cost Optimizer

## Goal

Trigger the cost optimizer agent and review the generated cost optimization report.

### Evidence

#### Screenshot 6 — The full cost optimization report

![Screenshot 6](screenshots\4th_assignment\6th_screensort.png)
![Screenshot 6](screenshots\4th_assignment\6_1th_screensort.png)
![Screenshot 6](screenshots\4th_assignment\7th_screensort.png)

---

# Submission Instructions

- Ensure all agent files are committed in `.claude/agents/`
- Complete all written answers in your GitHub Repo
- Push final changes to your forked GitHub repository

---

## GitHub Repository URL

Paste your forked repository URL here:

`Add your URL here`

---

# Completion Checklist

- [✅] `.claude/agents/` folder contains all 3 agent files
- [✅] Screenshot 2 shows correct `security-auditor.md` configuration
- [✅] Screenshot 3 shows correct `cost-optimizer.md` configuration
- [✅] All 3 written answers completed 
- [✅] Security auditor executed successfully
- [✅] Cost optimizer executed successfully
- [✅] Security report is visible with findings
- [✅] Cost report is visible with recommendations
- [✅] All required screenshots added
- [✅] GitHub repo updated with agents

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*