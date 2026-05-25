# Data

This directory is reserved for project data organization.

## Current Source Dataset

The original Excel file is currently kept at the repository root:

- `08. Analisando o engajamento no Instagram.xlsx`

It was not moved or modified in this organization pass because the existing notebooks read it by filename from the repository root.

## Intended Layout

- `data/raw/`: raw, immutable source files.
- `data/processed/`: derived files generated from analysis steps.

Do not commit sensitive data, credentials, private exports, or files containing personal information. If a future task moves the existing Excel file into `data/raw/`, update notebook paths in the same review and verify that analytical conclusions remain unchanged.
