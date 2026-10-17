# 🚀 AI Sales CRM — Intelligent Lead Management & Follow-up Automation

### AI-Powered CRM | n8n Automation | Google Gemini | Google Sheets | Gmail | Looker Studio

An intelligent Customer Relationship Management (CRM) system designed to automate lead qualification, prioritize sales opportunities, streamline follow-up activities, and visualize sales performance.

This project combines **AI, workflow automation, and business analytics** to demonstrate how businesses can reduce manual CRM tasks and improve their sales processes.

## 📌 Project Overview

The AI Sales CRM consists of three integrated components:

1. **AI Lead Management & Qualification** — Automatically evaluates incoming leads, assigns scores, and classifies them into Hot, Warm, or Cold categories.
2. **Daily Follow-up Scheduler** — Checks follow-up dates, sends reminders, and updates CRM records.
3. **Sales Analytics Dashboard** — Provides interactive visualizations of lead distribution, pipeline activity, follow-up tracking, and AI-generated scores.

The system uses Google Sheets as a lightweight CRM database, n8n for workflow orchestration, Google Gemini for intelligent analysis, Gmail for email communication, and Google Looker Studio for reporting.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| Google Gemini | AI lead scoring, classification, and email generation |
| Google Sheets | CRM database and lead tracking |
| Gmail | Email notifications and personalized drafts |
| Google Looker Studio | Sales analytics and visualization |
| JavaScript / Expressions | Data processing, conditions, and workflow logic |

## ✨ Key Features

### 1. AI-Powered Lead Qualification

When a potential client submits an inquiry form, the system:

- Captures client information and project requirements.
- Stores the lead in Google Sheets.
- Analyzes project details, budget, and buying intent using Google Gemini.
- Generates an AI lead score.
- Categorizes the lead as Hot, Warm, or Cold.
- Suggests the next sales action.
- Updates the CRM database automatically.

**Lead categories:**

| Category | Description | Automated Action |
|---|---|---|
| 🔥 Hot | High-priority leads with strong buying intent | Send a sales notification email |
| 🌤️ Warm | Interested prospects who need more information | Generate a personalized follow-up email draft |
| ❄️ Cold | Low-priority leads without immediate purchasing intent | Update CRM status for future nurturing |

### 2. Intelligent Lead Routing

The system uses conditional routing to direct leads to different automation branches based on their AI-generated category.

This enables businesses to prioritize high-potential clients while maintaining organized records of prospects who may require future engagement.

### 3. AI-Generated Follow-up Emails

For Warm leads, Google Gemini generates personalized follow-up content based on the client's inquiry.

The automation creates a Gmail draft that can be reviewed and edited before sending.

This combines AI-assisted communication with human review.

### 4. Daily Follow-up Scheduler

A separate n8n workflow handles follow-up reminders.

**Workflow process:**

1. A Schedule Trigger starts the automation.
2. Google Sheets retrieves CRM lead records.
3. A filter identifies leads with due follow-up dates.
4. Gmail sends a follow-up reminder.
5. Google Sheets updates the reminder tracking information.

The workflow is designed to support timely follow-ups and reduce the need for manual CRM checking.

### 5. CRM Database

Google Sheets serves as the central database for the system.

It stores:

- Lead ID
- Full Name
- Email Address
- Company Name
- Requested Service
- Budget
- Project Details
- Lead Status
- AI Lead Score
- Lead Category
- AI Reasoning
- Recommended Next Action
- Next Follow-up Date
- Last Follow-up Date
- Follow-up Notes
- Last Reminder Sent Date

### 6. Interactive Sales Analytics Dashboard

The system includes a Google Looker Studio dashboard connected to the CRM database.

**Dashboard components:**

**AI Lead Distribution**

A pie chart displaying the percentage of Hot, Warm, and Cold leads.

**CRM Lead Pipeline**

A bar chart showing the number of leads in each CRM status, such as New, Sales Notified, Follow-up Drafted, and Nurture Later.

**CRM Follow-up Tracking**

A table showing lead names, statuses, follow-up dates, reminder information, next actions, and AI scores.

**Average Lead Score**

A KPI card displaying the average AI-generated score across the CRM dataset.

The dashboard helps visualize lead quality, sales activity, and follow-up priorities.

## 🔄 System Architecture

```text
WORKFLOW 1 — AI LEAD MANAGEMENT

Lead Submission Form
        |
        v
Edit & Prepare Lead Data
        |
        v
Google Sheets — Save Lead
        |
        v
Google Gemini — AI Analysis
        |
        v
Process AI Results
        |
        v
Google Sheets — Update Lead
        |
        v
Lead Routing
        |
        +---- HOT ----> Gmail Notification
        |                     |
        |                     v
        |              Update CRM Status
        |
        +---- WARM ---> Gemini Follow-up
        |                     |
        |                     v
        |              Create Gmail Draft
        |                     |
        |                     v
        |              Update CRM Status
        |
        +---- COLD ---> Update CRM Status


WORKFLOW 2 — DAILY FOLLOW-UP

Schedule Trigger
        |
        v
Google Sheets — Read Leads
        |
        v
Follow-up Due Filter
        |
        v
Gmail — Send Reminder
        |
        v
Google Sheets — Update Record


ANALYTICS

Google Sheets CRM Database
        |
        v
Google Looker Studio
        |
        v
Sales Analytics Dashboard
```

## 📊 Project Screenshots

## 🎬 Project Demonstration

The demonstration uses fictional client inquiries to illustrate how the CRM processes different lead categories.

**Demonstrated scenarios:**

- Hot Lead — High buying intent and immediate sales notification.
- Warm Lead — Interested prospect and AI-generated follow-up draft.
- Cold Lead — Low-priority prospect and CRM status update.

The project also includes a daily reminder workflow and a sales analytics dashboard.

**Demo video:** [Watch the demonstration](demo/demo-video.mp4)

## ⚙️ How to Use

### Prerequisites

- An n8n instance or n8n Cloud account
- Google account with access to Google Sheets and Gmail
- Google Gemini API access
- Google Looker Studio

### Setup

1. Import the provided workflow JSON files into n8n.
2. Configure the required Google Sheets, Gmail, and Gemini credentials.
3. Create a CRM spreadsheet with the required columns.
4. Select the correct spreadsheet and sheet in each Google Sheets node.
5. Configure the AI classification prompts and lead routing rules.
6. Review Gmail recipients and follow-up conditions.
7. Configure the scheduler's timezone and execution frequency.
8. Test the workflows using fictional leads and email addresses you control.
9. Connect the CRM spreadsheet to Google Looker Studio to recreate the analytics dashboard.
10. Activate the workflows only after successful testing.

**Note:** Imported workflows require configuration and testing before they can run in a different environment.

## 🧪 Testing

The lead management workflow was tested using fictional client inquiries representing Hot, Warm, and Cold leads.

Testing focused on:

- Form submissions
- AI-generated lead scores
- Lead classification
- Conditional routing
- Gmail notifications and drafts
- CRM record updates

The daily follow-up workflow should also be validated for due-date filtering, successful reminders, record updates, and duplicate-reminder prevention before production use.

## 🔒 Security & Limitations

- No API keys, OAuth secrets, or private credentials should be included in this repository.
- Demonstrations should use fictional client information.
- Gmail drafts allow human review before contacting prospects.
- AI-generated lead classifications may require manual review.
- Google Sheets is suitable for this prototype but may not be ideal for large-scale CRM operations.
- Concurrent updates, access controls, error handling, and duplicate prevention require additional safeguards for production deployment.

## 🚀 Future Improvements

- Dedicated CRM web dashboard
- Automatic appointment scheduling
- WhatsApp and Slack notifications
- AI-generated follow-up sequences
- Advanced lead scoring models
- Sales conversion and revenue analytics
- CRM integrations with HubSpot or Salesforce
- More robust database and audit logging

## 💼 Project Applications

This system demonstrates automation opportunities for:

- Digital marketing agencies
- Freelancers and consultants
- Sales teams
- Service-based businesses
- Startups and small businesses

## 👩‍💻 Developer

**Nour Ben Fekih Ahmed**

Software Engineering Student | Web Development | AI & Automation

- **GitHub:** https://github.com/benfekihnourrr
- **LinkedIn:** https://www.linkedin.com/in/nour-ben-fekih-ahmed-505778347

---

*Built as a portfolio project demonstrating practical AI integration, workflow automation, CRM management, and business intelligence reporting.*
