# Create-a-web-scraper-that-extracts-information-from-a-website
import requests
from bs4 import BeautifulSoup

def scrape_website(url):
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')
    # Extract data from the website here
    # Example: Extract all the links on the page
    links = soup.find_all('a')
    for link in links:
        print(link.get('href'))

url = input("Enter website URL: ")
scrape_website(url)
