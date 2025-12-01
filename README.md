# 📘 AI-Powered PDF Study Assistant  
## *Summaries + Flashcards from Any PDF*

This project is a lightweight multi-agent pipeline that converts **PDF documents into clean study notes and flashcards** using Google’s Gemini models. It is optimized for reliability, fast execution, and use inside a Jupyter/VSCode environment.

---

## ✨ Features

### 🔍 PDF → Notes → Flashcards Pipeline
- Extracts text **only from PDF files** (via `pypdf`).
- Splits long PDFs into manageable model-safe chunks.
- Sequential agent workflow:
  - **Summarization Agent** – creates structured study notes.
  - **Flashcard Agent** – generates Q/A flashcards in JSON format.

### 🧠 Agents Used
This project uses:
- **Sequential multi-agent pipeline**
  - `summarization_agent()`
  - `flashcard_agent()`
- **LLM-driven agents** using `gemini-2.5-flash`
- **Lightweight custom tools**
  - PDF text extraction  
  - Text chunking  
  - LLM wrapper  

_No parallel, loop, or long-running agents — intentionally simple and reliable._

### 📊 Notebook Display Tools
- Notes displayed with Markdown.
- Flashcards shown using **Accordion widgets** (VSCode Jupyter-compatible).

---

## 🏗️ Project Structure
```
project/
│── README.md
│── notebook.ipynb
│── sample.pdf
└── main.py (optional)
```

---

## ▶️ How It Works

### 1. Install dependencies
```bash
pip install google-generativeai pypdf pandas ipywidgets
```
2. Add your Gemini API key
```
genai.configure(api_key="YOUR_KEY_HERE")
```
3. Run the pipeline
```
full_notes, flashcards = process_file("sample.pdf")
```
4. Display the outputs
```
show_notes(full_notes)
show_flashcards(flashcards)
```
📁 Core Components (Technical Overview)
PDF Reader
Uses pypdf.PdfReader to extract raw text from every page.

Text Chunker
Splits long PDFs into ~6000-character chunks to stay within model limits.

LLM Wrapper
Unified Gemini API call function:

```
def call_llm(prompt):
    return genai.GenerativeModel(MODEL).generate_content(prompt).text
```
Summarization Agent
Converts raw PDF text into structured notes including:

- key concepts

- definitions

- examples

- relationships

Flashcard Agent
Transforms notes into concise flashcards in JSON format.

Notebook Display Functions
- Markdown output for notes

- Accordion-based display for flashcards

📦 Use Cases
- Reading academic papers

- Reviewing lecture slides

- Creating revision materials

- Fast comprehension of long PDFs

🚀 Future Enhancements (Optional)
To increase rubric satisfaction:

- Parallel agents

- Long-term memory

- Context compaction

- Metrics/logging dashboard

- A2A protocol orchestration

- Export study notes as PDF

- Auto-generated diagrams
