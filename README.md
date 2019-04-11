# dashboard

![](https://github.com/apjanco/dashboard/raw/master/Screen%20Shot%202019-04-11%20at%202.57.13%20PM.png)

This is a work in progress.  The end goal is a research dashboard that will help a researcher who studies Russian literary journals that feature poetry, essays and other writing. In the Soviet period, journals were the most affordable way to stay connected with contemporary culture and print runs were often over a million copies per issue. Solzhenitysn was first published in a thick journal.

There is a web-site in Russia called [Journal Room](http://magazines.russ.ru/) (Zhurnalnyi zal') that has the full text of many thick journals. They recently posted that the site will no longer be updated. It is quite likely that the site will go offline in the near future.  The current dataset is compsed of 76,296 texts that I scraped from Journal Room.  Using beautifulSoup, I traversed the table of contents for each journal issue to record a text's author, title, genre, journal, year, and the full text of the piece.  I am only missing full text for 6,764 of the entries.  For current purposes, I creates a csv file of the text metadata, which can be downloaded [here](https://haverford.box.com/shared/static/jwp9pd68ffl7tneh9hjob943ikcqg6x4.csv). 

The current dashboard was created with [Dash](https://plot.ly), which serves the plotly Python library using Flask.  I have included app.py which will run locally with dash and pandas.  Just `pip install dash pandas` in your prefered virtualenv, clone the repository, `cd dashboard` and then `$ python app.py`.  I am currently working on serving the application with nginx and uWsgi.  I have also experimented with a Django app for adding Dash apps to Django projects.  I hope to have these working soon.  I have had a lot of trouble with Idyll and bqplot.      

The dashboard has three elements, a date slider, a datatable and a scatterplot.  I plan to change the date slider to select a time range.  It is currently working, but selects a time period between the minimum value and the time selected.  The table displays the raw data and can be sorted and viewed with forward and backward buttons.  I would like to add a search field if possible.  The scatterplot shows the number of total articles on the y axis and authors' names on the x axis.  The points are color coded by journal.  This makes it possible to identify clusers of authors that are all associated with a common journal.  This is a key interest for my researcher.  It is possible to zoom in on a particular cluster to see the names of the authors and the journal on hover.   

