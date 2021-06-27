# Web Scrape with Python

### What is Web Scraping?
 > a technique to automatically access and extract large amounts of information from a website, 
   which can save a huge amount of time and effort.

### Important notes about web scraping
- check the legal stuff about using the data, read the Terms and Conditions of the website.
- do not frequently and rapidly download data, as to avoid breaking the web or even getting blocked from website.

### Inspecting the Website
It important to scan and check the website for the pupose of finding  relevant pieces of code that contains our data.
then simply do the "inspect".

#### Python Code

- **librarie to use**:
   >    import requests
        import urllib.request
        import time
        from bs4 import BeautifulSoup


- **set the url to the website and access the site with our requests library**
 > url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)

- **parse the html with BeautifulSoup**
> soup = BeautifulSoup(response.text, “html.parser”)

- **locate all of our <a> tags** 
> soup.findAll('a')

-**extract the actual link**
> one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]

> download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])

> time.sleep(1)
