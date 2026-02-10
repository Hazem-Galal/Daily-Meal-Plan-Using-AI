# 🍽️ Daily Meal Plan Generator

An AI-powered daily meal plan generator that creates healthy, calorie-controlled recipes with photorealistic food images, audio narration, and video scripts — built with **OpenAI GPT-4o**, **DALL·E 3**, **TTS**, and **Gradio**, designed to run in **Google Colab**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Hazem-Galal/Daily-Meal-Plan-Using-AI/blob/main/Daily_Meal_Plan_Generator.ipynb)

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🧠 **AI Meal Planning** | GPT-4o generates balanced Breakfast, Lunch & Dinner recipes |
| 📊 **Calorie Tracking** | Total daily intake stays under your target (1200–3500 kcal) |
| 📝 **Precise Recipes** | Exact ingredient quantities, step-by-step instructions, prep/cook times |
| 🖼️ **Food Photography** | DALL·E 3 generates photorealistic images for each meal |
| 🔊 **Audio Narration** | OpenAI TTS reads out each recipe's ingredients & cooking steps |
| 🎥 **Video Scripts** | AI-generated short-form cooking video scripts (for Sora, Runway, Pika) |
| 🎛️ **Interactive UI** | Gradio web interface with sliders, checkboxes, and progress indicators |
| 🔒 **Ingredient Control** | Option to use only your listed ingredients or allow AI additions |

---

## 🚀 Quick Start

### 1. Open in Google Colab

Click the badge above or go to:  
👉 [Open in Colab](https://colab.research.google.com/github/Hazem-Galal/Daily-Meal-Plan-Using-AI/blob/main/Daily_Meal_Plan_Generator.ipynb)

### 2. Set up your OpenAI API Key

1. In Colab, click the **🔑 Secrets** icon in the left sidebar
2. Add a new secret:
   - **Name:** `OPENAI_API_KEY`
   - **Value:** Your OpenAI API key
3. Toggle **Notebook access** to ON

> Don't have an API key? Get one at [platform.openai.com/api-keys](https://platform.openai.com/api-keys)

### 3. Run All Cells

Click **Runtime → Run all** or press `Ctrl+F9`. The Gradio UI will launch with a public URL.

### 4. Generate Your Meal Plan

- Enter your available **ingredients** (comma-separated)
- Set your **max daily calories** with the slider
- Optionally check **"Exact ingredients only"** to restrict the AI
- Optionally uncheck **"Generate DALL·E images"** to save cost
- Optionally uncheck **"Generate audio narration"** to skip TTS
- Add any **dietary constraints** (e.g., "high-protein", "vegetarian")
- Click **🚀 Generate Meal Plan**

---

## 📸 Screenshots

After generation, you'll see a styled meal plan with:

- 🌅 **Breakfast**, ☀️ **Lunch**, and 🌙 **Dinner** cards
- Photorealistic DALL·E 3 food images
- Calorie badges and time estimates
- Embedded audio players to listen to each recipe
- Expandable video scripts and DALL·E prompts
- Total calorie tracker vs. your target

---

## 🏗️ Architecture

```
User Input (Gradio UI)
        │
        ▼
   build_prompt()          ← Renders prompt template with user inputs
        │
        ▼
   GPT-4o API Call         ← Generates 3 structured recipes
        │
        ▼
   parse_meal_plan()       ← Regex parser extracts fields from response
        │
        ▼
   DALL·E 3 API (×3)      ← Generates food photography for each meal
        │
        ▼
   TTS API (×3)            ← Generates audio narration for each recipe
        │
        ▼
   render_full_plan()      ← Builds styled HTML cards with images & audio
        │
        ▼
   Gradio HTML Output      ← Displayed in the browser
```

---

## 💰 API Cost Estimate

| Component | Cost per run |
|-----------|-------------|
| GPT-4o (1 call, ~4K tokens) | ~$0.03 |
| DALL·E 3 (3 images, 1024×1024) | ~$0.12 |
| TTS (3 audio narrations) | ~$0.03 |
| **Total** | **~$0.18** |

> Uncheck "Generate DALL·E images" and/or "Generate audio narration" in the UI to reduce cost.

---

## 📁 Project Structure

```
├── Daily_Meal_Plan_Generator.ipynb   # Main Colab notebook (all-in-one)
├── prompt.txt                        # Original prompt template
└── README.md                         # This file
```

---

## 🛠️ Technologies

- **[OpenAI GPT-4o](https://platform.openai.com/docs/models/gpt-4o)** — Meal plan text generation
- **[DALL·E 3](https://platform.openai.com/docs/guides/images)** — Photorealistic food image generation
- **[OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech)** — Audio narration of recipes & cooking steps
- **[Gradio](https://www.gradio.app/)** — Interactive web UI
- **[Google Colab](https://colab.research.google.com/)** — Free cloud execution environment

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
