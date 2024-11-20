
# ETL Pipeline: Extract, Transform, and Load Data (Car Dataset)

This Python script implements an **ETL (Extract, Transform, Load)** pipeline for processing car-related data from multiple file formats (CSV, JSON, and XML). It extracts data, transforms it into a standardized format, and loads the results into a CSV file. Additionally, it logs the progress of the ETL process in a log file.

---

## Features

1. **File Types Supported**:
   - CSV (`*.csv`)
   - JSON (`*.json`)
   - XML (`*.xml`)

2. **Data Transformation**:
   - Rounds off car prices to two decimal places.

3. **Logging**:
   - Tracks the progress of each phase (Extraction, Transformation, and Loading) in a log file (`log_file.txt`).

4. **Output**:
   - Transformed data is saved to `transformed_data.csv`.

---

## File Structure

- **Source Files**: Place CSV, JSON, or XML files in the same directory as the script.
- **Generated Files**:
  - `log_file.txt`: Logs ETL process details with timestamps.
  - `transformed_data.csv`: Stores the transformed data.

---

## Requirements

Ensure you have the following libraries installed:

- **pandas**: For data manipulation.
- **xml.etree.ElementTree**: For XML parsing.
- **glob**: For file pattern matching.
- **datetime**: For timestamp generation.

You can install missing libraries using `pip`:

```bash
pip install pandas
```

---

## How It Works

### 1. Extraction
- Processes all `.csv`, `.json`, and `.xml` files in the current directory.
- Extracts relevant data fields: `car_model`, `year_of_manufacture`, `price`, and `fuel`.

### 2. Transformation
- Rounds car prices to two decimal places.

### 3. Loading
- Saves the transformed data to `transformed_data.csv`.

### 4. Logging
- Logs the start and end of each phase (Extraction, Transformation, Loading).
- Records messages with timestamps in `log_file.txt`.

---

## Usage

1. **Place Source Files**:
   - Ensure all your `*.csv`, `*.json`, and `*.xml` files are in the same directory as the script.

2. **Run the Script**:
   ```bash
   python etl_pipeline.py
   ```

3. **Check Outputs**:
   - View `transformed_data.csv` for the final output.
   - Open `log_file.txt` for the ETL process log.

---

## Example Log Output (`log_file.txt`)

```
2024-Nov-20-12:00:00,ETL Job Started
2024-Nov-20-12:01:00,Extract phase Started
2024-Nov-20-12:02:00,Extract phase Ended
2024-Nov-20-12:03:00,Transform phase Started
2024-Nov-20-12:04:00,Transform phase Ended
2024-Nov-20-12:05:00,Load phase Started
2024-Nov-20-12:06:00,Load phase Ended
2024-Nov-20-12:06:30,ETL Job Ended
```

---

## Code Overview

### Functions

1. **`extract_from_csv(file_to_process)`**:
   - Reads a CSV file into a pandas dataframe.

2. **`extract_from_json(file_to_process)`**:
   - Reads a JSON file (line-delimited) into a pandas dataframe.

3. **`extract_from_xml(file_to_process)`**:
   - Parses an XML file and extracts `car_model`, `year_of_manufacture`, `price`, and `fuel`.

4. **`extract()`**:
   - Consolidates extracted data from all supported file formats.

5. **`transform(data)`**:
   - Rounds the price values to two decimal places.

6. **`load_data(target_file, transformed_data)`**:
   - Writes the transformed data to a CSV file.

7. **`log_progress(message)`**:
   - Appends messages with timestamps to `log_file.txt`.

---

## Notes

- Ensure proper formatting of XML files as per the structure required for `extract_from_xml`.
- CSV and JSON files should have columns corresponding to `car_model`, `year_of_manufacture`, `price`, and `fuel`.

This script is modular and can be extended to include additional data sources or transformations.
