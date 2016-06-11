---
layout: post
title: Scraper for Danish Air-Pollution Monitoring System 
excerpt: "The air-pollution monitoring systems installed in major cities in Denmark."
modified: 2016-06-11
category: blog
tags: [python, projects]
---

**Requirements**: Python 3+ and BeautifulSoup 4.

Aarhus University along with the DCE-National Center for Environment and Energy have multiple air-pollution monitoring systems in the major cities of Denmark. These systems measure he air-quality on major roads. All of the measured data is uploaded <a href='http://www2.dmu.dk/atmosphericenvironment/byer/forside.htm'>online</a>. 

As I wanted to use this dataset, I quickly whipped up a script to scrape the values and give me a CSV that can be easily handled. To be further useful, the values, originally in $$\frac{\mu g}{m^3}$$ is also converted to $$ppb$$ according to the computation method that is hosted <a href='http://www2.dmu.dk/AtmosphericEnvironment/Expost/database/docs/PPM_conversion.pdf'>here</a> as a pdf from Aarhus University. 

The script will on use, scrape the link, create two CSV files: one with unit converted values and the other as raw. The gist of the script is embedded below.

<script src="https://gist.github.com/vignkri/db62274e39ee1b76753ae0a28cdfd167.js"></script>
