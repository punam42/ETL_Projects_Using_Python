
# Movie Scraper: Top 50 Highly Ranked Films

This Python script scrapes the list of the **Top 50 Highly Ranked Films** from a web page using **BeautifulSoup** and **Requests**, stores the data in a SQLite database, and also saves it as a CSV file. The data includes the average rank, film name, and release year.

---

## Features

1. **Web Scraping**:
   - Scrapes the list of films from the web page on [EverybodyWiki](https://en.everybodywiki.com/100_Most_Highly-Ranked_Films) (archived version) using BeautifulSoup and Requests.

2. **Data Storage**:
   - Saves the scraped data into:
     - A CSV file (`top_50_films.csv`).
     - A SQLite database (`Movies.db`) with a table (`Top_50`).

3. **Data Columns**:
   - **Average Rank**: The rank of the film.
   - **Film**: The name of the film.
   - **Year**: The release year of the film.

4. **Database Interaction**:
   - Uses **SQLite3** to store the data in a relational database.

---

## File Structure

- **Source Files**:
  - The script fetches data from the archived web page.
- **Generated Files**:
  - `top_50_films.csv`: Stores the top 50 films in CSV format.
  - `Movies.db`: SQLite database file containing a table of the top 50 films.

---

## Requirements

Ensure you have the following libraries installed:

- **requests**: For making HTTP requests.
- **beautifulsoup4**: For parsing HTML content.
- **pandas**: For storing and processing the scraped data.
- **sqlite3**: For interacting with the SQLite database.

You can install missing libraries using `pip`:

```bash
pip install requests beautifulsoup4 pandas sqlite3
```

---

## How It Works

### 1. Scraping
- The script sends an HTTP GET request to the provided URL.
- It parses the HTML using BeautifulSoup and extracts the relevant data (average rank, film name, and year of release) from the first table of the page.

### 2. Data Storage
- **CSV Storage**: The data is saved into a CSV file (`top_50_films.csv`).
- **SQLite Database**: The data is stored in a SQLite database (`Movies.db`) in the `Top_50` table.

### 3. Output
- The final data is stored in both CSV and SQLite formats for further analysis or usage.

---

## Usage

1. **Run the Script**:
   ```bash
   python movie_scraper.py
   ```

2. **Check Outputs**:
   - View the CSV file: `top_50_films.csv`.
   - The SQLite database will be created with the file: `Movies.db` containing the `Top_50` table.

---

## Example Data (CSV)

| Average Rank | Film                  | Year |
|--------------|-----------------------|------|
| 1            | The Shawshank Redemption | 1994 |
| 2            | The Godfather          | 1972 |
| ...          | ...                   | ...  |

---

## Notes

- Ensure you have a stable internet connection for scraping the data.
- The script scrapes the top 50 films; if you want to scrape more, modify the script to handle more rows from the table.

This script can be extended for additional web scraping tasks or saving data in other formats.
