# Cars in Movies: Product Placement Research
Exploring data on cars featured in high grossing films to research the effectiveness of product placement marketing.

Hypothesis: Cars with a 3+ star rating in films represent a higher proportion of cars with an increase in sales from the prior year than either cars with less than three stars in films or cars not in films at all.

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

For each given year, questions answered for four comparative categories:

        A: cars in films with significant on screen presence (i.e., >= 3 stars)
            - subdivided into top and lower 50 films that year.
        B: cars in films with little to no significant on screen presence (< 3 stars)
            - subdivided into top and lower 50 films that year.
        C: total cars in films, regardless of screen presence
            - subdivided into top and lower 50 films that year.
        D: total cars

* How many have a positive versus negative % change on the year before, for each category total (A, B, C, D)?  By how much change?
* How many cars in films (A, B, C) had a positive % change out of all cars with a positive % change (C)?  By how much change?
* How many cars in films (A, B, C) had a negative % change out of all cars with a negative % change (C)?  By how much change?

* Using Pandas and SciPy to explore correlations between sales or % change with and of the four movie characteristics: Strongest Plot Rank, Count of High Plot Appearances, Count of Low Plot Appearances, or Total Appearances

### Assumptions
* Cars that have been have been renamed or succeeded were researched and had related data consolidated, removed, and/or recategorized.  An example of this is the Mercedes M-Class, which had a particular history of renaming for legal and internal reasons, and the Mercedes GLE-Class.  For all intents and purposes, they are represented as the same vehicle in this analysis.  For a different kind of example, consider the Toyota86 and Subura BRZ, a collaborative effort between two car makers.  Despite collaborating, the two cars are distinct in certain ways, and have unique sales data.  However, the Scion FR-S, another vehicle born of said collaboration, is considered the same vehicle as the Toyota86 (Toyota also owned and operated Scion) from a sales figure perspective, and so the Toyota and Scion occupy one row of data.  The alternative would be to erroneously count the same vehicle twice.  Research and ad hoc considerations were given for each brand with particular histories and naming conventions, in order to produce a clean, complete and accurate record of all sales data (available for free).
* Cars that have a "family" of variants over the years have been consolidated into a single row for that vehicle family.  This was also done to prevent duplicates (from the perspective of this study) in the counting process.  Some examples include combining all Toyota Prius or Volkswagen Golf sales as a single row for their group of variants.  This had already been done for most vehicles (e.g. Toyota RAV4 is one row of data for all RAV4 sales, regardless of variant or model year), but for the designs of this research project it was necessary to consolidate further.  For instance, consolidation was used to handle situations when a Toyota Prius is on screen.  The assumption is that, if there is any observable effect on sales, the mere presence of a Prius, regardless of variant, is qualification enough.  The raw sales data collected had already excluded like information, such as the year of the car's production, from the final sales figures.  To further support this assumption, consider the observation that variant information is not readily apparent when a vehicle appears on screen; rather, the simple make and model of the vehicle is presented.  Therefore, if there is a sales impact to be gleemed from appearing in a film, the analysis should focus on what information is available to the film viewer in that film.  There are notable exceptions to this guideline, such as when the variant has a distinct characteristic that makes it wholly different from other vehicles or families.  A Ford Explorer and Ford Explorer Police Interceptor may be similar to a high degree, for example, but they are actually distinct vehicles with their own respective customer base.  As such, those two cars are counted separately from each other.


### Limitations
* No considerations made for other and all marketing tactics used to promote each vehicle.
* Since we are judging impact on sales via the % change on the year prior, cars in their first production year are excluded from the analysis.  Perhaps being in the movie had an impact on a car's first year, perhaps not; potential effects are not observable in this broad approach.
* Sometimes, a top grossing film will feature a "made-for-movie," fictitious vehicle with a real auto brand represented (e.g. futuristic sci-fi films with Audi branded flying cars).  While this is clearly an instance of product placement marketing, the data for that category is incomplete and absent from the larger dataset of real, nonfictional vehicles.
* Since monthly data was not as complete for all cars as annual data was, this study is unable to do a more granular, and perhaps more accurate, examination of sales data over time.
* Many of the vehicles in this project have a longer sales history beginning before the earliest year featured, 2009, which is likely relevant to any conclusions about potential patterns.
* After looking at other research projects of a similar nature, a common metric used to measure the efficacy of product placement (besides sales) is feeback via changes in web traffic, and sentiment analysis of social media (i.e. twitter).  Such data for the entirety of the period in this analysis is not available for free.  Other common metric that are available, but not used in this analysis, include stock data and total sales data for each brand, as opposed to looking at individual vehicles here.  Including some or all of these variables could solve the limitations presented above.
* When calculating correlation coefficient for sales, % change against movie appearance details, the sample size was too small (7>n<12).
* Many cars did not have more than 7 years of data, excluding them from any correlation calculations.
* Project too large in scope, and given the selection process for finding associations in the data, any findings for one car or group of cars cannot be generalized to other cars/groups.


### Summary Analysis

* The proportion of cars with higher sales than the prior year was not significantly higher over time, for cars that with appearances in films.  This was true regardless of whether the plot presence was high or low.  The effect of films on car sales over time is not discernable here.
* Vast majority of vehicles had sample size (n<8) too small for calculating correlation, or had no meaningful association whatsoever.  A few select cars had strong associations with their sales, or % change in sales, and either the level of plot presence, the total number of appearances in films, or both.  The association with film presence was sometimes positive, sometimes negative.
    
        206 cars have sample size n>=8, out of 446 cars total.
        240 cars have a sample size too small to evaluate (n<8).
        76 cars have significant strength r value >0.5 or <-0.5, while 130 have no  significant correlation coefficient

* Given yearly sales data, this study would not being able to recommend investing in product placement in movies.  This conclusion is as much due to the limitations and weaknesses of this research project, as it is to an absence of results.
* Conclusion:  Given the number of limitations, lack of precision, and inability to generalize findings, more research would need to be done on car product placement in films.  A much better project could be designed for more meaningful findings, especially along the guidelines in the Future Ideas section.  However, such a project is not possible at this time, given lack of time and access to resources.

### Future Ideas

* Target a random, respresentative sample of vehicles on the market.
* Collect weekly sales data over a recent year; include brand sales and stock history.
* Continue using car-in-movies data to quantify plot presence, if any.
* Collect data from google analytics for changes in web traffic over the same period.
* Collect data from social media for changes in sentiment analysis over the same period.
* Look for trends between the release date of target films and forementioned metrics.
