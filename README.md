# Cars in Movies: Product Placement Research
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

* If time allows, test for discernable differences among different film characteristics, such as for film genres, directors, awards and accolades, or rating on Rotten Tomatoes.

### Assumptions
* Cars that have been have been renamed or succeeded were researched and had related data consolidated, removed, and/or recategorized.  For example, the Toyota86 and Subura BRZ, a collaborative effort between two car makers, have unique sales data.  However, the Scion FR-S is considered the same vehicle from a sales figure perspective, and so the Toyota and Scion occupy one row of data.  Research and ad hoc considerations were given for each brand with particular histories and naming conventions, in order to produce a clean, accurate record of all sales data available for free.
* Cars that have a "family" of variants over the years have been consolidated into a single row for that vehicle family.  Some examples include combining all Toyota Prius or Volkswagen Golf sales as one row for their group of variants.  This had been done already for most vehicles (e.g. Toyota RAV4 is one row of data for all RAV4 sales), but for the designs of this research project it was necessary to consolidate further.  The purpose here is for situations when a Toyota Prius is on screen, the assumption is that, if there is an observable effect on sale, the mere presence of the Prius, regardless of variant, is enough.  To support this assumption is the observation that information about the variant is not clear in films, simply the general make and model of the vehicle.  Therefore, if there is an impact from being in the film, the analysis should focus on what information is available to the film viewer, and not extraneous details.  There are certain exceptions to this assumption, such as when the variant has a distinct characterstic that makes it different from other vehicle families.  For example, a Ford Explorer and Ford Explorer Police Interceptor may be similar to a degree, but they are actually distinct vehicles with their own respective customer base.  As such, those two cars are counted separately from each other.

### Limitations
* No considerations or data for other marketing tactics used to promote each vehicle.
* Since we are judging impact on sales through the % change on the year prior, cars in their first production year are excluded from the analysis.  Perhaps being in the movie had an impact on a car's first year; there would be no way of observing that effect here.
* Sometimes, a big production film will feature a "made for movie," fictitious vehicle with a real brand presented (e.g. futuristic sci-fi films with Audi branded flying cars).  While this is clearly an example of product placement marketing, there is not enough data in this study to measure this effect along with the rest.  As a result, the narrow focus of this project may present a precise picture of relationship, the accuracy of such findings is in question.  More research and more data is necessary.
* Since monthly data was not as available for all cars as annual data was, this study is unable to do a more granular comparison of sales data over time.  Of course, this would up to twelve times more sales data available, for most vehicles.

### Summary Analysis