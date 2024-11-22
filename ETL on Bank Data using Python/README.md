
# Largest Banks Data Processor

This Python script extracts data about the largest banks from a webpage, transforms it into multiple currency representations, and stores it in a database and a CSV file.

## Features
- Scrapes bank data from a webpage.
- Converts market capitalization to GBP, EUR, and INR using exchange rates.
- Saves the transformed data to both a CSV file and an SQLite database.
- Logs progress of the script's execution in a log file.

## Requirements
- Python 3.x
- `requests` library
- `pandas` library
- `numpy` library
- `sqlite3` (part of Python standard library)
- `beautifulsoup4` library

## Installation

1. Clone this repository or download the script.
2. Install the required libraries using pip:
   ```bash
   pip install requests pandas numpy beautifulsoup4
   ```

## Usage

1. Ensure the exchange rate CSV file is present at the specified path (`./exchange_rate.csv`).
2. Run the script:
   ```bash
   python banks_project.py
   ```
3. Outputs:
   - A CSV file named `Largest_banks_data.csv`.
   - An SQLite database named `Banks.db` containing a table `Largest_banks`.
   - A log file `code_log.txt` documenting the script's progress.

## Code Details

- **URL Scraped**: [Archived URL](https://web.archive.org/web/20230908091635/https://en.wikipedia.org/wiki/List_of_largest_banks)
- **Data Columns**:
  - `Name`: Name of the bank.
  - `MC_USD_Billion`: Market capitalization in USD.
  - `MC_GBP_Billion`: Market capitalization in GBP.
  - `MC_EUR_Billion`: Market capitalization in EUR.
  - `MC_INR_Billion`: Market capitalization in INR.

## License

This project is licensed under the MIT License.
