# PureWeb Rules

This repo hosts the **remote rule set** for the [PureWeb](https://github.com/) browser extension.  
Rules here tell PureWeb how to detect and hide AI overviews, answer panels, and other “noise” in search results.

---

## 📄 rules.json Format

```jsonc
{
  "keywords": {
    "aiHints": [
      "AI Overview",
      "Overview",
      "Generative",
      "Generated answer",
      "From sources across the web",
      "Summarized",
      "Ask follow-up"
    ],
    "extras": {
      "paa": ["People also ask"],
      "videos": ["Videos"],
      "discussions": ["Discussions and forums", "Forums"]
    }
  },
  "selectors": {
    "google": [".s6JM6d"],
    "bing": [".b_algoAI"],
    "ddg": [".zci-answer"]
  }
}
