# ✍️ LinxAI – Multi-Agent LinkedIn Content Generator

> An advanced **multi-agent AI content generation system** built with **LangGraph**, **LangChain**, **Mistral AI**, **Llama 3.3 (Groq)**, and **Tavily Search**. LinxAI automatically researches, writes, reviews, and iteratively improves LinkedIn posts until they meet professional publishing standards.

---

# 🚀 Overview

LinxAI is an autonomous AI workflow that simulates a professional editorial team. Instead of generating a LinkedIn post in a single step, it follows an **iterative writer-reviewer feedback loop** where multiple AI agents collaborate to produce high-quality, engaging content.

The writer agent researches the topic, drafts a post, and the reviewer agent evaluates it against strict quality standards. If the post doesn't meet the criteria, detailed feedback is sent back to the writer for revision. This process continues until the content is approved or the maximum number of iterations is reached.

---

# 🤖 Multi-Agent Workflow

LinxAI consists of four intelligent agents orchestrated using **LangGraph**.

## 📝 Writer Agent

* Generates engaging LinkedIn posts
* Uses Mistral AI for content creation
* Incorporates reviewer feedback into new drafts
* Can invoke external tools when fresh information is required

---

## 🌐 Research Agent (Tavily Search)

Before writing, the system determines whether the topic requires current statistics, news, or trends.

If needed, the Writer Agent automatically performs a web search using **Tavily Search** to gather up-to-date information.

---

## 🔍 Reviewer Agent

The Reviewer Agent evaluates every draft using **Llama 3.3 70B (Groq)** against predefined publishing standards.

Evaluation Criteria:

* Strong opening hook
* One clear takeaway
* Easy-to-read formatting
* 150–200 words
* Professional yet human tone
* No hashtags
* Ends with a question or call-to-action

The reviewer returns either:

* ✅ APPROVED
* ❌ REJECTED + detailed feedback

---

## 🔄 Iterative Feedback Loop

If the reviewer rejects the draft:

* Feedback is sent back to the Writer Agent.
* A new version is generated addressing every issue.
* The cycle repeats until:

  * The post is approved, or
  * Three iterations have been completed.

---

# 🏗 Workflow Architecture

```text
                    User Topic
                         │
                         ▼
                 Writer Agent (Mistral AI)
                         │
             ┌───────────┴───────────┐
             │                       │
     Needs Web Search?          No Search Needed
             │                       │
             ▼                       │
      Tavily Search Tool             │
             │                       │
             └───────────┬───────────┘
                         ▼
                LinkedIn Draft Created
                         │
                         ▼
          Reviewer Agent (Llama 3.3 Groq)
                         │
            ┌────────────┴────────────┐
            │                         │
        APPROVED                 REJECTED
            │                         │
            ▼                         │
      Final LinkedIn Post      Feedback to Writer
                                      │
                                      └───────────────↺
```

---

# ✨ Features

* 🤖 Multi-Agent AI Workflow
* 🧠 LangGraph State Machine
* 🌐 Automatic Web Research
* 🔍 AI Content Review
* 🔄 Self-Improving Feedback Loop
* ✍️ Human-like LinkedIn Posts
* 📈 Professional Editorial Pipeline
* ⚡ Tavily Search Integration
* 🚀 Mistral AI Content Generation
* 🎯 Groq Llama 3.3 Quality Evaluation

---

# 🛠 Tech Stack

| Technology           | Purpose                |
| -------------------- | ---------------------- |
| Python               | Core Development       |
| LangGraph            | Workflow Orchestration |
| LangChain            | AI Framework           |
| Mistral AI           | Writer Agent           |
| Groq (Llama 3.3 70B) | Reviewer Agent         |
| Tavily Search        | Web Research           |
| python-dotenv        | Environment Variables  |

---

# 📂 Project Structure

```text
LinxAI/
│
├── project.py
├── requirements.txt
├── .env
└── README.md
```

---

# ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/LinxAI.git
cd LinxAI
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it:

### Windows

```bash
.venv\Scripts\activate
```

### macOS/Linux

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# 🔐 Configure Environment Variables

Create a `.env` file:

```env
MISTRAL_API_KEY=your_mistral_api_key
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
```

---

# ▶️ Run the Application

```bash
python project.py
```

Enter a topic:

```text
Artificial Intelligence in Healthcare
```

The system will automatically:

1. Research the topic (if needed)
2. Generate a LinkedIn post
3. Review the content
4. Improve it using reviewer feedback
5. Repeat until approved

---

# 📈 Example Workflow

```text
Topic
   │
   ▼
Writer Agent
   │
   ▼
Web Search (Optional)
   │
   ▼
Draft Generated
   │
   ▼
Reviewer Evaluation
   │
   ├── Approved → Final Post
   │
   └── Rejected
            │
            ▼
      Feedback Returned
            │
            ▼
      Writer Rewrites Draft
            │
            └────────────↺
```

---

# 🔮 Future Improvements

* Multiple reviewer agents
* SEO optimization
* Tone selection (Founder, CEO, Recruiter, Student)
* Company branding support
* Image & carousel caption generation
* LinkedIn scheduling integration
* Analytics-driven content scoring
* Human feedback mode
* Support for X (Twitter), Medium, and Blogs
* AI-powered content calendar

---

