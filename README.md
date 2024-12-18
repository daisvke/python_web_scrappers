# python_web_scrappers

## Web Scraper

This module implements a web scraper that recursively searches for a specified string within the content of a given base URL and all reachable links from that URL. The script utilizes the `requests` library to fetch web pages and `BeautifulSoup` from the `bs4` library to parse HTML content. 

### Key Features:
- **Recursive Scraping**: The scraper navigates through all links found on the base URL and continues to scrape linked pages unless restricted by the user.
- **Search Functionality**: It checks for the presence of a user-defined search string in the text of each page, with an option for case-insensitive searching.
- **Visited URL Tracking**: The script maintains a list of visited URLs to avoid processing the same page multiple times.
- **Skip Limit**: Users can set a limit on the number of skipped links (either due to already visited pages or bad links) before the scraper terminates.
- **Command-Line Interface**: The script accepts command-line arguments for the base URL, search string, case sensitivity, single-page mode, and skip limit.

### Usage:
```
// Display help
python web_scraper.py -h

positional arguments:
  link                  the name of the base URL to access
  search_string         the string to search

options:
  -h, --help            show this help message and exit
  -i, --case-insensitive
                        Enable case-insensitive mode
  -s, --single-page     Enable single page search mode
  -l LIMIT, --limit LIMIT
                        Number of already visiited/bad links that are allowed
                        before we terminate the search

// Run with case insensitive and single page mode
python web_scraper.py <base_URL> <search_string> -i -l <skip_limit> -s
```

## Spider

This module implements a web image scraper that recursively searches for images on a specified base URL and downloads them to a designated folder. 

### Key Features:
- **Image Downloading**: The scraper identifies and downloads images from the base URL and any linked pages, saving them to a specified local directory.
- **Search Functionality**: Users can specify a search string to filter images based on their `alt` text. The scraper can operate in case-sensitive or case-insensitive modes.
- **Recursive Scraping**: The script navigates through all links found on the base URL, continuing to scrape linked pages unless restricted by the user.
- **Visited URL Tracking**: It maintains a list of visited URLs to avoid processing the same page multiple times.
- **Skip Limit**: Users can set a limit on the number of skipped links (either due to already visited pages or bad links) before the scraper terminates.
- **Command-Line Interface**: The script accepts command-line arguments for the base URL, search string, case sensitivity, single-page mode, and skip limit.

### Usage:
```
// Display help
python spider.py -h

positional arguments:
  link                  the name of the base URL to access

options:
  -h, --help            show this help message and exit
  -r RESEARCH_STRING, --research_string RESEARCH_STRING
                        If not empty enables the string search mode
  -i, --case-insensitive
                        Enable case-insensitive mode
  -s, --single-page     Enable single page search mode
  -l LIMIT, --limit LIMIT
                        Number of already visiited/bad links that are allowed
                        before we terminate the search

// Run with case insensitive and single page mode
python web_scraper.py <base_URL> -r <search_string> -i -l <skip_limit> -s
```
