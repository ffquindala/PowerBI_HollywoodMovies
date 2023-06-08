# Power BI Solution Development "Hollywood Movies" 
## Dashboards Deployment Link : 

## Project Goal

This tutorial continues with the Self-Service (SS) aspects of the Business Intelligence, through
a complete Business Intelligence solution, to be developed from ‘scratch’ (from zero) and entirely
within the Power BI Desktop environment. 

## Business Needs

You’re an executive in an important and prestigious Hollywood movie studio, responsible for the newly created “data scientist and market analysis” role.
The studio’s CEO wants you to prepare a wayfor the studio to study movie sales (and ticket volume) for the American market over the last few years, and how COVID
has impacted (is still impacting?...) cinema attendance.
In two days’ time, you have to sit down with the CEO and her assessors andhave a way of dynamically “slicing and dicing” the box office (market) numbers for the biggest blockbusters
of the last 6 years (from 2022back to 2017).
You’re thinking it may be time to fire up Power BI Desktop.

## Data Sources

o https://www.the-numbers.com/ main page; note the menu bar at the top

o https://www.the-numbers.com/market/  “Box Office” meny entry and choose
“Theatrical Market” to get here – see the Annual Ticket Sales table, where each row
represents a *Year*.

o https://www.the-numbers.com/market/2022/summary by clicking on a specific
year (in this case, 2022), we can get to a summary page for each year; we are
particularly interested in the “Top Grossing Movies of 2022” table, a little further
down the page.

o https://www.the-numbers.com/market/2022/top-grossing-movies by clicking on
the “see complete chart” link at the bottom of the above summary table, we get to
this page, which will be the basis of our ETL.

## ETL Development

## Developing the Dim Movie ETL (Movie dimension)
The basic idea behind the Movie dimension is that we will ‘scrape’ the “The Numbers” website,
obtaining the table of Top Grossing movies from each year, so that we can then consolidate this list
and keep the major movie attributes in our Movies dimension.

At this stage, and because our time is limited, we will be keeping a very short list of attributes for this
dimension: movie name and release date (movie name will also play the role of ID).

We will be showing how to develop a parameter within Power BI, for the YEAR part of the URL address
to the page, so that we can develop a function-based query and have a very simple way of choosing
the year we are interested in, and get those values retrieved through Power BI.

## Developing the Dim Date ETL (Date dimension)

The basic idea behind the Date dimension is that we will develop the entire dimension from within
Power Query, generating all of the required dates as necessary, and then developing all the additional
attributes.

However, before developing the Date dimension, we must work out what range of dates we require –
and that range depends directly on our facts (which dates we require for each of the fact transaction
coming into our model).

In this case, our transaction is revenue and theaters across the 201 7-2022 period.
However, we have to make some business decisions due to movies that are released in a specific
year earning revenue across different years. We will consider all dates from start of the year in 201 7,
to the end of the year in 2022 - we will ignore revenue earned in 2023, from movies released late in

## Developing the Dim Distributor ETL (Distributor dimension)

The basic idea behind the Distributor dimension is to show you how to unpivot a data table, to be
imported from Excel. All of the distributor data has been gathered from the same website as before
(The Numbers), but it has been put into an Excel file, to be easier to load and to demonstrate pivot
techniques inside Power Query.

##Developing the Dim Genre ETL (Genre dimension)

The basic idea behind the Genre dimension is that it represents the different types of cinema genres
that Hollywood studios have been investing in, over the years: comedy, horror, drama, musical, etc.
We have a list of movie genres in a Comma Separated File (.csv), which is a very typical file format
for data exchange – especially for information exported between different information systems.

## Developing the Dim Country ETL (Production Country dimension)

The basic idea behind the Production Country dimension is that it represents the different production
countries involved during the making (“shooting”) of the movie. It will also allow us to get further
practice in ‘transforming’ some ill-shaped, awkward data into a proper, canonical dimension table.

We have been provided with the information about the different production countries from a fellow
studio executive; however, as we’ll see, the data has more detail than we require, and will need to be
refined into shape.

## Developing the Fact Table ETL (Loading the Measures)

Having loaded all of our different dimensions (recall that we are developing a simple Star Schema
model, with 5 dimensions), it is now time to load the transactions – in other words, time to load our
Fact table.

The three different measures we have decided to load into our model concern Gross Revenue (as in
cinema ticket sales, before discounting costs), Number of Theaters (cinemas) that are showing the
specific movie and the sequential day number (index) that the movie has been screening since release
day – in other words, a non-additive measure that provides a cumulative count of how many days the
movie has been out in theaters. We can get these numbers from the same website we have been
using so far – for each movie, there is a box office section that displays these three numbers for each
day the movie was being screened in at least 1 theater across the United States.

We can actually employ Power Query to get these numbers for us, but it takes quite a while, as it has
to ‘scrape’ a different page for each of the almost 300 movies we have. Therefore, and so as to save
time, we have provided an Excel file that already has more than 25.000 rows of daily revenue and
theater figures for the years 201 7 to 2022.

## Dashboards Development
## Movies Sales Trends

![image](https://github.com/ffquindala/PowerBI_HollywoodMovies/assets/80399273/024b627e-30d6-445a-abb8-03520ba19457)

## Avarage Sales by Theather

![image](https://github.com/ffquindala/PowerBI_HollywoodMovies/assets/80399273/171777e8-3d99-49ae-8340-a3335ffea764)

## CEO Dashbord

![image](https://github.com/ffquindala/PowerBI_HollywoodMovies/assets/80399273/b73ff44f-5cbd-42cc-9306-f6a0e6d9d9ae)


