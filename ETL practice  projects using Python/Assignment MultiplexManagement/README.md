
# Movie Data Scraper

This Python script scrapes data from a web page, filters the top 25 movies from the 2000s, 
and stores the data in both a CSV file and an SQLite database.

## Features
- Scrapes movie data from a webpage using BeautifulSoup.
- Filters movies released in the 2000s.
- Saves the top 25 movies to a CSV file.
- Stores the data in an SQLite database.

## Requirements
- Python 3.x
- `requests` library
- `pandas` library
- `sqlite3` (part of Python standard library)
- `beautifulsoup4` library

## Installation

1. Clone this repository or download the script.
2. Install the required libraries using pip:
   ```bash
   pip install requests pandas beautifulsoup4
   ```

## Usage

1. Ensure that the script is updated with the correct URL for scraping.
2. Run the script:
   ```bash
   python script_name.py
   ```
3. The output will include:
   - A CSV file named `top_25_films.csv`.
   - An SQLite database named `Movies.db` containing a table `Top_25`.

## Code Details

- **URL Scraped**: The script scrapes data from the URL archived via Wayback Machine:
  [Archived URL](https://web.archive.org/web/20230902185655/https://en.everybodywiki.com/100_Most_Highly-Ranked_Films)
- **Data Columns**:
  - `Film`: Name of the movie.
  - `Year`: Release year.
  - `Rotten Tomatoes`: Rotten Tomatoes score.

## Output

- **CSV File**: Contains the top 25 movies from the 2000s.
- **SQLite Database**: Stores the same data in a table called `Top_25`.

## Notes

- Ensure the URL remains valid. If the data source changes, update the script accordingly.
- Errors in scraping specific rows are handled gracefully and logged.

## License

This project is licensed under the MIT License.
