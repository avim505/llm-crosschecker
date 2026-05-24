# 🔍 LLM Cross-Checker — AI Response Verification Extension

A Chrome browser extension that automatically verifies AI responses across multiple models simultaneously. Get an instant accuracy verdict, bias detection, and confidence scoring on any ChatGPT or Claude response — without leaving the page.

---

## 🖥️ How It Works

```
You get a response from ChatGPT or Claude
              ↓
Click the Cross-Check button that appears below the response
              ↓
Extension routes the response to multiple AI models simultaneously
              ↓
Results panel appears directly on the page showing:
✅ HIGH CONFIDENCE — All models agree the response is accurate
⚠️  CAUTION — Models partially disagree — review carefully
❌ HIGH RISK — Multiple models flagged inaccuracies
```

---

## ⚙️ Features

- **Real-time verification** — Cross-checks any AI response without leaving the page
- **Multi-model consensus** — Routes to Claude, GPT-4o, Gemini, Cohere, Groq, and DeepSeek simultaneously
- **Bias detection** — Identifies potential bias flagged across models
- **Confidence scoring** — Per-model and average confidence percentage
- **Verdict classification** — ACCURATE, PARTIALLY ACCURATE, INACCURATE, or UNVERIFIABLE
- **Free tier** — 10 checks per month with 2 models, no signup required
- **Pro tier** — Unlimited checks with all 6 models
- **BYOK** — Bring your own API keys for maximum control

---

## 🛠️ Tech Stack

| Component         | Technology         | Purpose                                          |
| ----------------- | ------------------ | ------------------------------------------------ |
| Extension         | Chrome Manifest V3 | Browser extension framework                      |
| Content Script    | JavaScript         | Detects AI responses and injects UI              |
| Background Worker | JavaScript         | Handles API communication                        |
| Payment           | ExtensionPay       | Subscription management                          |
| Backend API       | Node.js, Express   | Secure API key management and verification logic |
| Database          | MongoDB Atlas      | User storage and usage tracking                  |
| Hosting           | Render.com         | Backend server deployment                        |

---

## 📁 Project Structure

```
llm-crosschecker/
├── ExtPay.js              # ExtensionPay library for payments
├── manifest.json          # Chrome extension configuration
├── background.js          # Service worker — handles messaging and API calls
├── content/
│   ├── content.js         # Injected into ChatGPT and Claude pages
│   └── content.css        # Styles for injected UI components
├── popup/
│   ├── popup.html         # Extension popup — settings and upgrade UI
│   ├── popup.js           # Popup logic — plan status, BYOK, upgrade flow
│   └── popup.css          # Popup styles
└── icons/
    ├── icon16.png
    ├── icon48.png
    └── icon128.png
```

---

## 🚀 Installation

### From Chrome Web Store (Recommended)

```
Search "LLM Cross-Checker" in the Chrome Web Store
Click Add to Chrome
Navigate to ChatGPT or Claude and start cross-checking
```

### Manual Install (Developer Mode)

```
1. Clone this repo:
   git clone https://github.com/YOUR_USERNAME/llm-crosschecker.git

2. Open Chrome and go to:
   chrome://extensions/

3. Enable Developer Mode (top right toggle)

4. Click Load unpacked

5. Select the llm-crosschecker folder

6. Extension appears in your toolbar
```

---

## 💳 Plans

| Feature            | Free                | Pro            | BYOK          |
| ------------------ | ------------------- | -------------- | ------------- |
| Checks per month   | 10                  | Unlimited      | Unlimited     |
| Models             | 2 (Claude + Cohere) | 6 (All models) | 6 (Your keys) |
| Bias detection     | Basic               | Full           | Full          |
| Confidence scoring | ✓                   | ✓              | ✓             |
| Price              | Free                | $4.99/month    | $1.99/month   |

**Free tier** requires no signup — works immediately on install.

**Pro tier** unlocks all 4 models and unlimited checks via ExtensionPay.

**BYOK (Bring Your Own Key)** — Enter your own API keys in the popup. Your keys are stored securely on our backend and used only for your verification requests.

## 🤖 Models Used For Verification

| Model             | Provider  | Plan       |
| ----------------- | --------- | ---------- |
| Claude Sonnet     | Anthropic | Free + Pro |
| Cohere Command R+ | Cohere    | Free + Pro |
| GPT-4o            | OpenAI    | Pro only   |
| Gemini 2.0 Flash  | Google    | Pro only   |
| Llama 3.3 70B     | Groq      | Free + Pro |
| DeepSeek R1       | Google    | Free + Pro |

---

## 🔒 Privacy & Security

- **No browsing history collected** — the extension only activates on ChatGPT and Claude
- **No prompts stored** — only the AI response text is sent for verification, never your questions
- **Response text not retained** — verification text is processed and immediately discarded
- **API keys encrypted** — BYOK keys stored securely and never exposed
- **Anonymous by default** — identified by a random install ID, no personal data required

Full privacy policy: https://github.com/avim505/llm-crosschecker-privacy

---

## 🏗️ Backend

The verification logic and API key management runs on a separate private backend repository deployed on Render.com. The extension communicates with this backend for all AI verification requests.

Backend handles:

- Secure API key storage and routing
- Free tier usage tracking (10 checks/month limit)
- Subscription status syncing with ExtensionPay
- Simultaneous multi-model API calls
- Overall verdict calculation and bias aggregation

---

## 📚 Relevant Use Cases

```
Research and fact-checking
→ Verify claims before using them in reports or essays

Professional work
→ Cross-check AI-generated content before sending to clients

Education
→ Understand when AI responses should be trusted or questioned

Journalism
→ Quick first-pass verification of AI-sourced information

Developers
→ Validate AI-generated code explanations and documentation
```

---

## ⚠️ Disclaimer

LLM Cross-Checker is a verification aid tool and does not guarantee factual accuracy. AI model responses used for verification are themselves subject to hallucination and error. Always verify critical information through authoritative primary sources.

---

## 👤 Author

**Avinesh Mohanaranjan**
Founder, WebCore Agency — AI automation, agents, and workflows

- GitHub: https://github.com/avim505
- LinkedIn: https://www.linkedin.com/in/avineshmohanaranjan/
- Agency: https://webcoreagency.ca

---

## 📄 License

MIT License — free to use, modify, and distribute with attribution.
