# cars_in_movies_project
Exploring data on cars featured in high grossing films to research the effectiveness of product placement marketing.

Hypothesis: cars with a 3+ star rating in films represent a higher proportion of cars with an increase in sales from the prior year than either cars with less than three stars in films or cars not in films at all.

Null Hypothesis: the increase or decrease in car sales year to year has no discernable relationship to it's presence or absence in top grossing films.

Work in progress:

### Data Sources
* Domestic yearly box office - boxofficemojo.com
* Internet Movie Car Database - IMCDb.org
* Open Movie Database API - omdbapi.com
* GoodCarBadCar - goodcarbadcar.net
* CarSalesBase - carsalesbase.com

### Data Strategry, Metrics, & Retrieval Plan
* Scrape rank and gross revenues for the top grossing films, 2010-2020 (Pandas) 
* Scrape car and star data (stars: screen time) for the top 100 grossing films each year (Beautiful Soup, Splinter)
* Collect movie details: genre, director, ratings, etc. (Python API requests)
* Scrape car sales volume data in the U.S. for the years 2010-2020 (Python requests)
* Correct and complete car sales dataset manually

### Analyze for Trends

All questions answered for each given year, for four comparative categories:

        A: cars in films with significant on screen presence (i.e., >= 3 stars)
            - subdivided into top and lower 50 films that year.
        B: cars in films with little to no significant on screen presence (< 3 stars)
            - subdivided into top and lower 50 films that year.
        C: total cars in films, regardless of screen presence
            - subdivided into top and lower 50 films that year.
        D: total cars, regardless of film presence

* How many have a positive versus negative % change on the year before, for each category total (A, B, C, D)?  By how much change?
* How many cars in films (A, B, C) had a positive % change out of all cars with a positive % change (C)?  By how much change?
* How many cars in films (A, B, C) had a negative % change out of all cars with a negative % change (C)?  By how much change?
* Out of all that year's films, how many cars in films (C) have a positive versus negative % change on the year before?  By how much change?

### Limitations

### Summary Analysis