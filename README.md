# Homes_Sold
Scrape, store, and analyze housing data from Zillow in a ipython notebook

Run this file to scrape, store, and analyze sold homes in a specific area of interest. By default, this code is set up to run for `forked-river-nj` (my hometown). To change this, set the `city` variable to the area of interest found in the zillow url. For example, Los Angeles inside the zillow url is https://www.zillow.com/los-angeles-ca/ so you would set the `city` variable to "los-angeles-ca". 

Once run, the code will try to grab as much sold home data from that area as possible and store it into a csv named as `city`+`today's date`. Zillow limits its results to 20 pages per search query. To grab as much data as possible, the script queries for all possible bed + bath combos (2 Bed 1 Bath, 2 Bed 2 Bath etc.) and then paginates through the 20 pages of results for each. The data is then cleaned and stored in a csv. 

To analyze the data, all csvs across all dates for the `city` variable are read, merged, and de-duplicated. This allows as much data to be stored and used in analysis as possible; if you run this across days, weeks or months, all data will be stored in the csvs and used in the analysis. Once merged, price per square foot is calculated and a plot showing all data points and an EMA of price per square foot over time is show.


![image](https://user-images.githubusercontent.com/46106765/173243683-2144c1a7-28e4-4d0e-b144-020c455eb195.png)

## future plans ##
* Scrape the thumbnail image of the house
* Format the hover on the plotly chart to include all information about the house and the homes thumbnail image
