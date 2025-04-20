# Ride Duration Prediction - Micron Hackathon

## Dataset
- This dataset Originally consisted of 10M record out of which we samples 1M record for our modelling task
- We used 90:5:5 split for train:val:test split

## Aim:
The goal was to predict the ride duration based on factors like vendor,pickup location, drop location, distance between them, payment type and pickup time etc

## Methodology:

### eda and Featue engineering

- We performed extensive cleaning of the dataset removing outliers for each column from each columsn and analysed each column's relationship with the duration column.
- Extensively performed feature engineering and designed new columns
- We target encoded the routes column and sine encoded the hour column so that the model understands that 11 pm and 12am are just 1 hr away
- We used tolls_amount as an indicator of the presence of tolls

## Modelling

- We Tried ANN , Regression which gave a R sqaured of 73% , Random forest which gave 79% and the Neural Network gave a R squared of 77%  but the best was saved for XG boost giving a whopping R sqaured of 80 percent
- We Then performed post modelling analysis using shap, partial dependency plots

## Results:

- The obvious factor for duration is the ride distance but we got some intresting analysis via shap which told us that route was also quite dominant
- Holidays observed a lot of traffic suprisingly
- And the pickup hour also had significant contribution
- Finally the xgboost model on the test set gave an R squared of 80.24%


