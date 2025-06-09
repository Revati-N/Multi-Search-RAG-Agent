# 🧠 Multi-Search RAG Agent (LangChain + Ollama + LLaMA2)

This repository contains an experimental implementation of a **multi-source Retrieval-Augmented Generation (RAG) agent**, built with [LangChain](https://www.langchain.com/) and powered **locally** using the **LLaMA2 model via Ollama**.
The purpose of this notebook was to explore and better understand how LangChain tools, agents, and local LLMs can be combined to build flexible and private information retrieval systems.

---

## 📌 Features

* 🔎 **Multi-source search**: The agent queries:

  * [Wikipedia](https://www.wikipedia.org/)
  * [Arxiv](https://arxiv.org/)
  * Different domain-specific websites (via requests and scraping)

* 🧰 **LangChain Tools & Agents**: Utilizes LangChain's `create_openai_functions_agent` and tool wrappers for modular querying.

* 🤖 **Local LLM Inference**: Entirely local setup using [Ollama](https://ollama.com/) running `LLaMA2` — no external API keys or internet access required after setup.

* 🧪 **Learning-focused**: Designed as a hands-on exploration of retrieval workflows and agent orchestration within LangChain.

---

## 🧑‍💻 Setup Instructions

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Set Up Ollama

Install Ollama and pull the LLaMA2 model:

```bash
ollama run llama2
```

> Visit [https://ollama.com](https://ollama.com) for installation guides for your OS.

---

## 🚀 How It Works

The agent uses LangChain’s **Function Calling Agent** setup and a toolkit of search tools. Here's a breakdown:

* **Wikipedia Tool** → Uses `WikipediaAPIWrapper` with specific `top_k` and `content_max_char` constraints.
* **Arxiv Tool** → Uses `ArxivQueryRun` to fetch academic papers related to the query.
* **Custom Tool** → Queries a specific site (defined in the code) when conditions are met.
* **LLaMA2 via Ollama** → Acts as the reasoning engine that decides how to use these tools, all locally.

---

## 📚 Example Use Cases

* "What is quantum computing ?"
* "Give a brief summary of AI in healthcare"

---

## 🎯 Purpose

This is not a full-fledged product but rather a **learning-focused prototype** designed to:

* Explore the integration of multiple retrieval tools in LangChain.
* Experiment with **local-only inference pipelines** using open models.
* Understand agent reasoning and routing behavior.

