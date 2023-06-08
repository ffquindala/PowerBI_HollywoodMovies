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
