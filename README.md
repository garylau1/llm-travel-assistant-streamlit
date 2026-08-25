# llm-travel-assistant-streamlit

Markdown
# Personal Travel Assistant & Multi-LLM Benchmark

Hi there! 👋 This is my project for postgraduate Natural Language Processing / Text Generation[cite: 3]. It explores building an interactive dialogue system for travel planning while benchmarking cloud-based LLM APIs against local open-source models[cite: 3].

The application features a multi-step **Streamlit** user interface connected to **Google Gemini (gemini-2.0-flash)** and a locally hosted **Gemma 3:1B (via Ollama)**, evaluating their reasoning, bilingual generation, and contextual refinement capabilities[cite: 3, 4].

---

## 📌 Project Overview

Planning personalized travel involves handling diverse constraints (dates, budgets, interests, age-appropriate activities, and language preferences)[cite: 3]. This project tackles that workflow by:
* Designing a conversational flow that collects user constraints step-by-step[cite: 3, 4].
* Generating detailed, multi-day personalized itineraries[cite: 3].
* Allowing iterative refinement (e.g., adding specific cultural activities or preferences after the initial plan)[cite: 3, 4].
* Testing privacy preservation and implementing prompt guards to minimize model hallucinations[cite: 3, 4].

---

## 🛠️ Key Components & Implementation

### 1. Multi-LLM Backend Architecture
* **Cloud API Integration:** Configured the `google-genai` SDK to interface with `gemini-2.0-flash` for high-accuracy, zero-setup inference[cite: 3, 4].
* **Local Deployment with Ollama:** Deployed `gemma3:1b` locally within the runtime environment via Ollama to evaluate offline privacy, latency, and resource efficiency[cite: 3, 4].

### 2. Interactive Streamlit Interface
* Built a stateful, 6-step guided dialogue app using `st.session_state`[cite: 4]:
  1. **Task Definition:** Clarifies the core objective (trip planning, accommodations, flights)[cite: 3, 4].
  2. **Personal Information & Privacy:** Collects optional details (name, age, gender) while allowing users to skip to protect privacy[cite: 3, 4].
  3. **Language Selection:** Supports bilingual interaction (English and Simplified Chinese)[cite: 3, 4].
  4. **Travel Preferences:** Gathers destinations, travel timing, trip styles, and budget constraints[cite: 3, 4].
  5. **Initial Plan Generation:** Generates a structured daily itinerary based on gathered context[cite: 3, 4].
  6. **Iterative Refinement:** Accepts follow-up user inputs to enrich the final itinerary with specific attractions and local guidelines[cite: 3, 4].

### 3. Prompt Engineering & Safeguards
* **Context Injection:** Injects reliable travel context guidelines and user history into refined prompt iterations[cite: 3, 4].
* **Hallucination & Safety Controls:** Explicitly constrains outputs to verified details, includes verification disclaimers for users, and strips unnecessary personal identifiers before model inference[cite: 3, 4].

---

## 📊 Comparative Analysis: Gemini vs. Gemma 3:1B

Across multiple structured test scenarios (varying traveler age, budget, cultural themes, and language)[cite: 3]:
* **Gemini 2.0 Flash:** Demonstrated strong instruction following, accurate bilingual text generation (English/Chinese), and reliable incorporation of multi-turn refinements (such as specific museum visits and budget adjustments)[cite: 3].
* **Gemma 3:1B (Local):** Provided fast local execution and detailed general logistics, but occasionally required tighter prompt phrasing to maintain consistent bilingual outputs and avoid follow-up queries when instructed to finalize[cite: 3].

---

## 📁 Repository Structure
* `source_code.ipynb` - Jupyter / Google Colab notebook containing environment setup, API configurations, and prompt experiment logs[cite: 4, 5].
* `source_code.py` - Streamlit application code
* `Final_report.pdf` - Project report detailing prompt engineering strategies, dialogue design, and comparative experimental results[cite: 3].
