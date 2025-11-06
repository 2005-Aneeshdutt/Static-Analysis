# Static-Analysis - Static Code Analysis Submission

Static code analysis of the Inventory System program for **SE Lab 5** using `pylint`, `flake8`, and `bandit`.

**Repository:** [https://github.com/2005-Aneeshdutt/Static-Analysis](https://github.com/2005-Aneeshdutt/Static-Analysis)

---

## 🧩 Contents

- `inventory_system.py` — original (uncleaned) file  
- `cleaned_inventory_system.py` — updated version with fixes  
- Reports (for both original and cleaned files):
  - `pylint_report_original.txt`, `pylint_report.txt`
  - `flake8_report_original.txt`, `flake8_report.txt`
  - `bandit_report_original.txt`, `bandit_report.txt`
- `reflection.md` — additional notes  
- `.gitignore`, `README.md`

---

## ⚙️ Known Issues Table (before and after cleaning)

| **Tool** | **Issue Detected** | **Description / Example** | **Fix Applied in Cleaned File** |
|-----------|--------------------|----------------------------|---------------------------------|
| **Pylint** | Missing module and function docstrings | Functions had no description | Added docstrings for all functions and the module |
| **Pylint** | Naming convention errors | Used camelCase for variables and functions | Renamed to follow `snake_case` convention |
| **Pylint** | Unused imports / variables | Redundant imports not used | Removed unused imports and variables |
| **Pylint** | Use of print statements for logging | Print used instead of logging | Replaced with `logging` module |
| **Flake8** | Line length > 79 chars | Long lines beyond PEP8 standard | Wrapped or split long lines |
| **Flake8** | Extra or missing blank lines | Formatting issues | Adjusted spacing according to PEP8 |
| **Flake8** | Indentation errors | Code blocks not aligned properly | Corrected indentation |
| **Bandit** | Bare `except:` statements | Could catch unintended exceptions | Replaced with specific exception types |
| **Bandit** | Files opened without context manager | Risk of unclosed file handles | Used `with open()` syntax |
| **Bandit** | Potential insecure function usage | Insecure input handling | Added input validation and safer alternatives |

---

## 🧾 Reflection Questions & Answers

### 1️ Which issues were easiest to fix?
Formatting issues, missing docstrings, and unused imports were easy to fix since they did not affect logic. These were mostly PEP8 compliance corrections.

### 2️ Which issues were hardest to fix?
Bandit security warnings related to unsafe functions and exception handling were hardest since they required logic modification and testing to ensure functionality wasn’t broken.

### 3️ Did any tools report false positives?
Yes, a few style warnings from `pylint` (for function names used intentionally by libraries) and security warnings from `bandit` on safe code patterns that matched general rules.

### 4️ How can static analysis be integrated into a workflow?
By using **pre-commit hooks** and **GitHub Actions** CI, so `pylint`, `flake8`, and `bandit` run automatically on every commit/push and block code with critical issues.

### 5️ What tangible improvements were observed?
The cleaned code became more consistent, readable, and secure. It now follows PEP8 standards, has proper logging, and avoids common runtime and security pitfalls.

---

## 📊 Reports

### Original (Uncleaned)
- `pylint_report_original.txt`
- `flake8_report_original.txt`
- `bandit_report_original.txt`

### Cleaned
- `pylint_report.txt`
- `flake8_report.txt`
- `bandit_report.txt`

Each file documents the tool outputs before and after code cleanup.

---

