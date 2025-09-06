# Reconcile Script

A Bash script to reconcile two delimited files (CSV/TSV/pipe).  
It compares a **source file** and a **target file**, then produces detailed reports on:

- Missing keys (present in source but not in target).
- Extra keys (present in target but not in source).
- Duplicate keys in either file.
- Per-column mismatched values (with optional numeric tolerance).
- Schema differences (column count and header names).
- Summary statistics.

---

## Features

- Works with CSV, TSV, or any single-character delimiter.
- Supports **headered** files (compare by column name) or **headerless** files (compare by column index).
- Optional **numeric tolerance** for floating-point comparisons (e.g., treat `1.000` vs `1.001` as equal).
- Generates multiple report files in plain CSV/TXT format.
- Combines schema and summary into a single **overview CSV** for convenience.

---

## Requirements

- Unix-like shell (Linux, macOS, WSL, or Git Bash on Windows).
- `awk` available in your environment (installed by default on most systems).

---

## Usage

```bash
./reconcile.sh -s <source_file> -t <target_file> -k <key_columns> [-d <delimiter>] [-H 1|0]



Ex Syntax: ./reconcillation.sh -s apple_products.csv -t apple_products-Copy.csv -k Product_Name "," -H 1
