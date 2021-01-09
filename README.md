# Assigning Player Positions in FIFA 2021 with the aid of Supervised Learning !!

## Table of Contents
- Introduction
- Data Description
- Exploratory Data Analysis
- Balancing the data(SMOTE) & Player Classification
- Modeling Phase
- Results
- PCA


## Introduction
FIFA is a series of association football simulation video games developed and released annually by Electronic Arts under the EA Sports label. Career Mode sees the gamer take control of an already existing team, and they play matches in a standard season format against the computer. The player can make transfers, control finances and tailor pre-season matches in numerous ways. Different skills set determine the position they play on the field.

### Objective
Based on different skill set each player is known for their best positions in the respective teams. The aim is to explore whether a machine can learn and classify the players positions on the basis of player’s skill sets.

## Data Description
The dataset is acquired from Kaggle. The dataset provided include the players information for the Career Mode for FIFA 21. The data contained features like player_id,short_name, weight, age,wage, international_reputation,etc.The data consists of 106 columns and 18944 records. Our model will be predicting the player positions.

## EDA
- Dropping Unnecessary columns and missing value imputation
- Below are the observations which we have made from the data visualization done as part of the Data Understanding process.
    * The most expensive player is: Kylian Mbappé Lottin
    * The player with the highest wage is: Lionel Andrés Messi Cuccittini
    * "FC Bayern München" Club has the highest Player value of 27.7 million euros on an average.
    * "Real Madrid" Club has the highest Wage of 155.5 thousand euros paid to the player on an average.
- The 4 major categories for Football would be :
    * Attackers: ST, LW, RW, CF
    * Midfielders: CAM, LM, CM, RM, CDM
    * Defenders: LWB, RWB, LB, CB, RB
    * Goalkeepers: GK
 - Defining a Function for bucketing the positions of the players in the respective categories mentioned above. 
 - In case any player has more than 2 position, then with the help of the function we would be able to bucket the position of the player as per the maximum count of the repeated position.
 - There are more midfielders and defenders than attackers and goalkeepers.
 
 ## Balancing the data(SMOTE) & Player Classification
 - SMOTE creates synthetic observations of the minority class by:
    * Finding the k-nearest-neighbors for minority class observations (finding similar observations)
    * Randomly choosing one of the k-nearest-neighbors and using it to create a similar, but randomly tweaked, new observation.
    * Sampling Strategy used is “minority”, which means that only the class which has less number of observations would be oversampled. In our case Class 3 have been oversampled from 1460 to 4970 observations.
    
## Modeling Phase
- Splitted dataset into into random train and test subset of ratio 70:30
- Diiferent models using K-Fold Cross Validation were build, where XGB Classifier outperformed.

## Result before PCA
- XGB Classifier has improved the scoring be it Recall, Precision, F-1 or Accuracy. Using the XGB Classifier ,it can be said that model is 90.6% accurate.
- The final model was very well able to increase the Recall Score for Attackers ,Midfielders, Defenders by 1%(in comparision to Logistic regression, which was the base model). Below are the results for the same:
    * 78% Attackers were correctly classified.
    * 87% Midfielders were correctly classified
    * 94% Defenders were correctly classified.
    
## PCA
- Because of severe multicolinearity between the independent features, dimensionality reduction technique known as PCA was applied.
### Result after applying PCA
- After applying PCA we can observe that with just 27 PCA Components we were able to get 99.9% of Training Accuracy and 90.1% of Testing Accuracy.
- PCA also helped to reduce the multicolinearity which was present b/w the independent features.

