# Crawl4AI DeepSeek Example

A minimal Python example that uses Crawl4AI with a DeepSeek-backed LLM extraction strategy to scrape structured data from a web page.

The current script targets the LMSYS Chatbot Arena leaderboard and demonstrates how to configure Crawl4AI for schema-guided extraction.

## What This Project Shows

- Running Crawl4AI's async crawler
- Using `LLMExtractionStrategy`
- Supplying an LLM provider through an environment variable
- Defining a Pydantic schema for extracted records
- Parsing extracted JSON results from a crawled page

## Tech Stack

- Python
- Crawl4AI
- DeepSeek API
- Pydantic
- asyncio

## Setup

Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

Install Crawl4AI:

```bash
pip install crawl4ai
crawl4ai-setup
```

Set your DeepSeek API key:

```bash
export DEEPSEEK_API=your_api_key_here
```

## Run

```bash
python main.py
```

If extraction succeeds, the script prints the structured items returned by the LLM extraction strategy and shows LLM usage details.

## Files

```text
.
├── main.py       # Async Crawl4AI extraction example
├── test.json     # Sample / scratch output
└── readme.md
```

## Notes

The schema in `main.py` is intentionally tiny and can be expanded to match the target table more precisely. For reliable production extraction, align the Pydantic model fields with the instruction text and validate the returned JSON before using it downstream.
