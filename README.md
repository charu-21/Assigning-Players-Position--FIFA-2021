# Assigning Player Positions in FIFA 2021 with the aid of Supervised Learning !!

## Table of Contents
- Introduction
- Data Description
- Exploratory Data Analysis
- Balancing the data(SMOTE) & Player Classification
- Modeling Phase
- Results
- Conclusions

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
 - For instance Player 51 plays in 3 positions (CAM,CF,ST). CF & ST are categorised under Attackers whereas CAM as Midfielders. So Player 51 should be categorised as Attacker as it is repeated twice.
