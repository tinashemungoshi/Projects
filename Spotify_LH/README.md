Personal Listening History — JSON to CSV pipeline

This repository contains a small pipeline to convert Spotify streaming-history JSON files (in `Source Data/`) into CSV files (in `Transformed Data/`).

What I added
- `ETL/pipeline.py` — main script. Uses only Python stdlib.

How to run (PowerShell)

# Run with defaults (looks for ../Source Data and writes ../Transformed Data)
python ETL\pipeline.py

# Run with explicit absolute paths and create combined CSV
python ETL\pipeline.py --source "C:\Users\tinas\OneDrive\Desktop\TM\Projects\Python\Personal Listening History\Source Data" --out "C:\Users\tinas\OneDrive\Desktop\TM\Projects\Python\Personal Listening History\Transformed Data" --combine

# Want more logging
python ETL\pipeline.py --verbose

Outputs
- A combined file `combined_streaming_history.csv` is written to `Transformed Data/`.
- `--combine` is retained as a compatibility flag for existing commands; the combined output is always produced.

Notes & next steps
- The script attempts to preserve column order based on first-seen keys.
- Non-primitive JSON values (lists, dicts) are JSON-encoded into the CSV cells.
- If you want to add filtering, column selection, or use pandas for richer parsing, I can add that next.
