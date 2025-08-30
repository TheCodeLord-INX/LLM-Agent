

# 🌐 GyaanSetu LLM Agent — Multi-Tool Reasoning in Your Browser

**[Live Demo](https://tds-bonus-project-llm-agent.vercel.app/)**

GyaanSetu LLM Agent is a browser-based proof-of-concept that brings together natural language reasoning and external tools—like search, AI pipelines, and live JavaScript execution—into a single, hackable web app. The agent loops intelligently, using multiple tools as needed, until your task is complete.

---

## 🚀 Highlights

- **Model Picker:** Instantly switch between AI Pipe Proxy (default), OpenAI GPT, Gemini, Claude, and more using a dynamic dropdown.
- **Reasoning Loop:** The agent takes your input, queries the LLM, and repeatedly calls tools (using OpenAI-style function calls) until the job is done.
- **Integrated Tools:**
  - 🔎 Google Search snippets for real-time info
  - 🔗 AI Pipe Proxy for flexible AI workflows
  - ⚡ JavaScript sandbox for safe, in-browser code execution
- **Modern UI/UX:**
  - Clean Bootstrap interface
  - Streaming chat with file upload
  - Error handling via Bootstrap alerts
  - Performance monitor and tool action logs

---

## 🧩 How It Works

1. User enters a prompt in the browser.
2. The agent queries the selected LLM provider.
3. If the LLM requests a tool, the agent executes it and feeds the result back.
4. This loop continues until the LLM signals completion.

**Conceptual Agent Loop:**
```python
def loop(llm):
    msg = [user_input()]
    while True:
        output, tool_calls = llm(msg, tools)
        print("Agent:", output)
        if tool_calls:
            msg += [handle_tool_call(tc) for tc in tool_calls]
        else:
            msg.append(user_input())
```

This logic is implemented in browser JavaScript, connected to your chosen provider.

---

## 🛠️ Getting Started

### Requirements

- A modern browser (Chrome, Edge, Firefox, etc.)
- API keys for:
  - [AI Pipe](https://aipipe.org/) proxy API (recommended)
  - Optionally: OpenAI, Gemini, or other providers

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/23f1000805/tds-bonus-project-LLM-Agent.git
   cd tds-bonus-project-LLM-Agent
   ```
2. Open `index.html` in your browser. *(No server needed—runs fully client-side!)*
3. Enter your API key in the app’s Settings Panel.

---

## 🎨 UI & Code Principles

- **Model Picker:** Built with `bootstrap-llm-provider`.
- **Agent Loop:** Event-driven JavaScript for LLM ↔ Tool calls.
- **Error Handling:** All errors surfaced via Bootstrap alerts.
- **Minimal, Hackable Code:** Designed for easy extension and experimentation.

---

## � Example Interaction

**User:** Interview me to create a blog post.
**Agent:** Sure! What’s the post about?

**User:** About IBM.
**Agent:** Let me search for IBM.
→ *(calls `search("IBM")`)*

**Agent:** IBM is a global tech company founded in 1911...

**User:** Next step, please.
**Agent:** Let’s draft an outline for your blog post...

---

## 🧪 What’s Included

- Browser-based JS app with:
  - LLM chat window
  - Google Search integration
  - AI Pipe proxy support
  - JavaScript execution sandbox
- OpenAI-style function calling
- Graceful error handling
- Easily extensible for new tools

---

## ✅ Evaluation

| Criteria               | Marks   |
| ---------------------- | ------- |
| Output functionality   | **1.0** |
| Code quality & clarity | **0.5** |
| UI/UX polish & extras  | **0.5** |
| **Total**              | **2.0** |

---

## � File Structure

```
├── index.html    # Main UI (chat + settings)
├── agent.js      # Agent logic, providers, and tools
├── styles.css    # Stylesheet
└── README.md     # Documentation
```

---

## � Credits

- [AI Pipe](https://aipipe.org/) for proxy API workflows
- OpenAI, Anthropic, Google for LLM APIs
- Bootstrap for UI components

---

## 🔮 Roadmap

- Add conversation persistence (IndexedDB/localStorage)
- Enable streaming, token-by-token responses
- Expand toolset: file parsing, charting, SQL, and more

---
