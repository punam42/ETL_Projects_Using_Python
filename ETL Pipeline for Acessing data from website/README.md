
# ETL Operations on Country-GDP Data

This project performs **Extract, Transform, Load (ETL)** operations on data related to countries and their GDP from a specified webpage. It extracts GDP data, transforms it into a usable format, and loads it into both a CSV file and an SQLite database for further analysis.

---

## Features

- Extracts data from a Wikipedia page using web scraping (`BeautifulSoup` and `requests`).
- Transforms GDP values from USD (Millions) to USD (Billions), rounding to two decimal places.
- Loads the processed data into:
  - A CSV file.
  - An SQLite database table.
- Logs the progress of ETL operations into a log file.
- Executes SQL queries on the database table to filter and analyze data.

---

## Requirements

### Libraries
The following Python libraries are required:
- `bs4` (BeautifulSoup)
- `requests`
- `pandas`
- `numpy`
- `sqlite3` (Standard library)
- `datetime` (Standard library)

---

## Usage

1. **Set up the environment**: Ensure all required libraries are installed in your Python environment.
2. **Edit parameters**: Update the following parameters in the script as needed:
   - `url`: URL of the webpage to scrape GDP data.
   - `table_attribs`: Column names to extract from the webpage table.
   - `csv_path`: Path to save the resulting CSV file.
   - `db_name`: Name of the SQLite database file.
   - `table_name`: Name of the database table to create.
3. **Run the script**: Execute the script to perform the ETL operations.
4. **Analyze the data**:
   - View the data in the saved CSV file or SQLite database.
   - Modify and run SQL queries for analysis.

---

## Code Structure

### Functions

- **`extract(url, table_attribs)`**: Extracts data from the webpage and returns a DataFrame.
- **`transform(df)`**: Converts GDP values from USD (Millions) to USD (Billions).
- **`load_to_csv(df, csv_path)`**: Saves the transformed data to a CSV file.
- **`load_to_db(df, sql_connection, table_name)`**: Loads the data into an SQLite database table.
- **`run_query(query_statement, sql_connection)`**: Executes SQL queries on the database.
- **`log_progress(message)`**: Logs ETL progress messages to a log file.

### Execution Flow
1. Extract data from the webpage.
2. Transform the data.
3. Load the data into a CSV file and an SQLite database.
4. Execute SQL queries for analysis.

---

## Logs

- A log file named `etl_project_log.txt` is created to record each step of the ETL process with timestamps.

---

## Example Output

Sample SQL query:
```sql
SELECT * from Countries_by_GDP WHERE GDP_USD_billions >= 100;
```

---

## License

This project is licensed under the MIT License. You are free to use and modify the code for personal or commercial purposes.
