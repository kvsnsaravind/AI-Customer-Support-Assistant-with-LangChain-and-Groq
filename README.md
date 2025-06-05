# AI-Customer-Support-Assistant-with-LangChain-and-Groq
An intelligent, real-time customer support assistant powered by LLaMA 3, LangChain, LangGraph, and Groq for ultra-fast LLM inference.


# 🤖 AI-Powered Customer Support Assistant

This is a real-time, intelligent customer support assistant powered by **LangChain**, **LangGraph**, and **Groq**’s ultra-fast **LLaMA 3** models. It classifies incoming customer queries, analyzes sentiment, routes them to the appropriate handler, and escalates when needed — all with blazing-fast LLM inference.

---

## 🚀 Features

- 🔍 **Query Categorization**: Automatically classifies queries as `Technical`, `Billing`, or `General`.
- 😐 **Sentiment Analysis**: Detects if the tone of the query is `Positive`, `Neutral`, or `Negative`.
- 🧠 **Smart Routing**: Sends the query to the correct support handler or escalates to a human.
- ⚡ **Groq-Powered LLaMA 3 Inference**: Experience sub-second latency on complex LLM calls.
- 🔄 **Modular Workflow with LangGraph**: Easily extend or modify the graph of logic blocks.

---

## 🧱 Tech Stack

| Component    | Description                            |
|--------------|----------------------------------------|
| LangChain    | Prompt chaining and LLM orchestration  |
| LangGraph    | Stateful workflow management (DAG)     |
| Groq         | Inference backend for LLaMA models     |
| LLaMA 3      | Language model used for reasoning      |
| Python       | Core programming language              |

---

## 🔧 Setup Instructions

### 1. Install Dependencies

```bash
pip install python-dotenv langchain[groq]
````

> Optionally, you can run this in a Google Colab environment as well.

### 2. Set GROQ API Key

#### In Google Colab:

```python
from google.colab import userdata
import os
os.environ['GROQ_API_KEY'] = userdata.get('groqAPIKey')
```

#### Or using `.env` locally:

Create a `.env` file:

```
GROQ_API_KEY=your-groq-api-key
```

---

## 🧠 What is Groq?

**Groq** is a high-performance inference engine that runs LLMs like **LLaMA 3** using custom-built **GroqChips™** designed for ultra-low latency.

In this project:

* Groq acts as the **API provider** for running the `"llama3-8b-8192"` model.
* You interact with the model via LangChain using:

  ```python
  llm = init_chat_model("llama3-8b-8192", model_provider="groq")
  ```
* This removes the need to host or manage LLaMA yourself.
* Think of it as a **super-fast OpenAI alternative** for LLM inference.

🔗 [Groq Website](https://groq.com/) | [Groq Console](https://console.groq.com/)

---

## 🔁 How It Works

1. **Categorize** – LLM classifies the query topic.
2. **Sentiment Analysis** – Analyzes emotional tone.
3. **Routing** – Based on sentiment and category:

   * `handle_technical()`
   * `handle_billing()`
   * `handle_general()`
   * or `escalate()` for negative sentiment
4. **Respond** – Returns a support reply or escalates.

---

## 🧩 Example Usage

```python
query = {"query": "I was charged incorrectly on my bill and I'm angry!"}
app.invoke(query)
```

### Output:

```
Category: Billing  
Sentiment: Negative  
Response: This query has been escalated to a human agent.
```
---


## 📜 License

This project is open-source under the MIT License.

---

## 🙌 Acknowledgements

* [LangChain](https://github.com/langchain-ai/langchain)
* [LangGraph](https://github.com/langchain-ai/langgraph)
* [Groq](https://groq.com/)
* [Meta LLaMA 3](https://ai.meta.com/llama/)

