# IT23821118-playwright-automation-testing-Assignment1
# Option 1: Transliteration Accuracy Testing

This project contains automated test cases for the [Pixels Suite Chat Translator](https://www.pixelssuite.com/chat-translator) web application using the **Playwright** framework. The test suite validates the accuracy of **Chat Sinhala transliteration** by testing chat-style Singlish input and evaluating the correctness of the Sinhala output.

---

## 📋 Project Overview

- **Total Test Cases**: 50
  - **Negative Test Cases**: 50 (Neg_0001 to Neg_0050)
- **Test Objective**: Identify scenarios where the system **fails** to correctly convert chat-style Singlish into Sinhala
- **Target URL**: [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

---

## 🎯 Test Objectives

The test suite validates:
- Singlish to Sinhala transliteration accuracy
- Various Singlish input types including question forms, command forms, greetings, requests, responses, repeated words, punctuation, spelling variants, English insertions, slang, emojis, and more
- Edge cases such as abbreviated spellings, mixed-case inputs, numeric suffixes, currency, dates, time formats, and online identifiers
- Failure scenarios where the translator produces incorrect Sinhala output

---

## 🛠️ Prerequisites

Before running the tests, ensure you have:

- **Python** 3.11 / 3.12 / 3.14
- **pip** (Python package manager)
- **Google Chrome** (recommended) or Playwright will install Chromium automatically
- **Git** (for cloning the repository)

---

## 📦 Installation

### 1. Clone the repository:
```bash
git clone https://github.com/Pamodhaya/IT23821118-playwright-automation-testing-Assignment1.git
cd IT23821118-playwright-automation-testing-Assignment1
```

### 2. Install required Python packages:
```bash
pip install -U pip
pip install playwright openpyxl
```

### 3. Install Playwright browsers:
```bash
python -m playwright install
```

---

## 🚀 Running Tests

### Run all 50 test cases:
```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Command Arguments Explained:

| Argument | Value | Description |
|---|---|---|
| `--excel` | `"Assignment 1 - Test cases.xlsx"` | Path to the Excel test cases file |
| `--url` | `"https://www.pixelssuite.com/chat-translator"` | Target website URL |
| `--wait-ms` | `5000` | Wait time in milliseconds after each input |
| `--type-delay-ms` | `80` | Delay between each keystroke in milliseconds |
| `--slow-mo-ms` | `200` | Slow motion delay for browser actions |
| `--save-every` | `1` | Save results to Excel after every test case |
| `--keep-open` | — | Keep browser open after test completion |

---

## 📁 Project Structure

```
IT23821118-playwright-automation-testing-Assignment1/
├── test_automation.py              # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx  # Excel file with all 50 test cases
└── README.md                       # Project documentation
```

---

## 📊 Excel File Structure

The Excel file **"Assignment 1 - Test cases.xlsx"** contains the following columns:

| Column | Name | Description |
|---|---|---|
| A | Test Case ID | Unique ID starting with 'Neg' (e.g., Neg_0001) |
| B | Input length type | S (≤30 chars), M (31–299 chars), L (300–450 chars) |
| C | Input | Singlish input text |
| D | Expected output | Correct Sinhala translation |
| E | Actual output | Auto-filled by automation script |
| F | Status | Auto-filled as PASS or FAIL |
| G | Singlish input types covered | Input type(s) from Appendix 1 |
| H | Evidence or rationale | Explanation of why this input type is covered |

---

## 🧪 Test Cases Overview

All 50 test cases are **negative test cases** — scenarios where the translator **fails** to produce the correct Sinhala output.

### Singlish Input Types Covered (24 types × 2 minimum each):

| # | Input Type | Test Case IDs |
|---|---|---|
| 1 | Question forms | Neg_0001, Neg_0002 |
| 2 | Command forms | Neg_0003, Neg_0004 |
| 3 | Greetings | Neg_0002, Neg_0005 |
| 4 | Requests | Neg_0006, Neg_0014 |
| 5 | Responses | Neg_0007, Neg_0010 |
| 6 | Repeated Words | Neg_0008, Neg_0012 |
| 7 | Inputs with Punctuation Marks | Neg_0005, Neg_0015 |
| 8 | Romanization / Spelling Variants | Neg_0003, Neg_0011 |
| 9 | Isolated English Word Insertions | Neg_0016, Neg_0039 |
| 10 | Multi-Word English Phrases | Neg_0040 |
| 11 | English Digital Terms | Neg_0041 |
| 12 | Platform/App Names | Neg_0021, Neg_0033 |
| 13 | English Abbreviations/Acronyms | Neg_0008, Neg_0013 |
| 14 | English Clipped Forms | Neg_0019 |
| 15 | Place Names Embedded | Neg_0031, Neg_0045 |
| 16 | Person Names Embedded | Neg_0032, Neg_0043 |
| 17 | Inputs with Numbers and Numeric Suffixes | Neg_0023, Neg_0044 |
| 18 | Inputs with Currency | Neg_0017, Neg_0023 |
| 19 | Inputs with Time Formats | Neg_0022, Neg_0049 |
| 20 | Inputs with Dates | Neg_0028 |
| 21 | Inputs with Unit of Measurements | Neg_0026, Neg_0030 |
| 22 | Inputs with Slang and Casual Phrasing | Neg_0020, Neg_0029 |
| 23 | Online Identifiers | Neg_0027, Neg_0042 |
| 24 | Inputs Containing Emojis | Neg_0018, Neg_0034 |

---

## ✅ Expected Test Results

- **All 50 test cases**: Expected to **FAIL**
- Status column will show `FAIL` for all rows after automation runs
- This is expected — these are intentionally designed as failure scenarios

---

## 🔧 How It Works

1. The script opens the Chrome browser automatically
2. Navigates to [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)
3. For each row in the Excel file:
   - Types the Singlish input into the translator
   - Waits for the Sinhala output to appear
   - Captures the actual output
   - Compares it with the expected output
   - Records the result as PASS or FAIL
4. Saves results to the Excel file after every test case

---

## 🌐 Target Application

**Website**: [https://www.pixelssuite.com/chat-translator](https://www.pixelssuite.com/chat-translator)

The Pixels Suite Chat Translator converts chat-style Singlish (Sinhala written in English characters) into proper Sinhala script. This assignment tests the **Chat Sinhala** transliteration function only.

> **Note**: Evaluating the Standard Sinhala transliteration function, backend APIs, and conducting performance, scalability, or security testing are **outside the scope** of this assignment.

---

## 🐛 Troubleshooting

### `playwright` is not recognized?
Use the Python module approach instead:
```bash
python -m playwright install
```

### Tests failing unexpectedly?
1. Ensure you have a stable internet connection
2. Increase `--wait-ms` value (e.g., `--wait-ms 8000`)
3. Reinstall browsers:
```bash
python -m playwright install --force
```

### pip permission error?
Run with user flag:
```bash
pip install playwright openpyxl --user
```

### Excel file not found?
Make sure the Excel file is in the **same folder** as `test_automation.py` before running the script.

---

## 👤 Author

- **Student ID**: IT23821118
- **Unit**: IT3040 – IT Project Management
- **Assignment**: Assignment 1 – Option 1: Transliteration Accuracy Testing
- **Repository**: [GitHub – IT23821118-playwright-automation-testing-Assignment1](https://github.com/Pamodhaya/IT23821118-playwright-automation-testing-Assignment1.git)

---

## 📄 License

This project is created for **educational purposes** as part of the IT3040 – ITPM unit coursework at SLIIT.
