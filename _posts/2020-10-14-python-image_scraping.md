---
layout: post
title: "Python Study: Imgage Scrapping(Crawling) from web"
categories:
  - Python study
tags:
  - python
  - image scrapping
  - web scrapping
  - crawling
  - web crawling
---

###1. Setting Pip(Python install package)
  need to set pips below
	- dload
	- selenium
	- bs4 (beautifulsoup4)

###2. Web crawling code

```

import dload
from bs4 import BeautifulSoup
from selenium import webdriver
import time

driver = webdriver.Chrome('chromedriver') # Path of web driver file
driver.get("#") # Enter the web page at '#' where you are going to scrap images
time.sleep(5) # Giving 5 seconds delay to load the web page

req = driver.page_source # Setting the HTML as usable statement for BeautifulSoup Library

soup = BeautifulSoup(req, 'html.parser') # Variable soup contains parserble html

thumbnails = soup.select('#') # Enter copied by selector/ check the select function again

i = 1
for thumbnails in thumbnails:
     img = thumbnails['src'] # Scrapping the img src
     dload.save(img, f'Directory/{i}.jpg')	# Saving imges at the Directory folder
     i += 1



driver.quit() # Closing the browser after work is done

```