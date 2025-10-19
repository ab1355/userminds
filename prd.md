## Product Requirements Document: Upvoty Pro (AI-Enhanced Feedback Platform)

---

## 1. Introduction

### **1.1 Goal**
To transform Upvoty from a simple feedback collection tool into an **AI-powered strategic prioritization engine**. This version will automate the most time-consuming aspects of product management—triage, prioritization, and communication—enabling teams to ship features with the highest business impact faster.

### **1.2 Target User**
* **Product Managers/Owners:** Seeking to reduce manual triage time and gain confidence in prioritization decisions backed by quantitative data.
* **Product Marketing/Customer Success:** Needing automated, granular communication to close the feedback loop effectively.
* **Executives/Leadership:** Requiring high-level dashboards to understand the flow and business impact of feature requests.

---

## 2. Features and Requirements

### **2.1 AI-Powered Feedback Triage & Prioritization**

| Feature | Description | Key Requirements |
| :--- | :--- | :--- |
| **Auto-Tagging & Categorization** | AI automatically applies relevant **Tags** and assigns incoming feedback posts to a product area or feature. | Must achieve >90% accuracy against manually-tagged posts. Must be trainable on new custom tags. |
| **Sentiment Analysis** | Analyze comments and post text to determine overall sentiment (Positive, Neutral, Negative, Frustrated, Urgent). | Sentiment scores must be visible on the **Feedback Boards** and filterable on the analysis dashboard. |
| **Value Scoring (Prioritization Matrix)** | A calculated score for each post based on business impact factors. | Must be customizable via a formula (e.g., $Impact = (Votes \times Sentiment \times User\_Tier\_Weight)$). **User SSO** integration is mandatory for tier-weighting. |
| **Merge AI 2.0** | Enhanced AI to automatically detect and suggest merging duplicate posts with higher accuracy. | Must suggest the most accurate "master post" based on detail/age. |

### **2.2 Advanced Workflow Automation**

| Feature | Description | Key Requirements |
| :--- | :--- | :--- |
| **Roadmap-to-Changelog Sync** | Automatic generation of a **Changelog** draft entry when a **Roadmap** item moves to "Done." | PM must be able to review and approve/edit the draft before publishing. Must link to the original feature post. |
| **Granular User Notification** | Ability to notify specific subsets of users about updates. | Notification filters must include: 1) Voted/Commented on this post, 2) User Tier/Plan (from SSO), 3) Specific **Tags**. |
| **Development Tool Sync (e.g., Jira/GitHub)** | Two-way integration to keep the **Roadmap** and development sprints aligned. | Status changes in Jira/GitHub (e.g., "In Progress") must update the **Roadmap** status automatically and vice-versa. |

### **2.3 Integrated Communication & Proactive Feedback**

| Feature | Description | Key Requirements |
| :--- | :--- | :--- |
| **In-App Micro-Surveys** | Trigger short, contextual surveys directly within the customer's application. | Must integrate via an embeddable widget (separate from the main widget). Must be triggered by user behavior (e.g., after 3 uses of a specific feature). |
| **Direct Product Chat** | Secure, internal messaging system linked to each feedback post for PMs to follow up with the original author. | Chat history must be logged against the feedback post. User identity must remain secure. |

### **2.4 Analytics and Reporting**

| Feature | Description | Key Requirements |
| :--- | :--- | :--- |
| **Custom Dashboards** | Users can create personalized dashboards visualizing feedback data. | Must allow charting and combining **Value Score**, **Sentiment**, **Tags**, and **Launch Dates**. |
| **Feedback Funnel Visualization** | A report showing the flow of ideas: Idea $\to$ Voted $\to$ Planned $\to$ Launched. | Must clearly identify bottlenecks (e.g., "50% of high-value ideas stall in 'Planned'"). |

---

## 3. Scope and Acceptance Criteria

### **3.1 Out of Scope**
* Full-fledged project management/sprint planning system (rely on Jira/GitHub integration).
* Video-based feedback collection.

### **3.2 Key Success Metrics (KPIs)**
* **Decrease in Manual Triage Time:** Target 50% reduction in time spent manually sorting/tagging new posts.
* **Increase in User Notification Rate:** Target 25% increase in users notified about the features they requested.
* **Feature-to-Value Conversion:** Target a 15% increase in the number of high **Value Score** posts moving to the "Launched" status.

---

## 4. Notes

* Package Manager: This project uses bun for package management. Always use bun instead of npm or yarn.

* Testing
The project uses Bun's built-in test runner for optimal performance:

* Linting and Formatting
The project uses Biome for linting and formatting:

* Deployment:
Akash 

* Environment Configuration
Runtime: Bun (preferred over Node.js for 50x faster performance)
Package Manager: Bun (configured in package.json as "packageManager": "bun@1.2.18")
Module Type: ES modules ("type": "module" in package.json)
Platform: Windows-optimized with PowerShell scripts
Build Tool: tsup for dual ESM/CJS output with TypeScript declarations

* Troubleshooting
Common Issues
General Issues
Dependency Installation: Use bun install instead of npm to avoid hanging
Build Failures: Check TypeScript configuration and run bun affected --target=build
Test Issues: Ensure Bun test runner is properly configured in project.json
Windows Execution: Use PowerShell with ExecutionPolicy Bypass for scripts
