# Scrapethat

Scrapethat makes your python scraping codes faster and more readable

## Installation

You can install your package using pip:

```bash
pip install scrapethat
```

## Functions

```python

from bs4 import BeautifulSoup
import requests
import pandas as pd
import cloudscraper

def read_html(link):
    response = requests.get(link)
    return (BeautifulSoup(response.text, 'html.parser'))


def read_cloud(link):
    scraper = cloudscraper.create_scraper()
    response = scraper.get(link)
    return (BeautifulSoup(response.text, 'html.parser'))


def get_texts(link_nodes):
    return ([x.text for x in link_nodes])


def strip_texts(my_texts):
    return ([x.strip() for x in my_texts])


def get_links(link_nodes):
    return ([x['href'] for x in link_nodes])


def paste0(base_link, numbers):
    return ([f'{base_link}{s}' for s in numbers])


def fromjson(link):
    response = requests.get(link)
    return (response.json())

```