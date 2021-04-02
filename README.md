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
* Cars that have been have been renamed or succeeded were researched and had related data consolidated, removed, and/or recategorized.  An example of this is the Mercedes M-Class, which had a particular history of renaming for legal and internal reasons, and the Mercedes GLE-Class.  For all intents and purposes, they are represented as the same vehicle in this analysis.  For a different kind of example, consider the Toyota86 and Subura BRZ, a collaborative effort between two car makers.  Despite collaborating, the two cars are distinct in certain ways, and have unique sales data.  However, the Scion FR-S, another vehicle born of said collaboration, is considered the same vehicle as the Toyota86 (Toyota also owned and operated Scion) from a sales figure perspective, and so the Toyota and Scion occupy one row of data.  The alternative would be to erroneously count the same vehicle twice.  Research and ad hoc considerations were given for each brand with particular histories and naming conventions, in order to produce a clean, complete and accurate record of all sales data (available for free).
* Cars that have a "family" of variants over the years have been consolidated into a single row for that vehicle family.  This was aslo done to prevent duplicates (from the perspective of this study) in the counting process.  Some examples include combining all Toyota Prius or Volkswagen Golf sales as a single row for their group of variants.  This had already been done for most vehicles (e.g. Toyota RAV4 is one row of data for all RAV4 sales, regardless of variant or model year), but for the designs of this research project it was necessary to consolidate further.  For instance, to handle situations when a Toyota Prius is on screen.  The assumption is that, if there is an observable effect on sales, the mere presence of a Prius, regardless of variant, is qualification enough.  The raw sales data collected already excluded like information, such as the year of the car's production, from the final sales figures.  To further support this assumption, consider the observation that variant information is not readily apparent when a vehicle appears on screen; rather, the simple make and model of the vehicle is presented.  Therefore, if there is a sales impact to be gleemed from appearing in a film, the analysis should focus on what information is available to the film viewer in that film.  There are notable exceptions to this guideline, such as when the variant has a distinct characterstic that makes it wholly different from other vehicles or families.  For example, a Ford Explorer and Ford Explorer Police Interceptor may be similar to a high degree, but they are actually distinct vehicles with their own respective customer base.  As such, those two cars are counted separately from each other.

### Limitations
* No considerations made or data available for other and all marketing tactics used to promote each vehicle.
* Since we are judging impact on sales via the % change on the year prior, cars in their first production year are excluded from the analysis.  Perhaps being in the movie had an impact on a car's first year; there would be no way of observing that effect here.
* Sometimes, a big production film will feature a "made for movie," fictitious vehicle with a real brand presented (e.g. futuristic sci-fi films with Audi branded flying cars).  While this is clearly an example of product placement marketing, the data for that category is incomplete and absent from the larger dataset of real, nonfictional vehicles.  As a result, while the narrow focus of this project may present a precise picture of relationships, the accuracy of such findings is in question.  More research and more data is necessary.
* Since monthly data was not as available for all cars as annual data was, this study is unable to do a more granular, and perhaps more accurate, comparison of sales data over time.

### Summary Analysis