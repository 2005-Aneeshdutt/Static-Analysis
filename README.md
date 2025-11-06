# Lab05 - Static Analysis Submission

# Lab05 - Static Analysis Submission

Static code analysis of the inventory system for SE Lab 5 using `pylint`, `flake8`, and `bandit`.

---

## About

This repository contains:
- `inventory_system.py` — original (uncleaned) program.
- `cleaned_inventory_system.py` — cleaned and refactored version after applying fixes suggested by static analysis tools.
- Static analysis reports for both uncleaned and cleaned code:
  - `pylint_report_original.txt`, `pylint_report.txt`
  - `flake8_report_original.txt`, `flake8_report.txt`
  - `bandit_report_original.txt`, `bandit_report.txt`
- `reflection.md` — short write-up about the fixes, challenges and integration ideas.
- `.gitignore` — to exclude the virtual environment and unnecessary files.

---

## Known Issues (from the static analysis reports)

The following were the main issues found in the **original code** and addressed during cleaning:

- **Missing docstrings** — added module and function docstrings.  
- **Naming style** — updated to `snake_case`.  
- **Mutable default arguments** — replaced with `None` and in-function initialization.  
- **Bare `except:` blocks** — replaced with specific exceptions.  
- **File handling** — replaced `open()` with context managers (`with open(...)`).  
- **Bandit security warnings** — resolved unsafe code patterns where possible.

---

## Reports

### Uncleaned (original)
- `pylint_report_original.txt`
- `flake8_report_original.txt`
- `bandit_report_original.txt`

### Cleaned
- `pylint_report.txt`
- `flake8_report.txt`
- `bandit_report.txt`

All reports are available in the repository for inspection.

---

## Setup (local)

1. Clone the repository:
```bash
git clone https://github.com/2005-Aneeshdutt/lab05-submission.git
cd lab05-submission
Create a Python virtual environment and activate it:

Linux / macOS
bash
Copy code
python3 -m venv .venv
source .venv/bin/activate
Windows (PowerShell)

powershell
Copy code
python -m venv .venv
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
Upgrade pip and install analysis tools:

bash
Copy code
python -m pip install --upgrade pip
pip install pylint flake8 bandit
Running Static Analysis
Run the following commands to regenerate the reports.

On original file
bash
Copy code
pylint inventory_system.py > pylint_report_original.txt 2>&1
flake8 inventory_system.py > flake8_report_original.txt 2>&1
bandit -r inventory_system.py -f txt -o bandit_report_original.txt
On cleaned file
bash
Copy code
pylint cleaned_inventory_system.py > pylint_report.txt 2>&1
flake8 cleaned_inventory_system.py > flake8_report.txt 2>&1
bandit -r cleaned_inventory_system.py -f txt -o bandit_report.txt
Reflection Summary
See reflection.md for full write-up.

##Key observations:
Easiest fixes: Formatting, docstrings, and unused imports.
Harder fixes: Security warnings and refactoring logic flagged by Bandit.
Future integration: Add a GitHub Actions workflow to automatically run static analysis on each push to prevent regressions
##.




