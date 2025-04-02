## Web Scraping Books Example

This script scrapes the first five book titles from [Books to Scrape](http://books.toscrape.com/) using Python.

### Prerequisites

Make sure you have the following libraries installed:

```bash
pip install requests beautifulsoup4
```

### Code

```python
import requests
from bs4 import BeautifulSoup

# Step 1: Get the webpage
url = "http://books.toscrape.com/"
response = requests.get(url)

# Step 2: Parse the HTML
soup = BeautifulSoup(response.text, "html.parser")

# Step 3: Find all book titles (first 5 only)
books = soup.find_all("h3")[:5]  # Gets first 5 books

# Step 4: Print results
print("--- Book Titles ---")
for i, book in enumerate(books, 1):
    print(f"{i}. {book.a['title']}")
```

### Usage

Run the script using:

```bash
python script.py
