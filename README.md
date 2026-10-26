

# ✍️ Inkcount

### A fast, private word counter with limits, readability and keyword insights.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Dependencies](https://img.shields.io/badge/dependencies-0-2EA043?style=flat-square)
![Privacy](https://img.shields.io/badge/privacy-100%25%20in--browser-FFD84D?style=flat-square&labelColor=1D1A16)

[**Live Demo**](https://YOUR-USERNAME.github.io/inkcount) · [**Report a Bug**](../../issues) · [**Request a Feature**](../../issues)

</div>

---

## Overview

Inkcount counts as you type. It shows words, characters, sentences, paragraphs and reading time, tracks limits for tweets, SMS, LinkedIn posts and essays, scores readability, and lists your top keywords. Everything runs in the browser. Your text is never uploaded.

## Features

| Area | What you get |
|---|---|
| **Counts** | Words, characters, characters without spaces, sentences, paragraphs, unique words, lines |
| **Time** | Reading time (238 wpm) and speaking time (150 wpm) |
| **Word stats** | Average word length and longest word |
| **Limits** | Presets for Tweet (280), LinkedIn post (3,000), Meta description (160), SMS (160), Essay (500 words), Blog (1,000 words), plus a custom goal in words or characters |
| **Progress bar** | Green while safe, amber at 90%, red when over the limit, with the exact number left or over |
| **Readability** | Flesch reading ease score with a plain-language label |
| **Keywords** | Top 8 keywords with frequency bars, ignoring common filler words |
| **Text tools** | UPPERCASE, lowercase, Title Case, Sentence case, clean extra spaces, undo, copy and clear |
| **Draft saving** | Your text is saved in the browser automatically |
| **Themes** | Light and dark, with a manual toggle that is remembered |
| **Responsive** | A sticky word and character counter on phones and tablets |
| **Accessible** | Labelled controls, visible focus rings, status messages and reduced-motion support |

## How Each Number Is Calculated

| Metric | Rule |
|---|---|
| **Words** | Groups of non-space characters, matched with `\S+` |
| **Characters** | Unicode characters in the text, so an emoji counts as one |
| **Characters (no spaces)** | The text with every whitespace character removed |
| **Sentences** | Text split on `.`, `!`, `?` or `…`, counting non-empty parts |
| **Paragraphs** | Blocks separated by a blank line |
| **Unique words** | Distinct lowercase words, ignoring punctuation |
| **Reading time** | words ÷ 238 words per minute |
| **Speaking time** | words ÷ 150 words per minute |
| **Average word length** | Total letters and digits in words ÷ number of words |
| **Keywords** | Words of 3 or more characters, excluding common stop words and pure numbers. Ties are sorted alphabetically |

### Readability

```text
Flesch reading ease = 206.835 − 1.015 × (words ÷ sentences) − 84.6 × (syllables ÷ words)
```

| Score | Label |
|---|---|
| 80 and above | Easy to read |
| 60 to 79 | Plain English |
| 40 to 59 | Fairly difficult |
| Below 40 | Difficult |

The score appears once there are at least 10 words and the text is mostly English letters. Syllables are estimated with a simple rule-based counter, so treat the score as a guide.

## Quick Start

```bash
git clone https://github.com/YOUR-USERNAME/inkcount.git
cd inkcount
open index.html          # or: npx serve .
```

No installs and no build step.

## Customize

**Add or change limit presets**: edit the `PRE` array. Each entry is `[label, limit, "chars" or "words"]`:

```js
const PRE = [
  ["Tweet", 280, "chars"],
  ["Instagram caption", 2200, "chars"],
  ["Essay 500", 500, "words"]
];
```

**Change reading speeds**: edit the two divisors in `update()`: `W/238` for reading and `W/150` for speaking.

**Edit ignored keywords**: add or remove words in the `STOP` set.

**Change the highlight colour**: edit `--hl` in the `:root` block.

## Browser Storage

| Key | Purpose |
|---|---|
| `inkcount-draft` | Your last text |
| `inkcount-theme` | Your light or dark choice |

Both stay on your device. Clear them from your browser's site data whenever you like.

## Deploy for Free

| Platform | Steps |
|---|---|
| **GitHub Pages** | Settings → Pages → Deploy from `main` |
| **Netlify** | Drag and drop the folder |
| **Vercel** | Import the repository |

## Test Checklist

- [ ] Empty text shows zero everywhere and no readability score
- [ ] `Hello world. This is a test!` gives 6 words and 2 sentences
- [ ] A blank line between two blocks gives 2 paragraphs
- [ ] Selecting the Tweet preset and typing 281 characters turns the bar red and shows "1 over the limit"
- [ ] Pressing a preset again clears the limit
- [ ] Title Case, Sentence case, Clean spaces and Undo work in order
- [ ] Refreshing the page restores your draft
- [ ] Dark mode and the mobile sticky counter both look right

## Known Limitations

- Sentence counting is a simple punctuation rule, so abbreviations like "Dr." or numbers like "3.5" can add extra sentences.
- Readability works for English only, and syllables are estimated.
- Keyword stop words are English. Other languages will list every word of 3 or more characters.
- Characters are counted as Unicode code points, so some complex emoji made of several parts count as more than one.

## Roadmap

- [x] Live counts, reading time and keyword list
- [x] Limit presets and custom goals
- [x] Readability score
- [x] Text tools with undo
- [x] Draft saving and themes
- [ ] Download as `.txt` when hosted
- [ ] Find and replace
- [ ] Keyword highlighting inside the text
- [ ] Multi-language stop words
- [ ] Shareable stats image

## Contributing

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-idea`
3. Commit: `git commit -m "Add your idea"`
4. Push and open a pull request

## Author

**S.S. Manikanda Prabu**, B.Tech CSE, SRM Institute of Science and Technology, Ramapuram

[GitHub](https://github.com/YOUR-USERNAME) · [LinkedIn](https://linkedin.com/in/YOUR-PROFILE)

## License

Released under the MIT License.
