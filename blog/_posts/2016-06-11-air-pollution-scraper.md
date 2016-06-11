---
layout: post
title: Scraper for Danish Air-Pollution Monitoring System 
excerpt: "The air-pollution monitoring systems installed in major cities in Denmark."
modified: 2016-06-11
category: blog
tags: [python, projects]
---

**Requirements**: Python 3+ and BeautifulSoup 4.

Aarhus University along with the DCE-National Center for Environment and Energy have multiple air-pollution monitoring systems in the major cities of Denmark. These measure he air-quality on major roads and background values. All of the measured data is found <a href='http://www2.dmu.dk/atmosphericenvironment/byer/forside.htm'>online</a> for everyone to see along with some very small graphs. These can be seen here

As I wanted to use the dataset available online, I quickly whipped up a script to scrape the values and give me a CSV. Additionally, I wanted to have the values converted from the standard <a href='http://www2.dmu.dk/AtmosphericEnvironment/Expost/database/docs/PPM_conversion.pdf'>microgram per cubic meter to parts per billion as well</a> using the computation specified in the link. 

The script will on use, scrape the link, create two CSV files: one with unit converted values and the other as raw. The gist of the script is embedded below.

<script src="https://gist.github.com/vignkri/db62274e39ee1b76753ae0a28cdfd167.js"></script>
