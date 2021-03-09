# cars_in_movies_personal
Exploring data on cars featured in the high grossing films to research the effectiveness of product placement marketing.

Work in progress

### Data Sources
* Domestic yearly box office - boxofficemojo.com
* Internet Movie Car Database. IMCDb.org
* Open Movie Database API, omdbapi.com
* Need: movie budgets
* Need: car sales (profits, earnings, volume/units sold, pricing), automaker profits/earnings, stock prices, other data?
### Data Strategry, Metrics, & Retrieval Plan
* Scrape top grossing films 2010-2021 (Pandas) 
* Scrape car and star rating data for the top 100 grossing films each year (Beautiful Soup, Splinter)
* Scrape movie information and ratings (Python API requests)
* Rottentomatoes.com?
* Need: car data
### Final Product
* Data cleaned and transformed into multiple tables, to be inserted into an SQLite database file.  Data can be queried across tables by joining tables on movie 'Release' titles, or name of car, depending on the query.
* Many if not most of the EDA and visualizations will be done in Tableau.