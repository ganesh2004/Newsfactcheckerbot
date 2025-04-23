# News Fact-Checker Telegram Bot 📰🤖

A Telegram bot that uses the Mistral-7B LLM and Google Search to fact-check news headlines and claims in real-time.

---

## ✨ Features

*   **Telegram Integration:** Fact-check directly within Telegram.
*   **LLM Analysis:** Uses `mistralai/Mistral-7B-Instruct-v0.3` (via Hugging Face) for analysis.
*   **Web Search:** Fetches real-time context using Google Custom Search API.
*   **Content Scraping:** Extracts text from search result links using `trafilatura`.
*   **Tiered Analysis:** Analyzes top 3 sources first, then up to 5 if the initial result is ambiguous.
*   **Clear Output:** Provides a verdict (Accurate, Inaccurate, etc.), summary, and source links.
*   **Efficient:** Uses 4-bit quantization (`bitsandbytes`) for the LLM.

## ⚙️ How It Works

1.  User sends a claim via Telegram.
2.  LLM generates a Google search query for the claim.
3.  Bot searches Google, scrapes top results.
4.  LLM analyzes scraped content against the claim (in 1 or 2 passes).
5.  Bot formats the LLM's verdict and summary and sends it back to the user.

## 🛠️ Tech Stack

*   **Python 3**
*   **Hugging Face:** `transformers`, `accelerate`, `bitsandbytes`, `torch`
*   **Telegram:** `python-telegram-bot`
*   **Search/Scraping:** `google-api-python-client`, `trafilatura`, `requests`, `beautifulsoup4`
*   **Async:** `asyncio`, `nest_asyncio`

## 🚀 Setup

**1. Prerequisites:**

*   Python 3.8+
*   Telegram Bot Token
*   Google Cloud API Key & Custom Search Engine ID
*   Hugging Face User Access Token
*   CUDA-enabled GPU (Recommended for the LLM)
  or
just run it in colab just by uploading the notebook file(You will still have to get your  keys)

**2. Clone & Install:**

```bash
git clone https://github.com/ganesh2004/Newsfactcheckerbot.git
cd Newsfactcheckerbot
pip install -r requirements.txt 
