# Detroit civic participation Project
- Geoff Perrin 3-30-22

### Civic Participation Score:
https://public.tableau.com/app/profile/g3201/viz/civic_participation_regression_dashboard_2/CivicParticipationScoreDashboard

This score is the sum of the zscores of % of population 5 and above fully vaccinated, % of population that voted in November 2020 election, and % "Total Self Response" to 2020 Census (from the "2020 Census Response Rate by Tract.xlsx" file), with all 2020 census tracts in Detroit as the cohort.

### Civic Participation Regression: 
https://public.tableau.com/app/profile/g3201/viz/civic_participation_regression_dashboard/CivicParticipationRegression

These are the residuals (i.e. the difference between the predicted civic participation score and the actual participation score) for a regression predicting civic participation score controlling for population density (from 2020 census), % black population (from 2020 census), and mean household income (from 2019 ACS). The goal here is to look at areas of the city that have high (or low) residual values - a high residual value would signify that for a given tracts' income, % black, and population density, the civic participation is much higher than the regression model would have thought. In other words, there must be something else going on (block club, strong community ties, successful outreach from the city and relationship with the city), and that might be worth investigating further. 
 
Things to note:
1. Northwest part of the city has a very high civic participation rate, and high residuals, meaning that even controlling for income / population density / % black, the northwestern census tracts 'hit above their weight' for civic participation.
2. Tract 9853 is the small tract in between downtown and southwest Detroit and has a high civic participation score mostly driven by its 100% vaccination rate - due to the small population size, this could be true, but this could be due to a high error bar associated with tracts with smaller populations.
3. Tract 5327 near Virginia Park was a tract of interest that the group picked out, as it is a lower civic participation tract surrounded by high civic participation - the regression model picks this out as one that should have a higher civic participation (0.333 predicted) but the actual (-2.5) is much lower. Interesting to maybe take a look at what else is going on in that tract.
4. Tract 5064 is the tract with one of the lowest residuals, meaning the difference between the predicted (0.594) and actual (-4.16) was one of the greatest - this is likely due to the presence of the Detroit Detention Center between Nevada and Davison skewing the results.
5. Southwest Detroit has low scores and low residuals, meaning the model predicted that those tracts would have much higher civic participation scores than they actually did.


### Data Sources:
1. All Doors FINAL Redacted 11-1-21.csv
- door knocking done by the city, given to me by Steve Mintline

2. 2020 Census Response Rate by Tract (2).xlsx - decennialrr2020 (1).csv
- I think taken from department of health, given to me by Steve Mintline

3. Vaccine Coverage by Census Tract as of 11.30.2021.xlsx
- these census numbers are from 2019 ACS - Steve M will give updated data that is 2020 census these are using CT10s

4. November 2020 General List of Voters.xlsx
- came from the city, don't know exact source

5. DECENNIALSF12010.P1_data_with_overlays_2021-12-05T220113.csv
- total population, from census: https://data.census.gov/cedsci/all?g=0500000US26163%241400000&y=2010&d=DEC%20Summary%20File%201

6. ACSST5Y2019.S1902_data_with_overlays_2021-12-05T222015.csv
- income / housing units, from census: https://data.census.gov/cedsci/all?g=0500000US26163%241400000&y=2010&d=DEC%20Summary%20File%201

7. ACSDT5Y2019.B05003_2022-01-25T195654/ACSDT5Y2019.B05003_data_with_overlays_2022-01-25T195636.csv
- citizenship status, from census (needed for the denominator of # of people who voted in november 2020): table B05003 (link was changed around recently)

8. DECENNIALPL2020.P1_data_with_overlays_2021-12-08T181156.csv
- pop black / white, from census: https://data.census.gov/cedsci/table?q=percent%20black&g=0500000US26163%241400000&y=2019&d=ACS%205-Year%20Estimates%20Data%20Profiles

9. ACSST5Y2019.S0101_2022-02-08T213209/ACSST5Y2019.S0101_data_with_overlays_2022-02-08T213200.csv
- Age 2019 ACS, ACS census: https://data.census.gov/cedsci/table?q=Age%20and%20Sex&t=Population%20Total%3APopulations%20and%20People&g=0500000US26163%241400000&tid=ACSST5Y2019.S0101
