# Flashcard Generator & Study Assistant

A Jupyter-based AI agent system that extracts, generates, and displays study flashcards from YouTube video transcripts. Built as a submission for the **Google 5-Day AI Agents Intensive Capstone Project**.

---

## 🚀 Overview

This project demonstrates how to build a multi-step, agent-powered workflow that:

1. Fetches a transcript from a YouTube video.
2. Cleans and preprocesses the transcript.
3. Generates structured flashcards using an LLM agent.
4. Displays those flashcards interactively in Jupyter using widgets such as **Accordion** and **ToggleButtons**.

The final result is an end-to-end agent system that transforms long-form educational video content into a manageable study tool.

---

## 🧠 Features Implemented

### ✔️ Multi-Step Agent Pipeline

* **Sequential agents** working in a pipeline:

  * Transcript Agent → Cleaning Agent → Flashcard Generation Agent → Display Layer.
* Each agent performs a specific part of the workflow.

### ✔️ Tools

* **Built-in tools**: Python / code execution in Jupyter.
* Light use of **context engineering** to ensure relevant input is passed between steps.

### ✔️ Interactivity

* Uses **ipywidgets** to present flashcards:

  * Accordion view
  * ToggleButton view
  * Randomized card shuffling

### ✔️ Clean & Extendable Architecture

* Easy to upgrade with more agent types (quiz generator, summarizer, analyzer, etc.)
* Modular design where each section can be replaced or improved.

---

## 🛠️ Installation & Requirements

### Requirements

* Python 3.10+
* Jupyter Notebook or JupyterLab
* Required packages:

  ```bash
  pip install ipywidgets youtube-transcript-api
  ```
* LLM access (e.g., OpenAI, Gemini, local model)

### Enabling Widgets

In JupyterLab:

```bash
pip install jupyterlab_widgets
```

In classic Jupyter Notebook:

```bash
jupyter nbextension enable --py widgetsnbextension
```

---

## 📂 Project Structure

```
/flashcard-agent
├── notebook.ipynb          # Main project notebook
├── flashcard_utils.py      # (optional) helper methods
├── README.md               # This file
```

---

## ▶️ How to Use

1. Open the notebook.
2. Provide the YouTube URL you want to study from.
3. Run the pipeline cells:

   * Extract transcript
   * Clean transcript
   * Generate flashcards via the LLM
   * Display the interactive UI
4. Use the widgets to flip between questions + answers.

---

## 📘 Example Flashcard JSON Output

```json
[
  {
    "question": "What is overfitting in machine learning?",
    "answer": "When a model memorizes the training data instead of generalizing patterns."
  }
]
```

---

## 🏗️ Agent Architecture Description

The pipeline follows this structure:

### 1. Transcript Agent

* Fetches YouTube transcript using `youtube-transcript-api`.

### 2. Cleaning Agent

* Removes timestamps, noise, filler words.
* Performs light formatting.

### 3. Flashcard Agent (LLM)

* Takes processed text & outputs structured flashcards.
* Ensures consistent formatting.

### 4. Flashcard Display Layer

* Displays flashcards in Jupyter via:

  * Accordion
  * ToggleButtons (Q/A flip-style)

---

## 📈 Limitations & Future Work

### Possible upgrades:

* Add a **Quiz Mode** agent.
* Add **long-term memory** to store prior video flashcards.
* Add **retrieval** for reviewing past decks.
* Add **multi-video summarization**.
* Add **metrics** for flashcard quality.

---

## 🙌 Acknowledgements

Built as part of the **Google AI Agents Intensive Course**.
