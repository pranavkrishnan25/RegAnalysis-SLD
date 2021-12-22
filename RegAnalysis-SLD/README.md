# Stemanities_Submission_Code

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
