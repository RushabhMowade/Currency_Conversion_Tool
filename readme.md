# Currency Conversion Tool 💱

An AI-powered currency conversion tool built using **Python, LangChain, Google Gemini, and ExchangeRate-API**.

The project demonstrates how a Large Language Model (LLM) can use **custom tools/function calling** to fetch live currency exchange rates and perform currency conversions automatically.

---

## 🚀 Features

- 🌍 Convert between different currencies
- 🔄 Fetch exchange rates using ExchangeRate-API
- 🤖 Powered by Google Gemini 2.5 Flash
- 🛠️ Uses LangChain custom tools
- 🔗 Demonstrates LLM tool/function calling
- 📡 Uses an external API for exchange-rate data
- ☁️ Built and tested using Google Colab
- 🔢 Automatically calculates the converted amount

---

## 🧠 Project Overview

The application uses **Google Gemini 2.5 Flash** as the reasoning layer.

Instead of manually calculating the conversion, Gemini determines which tool needs to be called based on the user's request.

The application contains two custom tools:

1. `get_conversion_factor`
2. `convert`

The first tool retrieves the exchange rate, while the second performs the actual mathematical conversion.

---

## 🔄 How It Works

```text
                    User Query
                        │
                        ▼
              ┌──────────────────┐
              │  Gemini 2.5 Flash │
              └────────┬─────────┘
                       │
                       ▼
              Identify Required Tool
                       │
             ┌─────────┴─────────┐
             │                   │
             ▼                   │
  get_conversion_factor()        │
             │                   │
             ▼                   │
      ExchangeRate-API           │
             │                   │
             ▼                   │
      Conversion Rate            │
             │                   │
             └─────────┬─────────┘
                       ▼
                  convert()
                       │
                       ▼
               Converted Amount
                       │
                       ▼
              Gemini Final Answer


