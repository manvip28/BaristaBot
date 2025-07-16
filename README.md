# ☕ BaristaBot – Cafe Ordering Assistant (LangGraph + Gemini)

A conversational AI assistant built with **LangGraph**, **Gemini**, and **LangChain**.

---

## 🚀 Features

- 🍵 Multi-turn chatbot for ordering drinks and breakfast
- 🧠 Built with LangGraph to manage chat and tool flows
- 🔧 Gemini-powered tools for `get_menu`, `add_to_order`, `confirm_order`, etc.
- 📦 Dynamic order tracking with state management
- 💬 Text-only interface using `input()` and `print()` (no UI)

---

## 🛠️ Setup in Google Colab

### 1. Configure API Key

Add your Gemini API key securely:

```python
from google.colab import userdata
import os

os.environ["GOOGLE_API_KEY"] = userdata.get("GOOGLE_API_KEY")
```

Then in **Colab → Settings → Secrets**, add a new secret:

```
Key: GOOGLE_API_KEY
Value: <your gemini api key>
```

---

### 2. Install Required Packages

```bash
!pip install -q langgraph langchain langchain-google-genai
```

---

### 3. Run the Graph

Make sure your code includes:
- Tool definitions using `@tool`
- `OrderState` and chatbot logic
- `StateGraph` and conditional edges
- ToolNode + custom `order_node`
- Execution loop (below)

---


---

## 🧰 Available Tools

| Tool             | Description                                  |
|------------------|----------------------------------------------|
| `get_menu()`     | Returns the full drink and food menu         |
| `add_to_order()` | Adds a drink/food item with modifiers        |
| `clear_order()`  | Clears the entire order                      |
| `get_order()`    | Lists current order                          |
| `confirm_order()`| Asks the user to confirm current order       |
| `place_order()`  | Places the final order and shows ETA         |

---

## 🧠 Why Use LangGraph?

LangGraph helps:
- Route between human/tool/chat logic easily
- Maintain order state
- Avoid hallucinations in order confirmation
- Visually understand agent flows

---


