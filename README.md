# 🎨 AI Moodboard Generator (Wayfair Externship Project)
Built with **n8n** | Google Gemini | Hugging Face (FLUX.1-schnell)
---
## 📋 The Problem
Wayfair customers and interior-design shoppers often have a clear aesthetic in mind but struggle to turn it into something visual:
- Describing a style in words is easier than finding it
- Manually building a moodboard means searching through large numbers of products and images
- There was an opportunity to use AI to turn a natural-language style preference directly into a curated visual moodboard
---
## ✅ The Solution
A conversational AI agent, built in n8n as part of an externship program with Wayfair, that takes a simple natural-language style prompt and returns a polished, ready-to-use moodboard image — no manual searching required.
---
## ⚙️ How It Works
1. A user describes a style in chat (e.g. "a bohemian rug in a cozy living room, natural light, wooden floors")
2. An AI agent, powered by Google Gemini and a custom prompt-engineering system prompt, expands that idea into one detailed, styled image-generation prompt — covering colors, textures, materials, and complementary decor elements
3. A code node cleans the AI's raw output (removes line breaks, markdown formatting, and fixes quote characters) into an API-ready format
4. The cleaned prompt is sent via HTTP POST to Hugging Face's image generation API, using the FLUX.1-schnell model
5. The returned base64 image data is converted into an actual downloadable PNG moodboard
---
## 🛠️ Tools Used
| Tool | Purpose |
|------|---------|
| n8n | Workflow & agent orchestration |
| Google Gemini (via LangChain agent node) | Prompt generation from a simple style idea |
| Hugging Face API (FLUX.1-schnell) | Image generation |
| JavaScript (n8n Code node) | Cleaning the AI's raw output for the image API |
---
## 💡 Key Features
- **Prompt-engineering agent** — a dedicated system prompt turns a one-line idea into a detailed, styled image prompt, with strict output rules so it's always API-ready
- **End-to-end automation** — from a natural-language idea straight to a finished image, no manual steps in between
- **Fast turnaround** — completes in under 30 seconds, tested end-to-end from chat input to PNG output
- **Output cleaning layer** — strips markdown and formatting artifacts from the LLM's response before it's used downstream
---
## n8n Screenshot

<img width="1919" height="951" alt="Screenshot 2026-07-16 054439" src="https://github.com/user-attachments/assets/433db3cf-ec94-4d09-b661-7845e760f0d5" />

---
## 📁 Files
- [`moodboard_image_generator_Agent.json`](moodboard_image_generator_Agent.json) — The n8n workflow (import directly into your n8n instance)

---
## 🚀 How To Use This Workflow
1. Download [`moodboard_image_generator_Agent.json`](moodboard_image_generator_Agent.json)
2. Open your n8n instance
3. Click **Import** and select the file
4. Connect your own Google Gemini and Hugging Face credentials
5. Activate the workflow and open the chat panel to test
---
*Built by [Martins](https://github.com/martinsautomates) as part of an AI/automation externship with Wayfair*
