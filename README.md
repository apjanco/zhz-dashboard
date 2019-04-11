# dashboard

![](https://github.com/apjanco/dashboard/raw/master/Screen%20Shot%202019-04-11%20at%202.57.13%20PM.png)

This is a work in progress.  The end goal is a research dashboard that will help a researcher who studies Russian literary journals that feature poetry, essays and other writing. In the Soviet period, journals were the most affordable way to stay connected with contemporary culture and print runs were often over a million copies per issue. Solzhenitysn was first published in a thick journal.

There is a web-site in Russia called [Journal Room](http://magazines.russ.ru/) (Zhurnalnyi zal') that has the full text of many thick journals. They recently posted that the site will no longer be updated. It is quite likely that the site will go offline in the near future.  The current dataset is compsed of 76,296 texts that I scraped from Journal Room.  Using beautifulSoup, I traversed the table of contents for each journal issue to record a text's author, title, genre, journal, year, and the full text of the piece.  I am only missing full text for 6,764 of the entries.  For current purposes, I creates a csv file of the text metadata, which can be downloaded [here](https://haverford.box.com/shared/static/jwp9pd68ffl7tneh9hjob943ikcqg6x4.csv). 

The current dashboard was create with Dash, which serves the plotly Python library using Flask.  I have included app.py which will run locally with dash and pandas.  I am currently working on serving the application with nginx and uWsgi.  I have also experimented with a Django app for adding Dash apps to Django projects.  I hope to have these working soon.  

