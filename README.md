# RegAnalysis-SLD
A Regression Analysis of the probability of a recession and student loan debt utilizing data between 1993-2019

Over 44.7 million Americans carry student loan debt, with the total amount valued at approximately $1.31 trillion (Quarterly Report, 2019). Ergo, consumer spending, a factor of GDP, is stifled and negatively impacts the economy (Frizell, 2014, p. 22). This study examined the relationship between student loan debt and the probability of a recession in the near future, as well as the effects of proposed student loan forgiveness policies through the use of a created model. The Federal Reserve Bank of St. Louis’s website (FRED) was used to extract data regarding total GDP per quarter and student loan debt per quarter ("Federal Reserve Economic Data," 2019). Through the combination of the student loan debt per quarter and total GDP per quarter datasets, the percentage of total GDP composed of student loan debt per quarter was calculated and fitted to a logistic curve. Future quarterly values for total GDP and the percentage of total GDP composed by student loan debt per quarter were found through Long Short Term Models and Euler’s Method, respectively. Through the creation of a probability of recession index, the probability of recession per quarter was compared to the percentage of total GDP composed by student loan debt per quarter to construct an exponential regression model. Utilizing a primarily quantitative method of analysis, the percentage of total GDP composed by student loan debt per quarter was found to be strongly associated[p < 1.26696* 10-8]with the probability of recession per quarter(p(R)), with the p(R) tending to peak as the percentage of total GDP composed of student loan debt per quarter strayed away from the carrying capacity of the logistic curve. Inputting the student loan debt forgiveness policies of potential congressional bills proposed by lawmakers found that eliminating 49.7 % and 36.7% of student loan debt would reduce the recession probabilities to be 1.73545*10-29% and 9.74474*10-25%, respectively.

#### train.ipynb

-   Trains an LSTM model to predict GDP for a set number of quarters.
-   Save the LSTM model to ./models/final_model.h5

#### predict.ipynb

-   Loads the saved LSTM model from ./models/final_model.h5
-   Predicts GDP for 2019 Q4 to 2021 Q2
-   Saves predicted GDP data to ./final_gdp_pct.csv

#### recession probability.ipynb

-   Uses the method described in [Chauvet and Hamilton (2005)](http://dss.ucsd.edu/~jhamilto/chauvet_hamilton_may_05.pdf) to find probability of recession occuring for a quarter based on that quarter's gdp growth.
-   Uses data from ./final_gdp_pct.csv to calculate probability of recession for 2019 Q4 to 2021 Q2.
-   Saves predicted recession probabilities data to ./final_rec_prob.csv

#### student loans regression.ipynb

-   fits a logistic curve to 1993-2008 data, and then 2009-2019 data.
-   Uses Eulers Method to predict student loans over gdp for 2020.
-   Conducts correlation and exponential regression between 2008 student loan over gdp and recession probabilities, and then 2020 student loan over gdp and recession probabilities.
-   Uses the 2020 exponential regression model to predict recession probabilities for 2020 if either Elizabeth Warren's or Pete Buttigieg's student loan debt forgiveness policies are applied.
