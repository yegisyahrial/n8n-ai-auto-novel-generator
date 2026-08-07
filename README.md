# 🚀 AI-Powered Auto Novel Generator Assistant

An end-to-end automated web novel generation workflow built with **n8n**, **Google Gemini AI**, **Google Sheets**, and **Google Docs**. 

This system automates the entire process of writing long-form fiction—from reading story outlines, character profiles, and previous chapter context to generating full-length chapters and publishing them directly to Google Docs.

---

## 📌 Problem Statement

Writing multi-chapter web novels manually or relying on standard LLM prompts presents several major challenges:
* **Narrative Drift & Hallucinations:** AI models frequently forget previous events, lore, and character traits over long chapter arcs.
* **Context Loss:** Lack of continuity between consecutive chapters leads to plot holes and awkward transitions.
* **Manual Bottlenecks:** Formatting, copying/pasting, creating files, and tracking chapter progress manually takes time away from plotting and editing.

---

## 💡 The Solution

An integrated n8n workflow designed to maintain strict narrative continuity and automate publishing:

1. **Database Trigger & Data Retrieval:** Fetches story metadata, character sheets, location lore, and chapter outlines from **Google Sheets**.
2. **Context & State Management:** A custom JavaScript node determines the next planned chapter and dynamically fetches the exact text of the previous chapter.
3. **Contextual AI Agent:** Utilizes **Google Gemini LLM** provided with active character sheets, location settings, writing style rules, and previous chapter prose.
4. **Automated Publishing & Logging:** Creates a formatted **Google Doc** with the new chapter, appends the doc link to the database, and updates the outline status to `Done`.

---

## 🏆 Key Features & Benefits

* 🧠 **Zero Context Loss:** Reads the exact manuscript of Chapter $N-1$ to open Chapter $N$ with a seamless transition.
* 👥 **Dynamic Character Filtering:** Only injects active characters and current location lore into the prompt to optimize context usage.
* 📝 **Strict Prose Formatting:** Enforces short, punchy paragraphs (2–4 sentences), dialogue line breaks, and zero raw Markdown symbols.
* 📈 **Scalable Architecture:** Capable of handling outlines ranging from 10 to 200+ chapters without degrading output quality.
* 📁 **Fully Automated Pipeline:** Automatically creates files, logs URLs, and updates progress in real time.

---

## 🏗️ System Architecture & Workflow
