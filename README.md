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

Sections
	•	keywords.aiHints → text snippets PureWeb scans for in top-of-page blocks (catch AI overviews even if classes change).
	•	keywords.extras → text triggers for optional “noise reducers” like PAA, Videos, or Discussions panels.
	•	selectors → CSS selectors for known containers on each search engine (more precise, but can break when class names change).

⸻

🔄 Updating Rules
	1.	Edit rules.json directly on GitHub (or push via Git).
	2.	In Chrome: chrome://extensions → PureWeb → Options → Rule updates.
	3.	Click Update now.
	4.	The extension merges your updated rules with its built-in defaults.

⸻

🛠 Contributing
	•	PRs welcome if you find a new AI box selector or keyword that slips through.
	•	Keep keywords broad but not too generic (avoid words that appear in normal search results).
	•	Use selectors when you can reliably target a container element.

⸻

✅ Example Use Cases
	•	Google adds a new AI layout → add a selector like .fooAIBox.
	•	Bing renames its AI class → update "bing": [".new_class_here"].
	•	DDG adds “AI Chat” panel → add "AI Chat" under keywords.aiHints.

⸻

📜 License

MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
