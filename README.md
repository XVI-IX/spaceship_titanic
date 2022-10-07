# Spaceship Titanic

![spaceship](/spaceship-titanic/nasa-rTZW4f02zY8-unsplash.jpg)

## Overview

Welcome to the year 2912, and we need to solve a cosmic mystery. We've received a transmission from four lightyears away and things aren't looking good.

The Spaceship Titanic was an interstellar passenger liner launched a month ago. With almost 13,000 passengers on board, the vessel set out on its maiden voyage transporting emigrants from our solar system to three newly habitable exoplanets orbiting nearby stars.

While rounding Alpha Centauri en route to its first destination—the torrid 55 Cancri E—the unwary Spaceship Titanic collided with a spacetime anomaly hidden within a dust cloud. Sadly, it met a similar fate as its namesake from 1000 years before. Though the ship stayed intact, almost half of the passengers were transported to an alternate dimension!

you are challenged to predict which passengers were transported by the anomaly using records recovered from the spaceship’s damaged computer system.

## Understanding the Data

To predict transported passengers, we need to understand the dataset

### Data Description

`PassengerId` - A unique Id for each passenger.
              Each Id takes the form gggg_pp where gggg indicates a group the passenger is travelling with and pp is their number within the group.
              People in a group are often family members, but not always.

`HomePlanet` - The planet the passenger departed from, typically their planet of permanent residence.

`CryoSleep` - Indicates whether the passenger elected to be put into suspended animation for the duration of the voyage.
            Passengers in cryosleep are confined to their cabins.

`Cabin` - The cabin number where the passenger is staying.
          Takes the form deck/num/side, where side can be either P for Port or S for Starboard.

`Destination` - The planet the passenger will be debarking to.

`Age` - The age of the passenger.

`VIP` - Whether the passenger has paid for special VIP service during the voyage.

`RoomService`, `FoodCourt`, `ShoppingMall`, `Spa`, `VRDeck` - Amount the passenger has billed at each of the Spaceship Titanic's many luxury amenities.

`Name` - The first and last names of the passenger.

`Transported` - Whether the passenger was transported to another dimension. This is the target, the column you are trying to predict.

### **Visualisations**

#### **Age**

##### **Age Distribution**

![Age Distribution](/spaceship-titanic/images/Age%20distribution.png)
From checking the distribution of ages in the dataset,

It can be observed that a majority of people on the spaceship were between the ages ~18 and 30.

##### **Age Distribution (Imputation)**

![Age Distribution (Imputation)](/spaceship-titanic/images/Age%20distribution%20(Imputation).png)
To impute the missing values in the datasets, the effects of imputing with the mean, median and mode was compared and since the imputing the missing values using the median does not affect the data distribution, it is used to impute the missing values.

##### **Age Distribution Based on Home Planet**

![Age Distribution Based on Home Planet](/spaceship-titanic/images/Age%20distribution%20based%20on%20home%20planet.png)

#### **Room Service**

##### **Room Service Distribution**

![Room Service Distribution](/spaceship-titanic/images/roomservice%20distribution.png)
Here it is observed that a lot of people did not pay for room service and very few people paid above 2000.

##### **Room Service Distribution (Imputation)**

![Room Service Distribution (Imputation)](/spaceship-titanic/images/roomservice%20distribution%20(imputation).png)
To impute the missing values in the datasets, the effects of imputing with the mean, median and mode was compared and since the imputing the missing values using the median does not affect the data distribution, it is used to impute the missing values.

##### **Total Spent on Room Services**

![Total Spent on Room Services](/spaceship-titanic/images/Total%20Spent%20on%20Room%20Services%20per%20Deck.png)
Of all the decks in the spaceship, we find that passengers in deck D spent more on room service than other decks with a majority of the spending coming from martian passengers.

The martian passengers were also the top spenders in decks G, E, and F.

Deck T however, has an almost equal amount of spending from Earth and Europian passengers with almost no spendings amongst the martians.

#### **Cryosleep**

##### **Number of People in Cryosleep based on Home Planet**

![Number of People in Cryosleep based on Home Planet](/spaceship-titanic/images/Number%20of%20People%20in%20Cryosleep%20based%20on%20Home%20Planet.png)
Passengers from Europa had more people in cryosleep while Earth has the lowest amount of people put in cryosleep.

##### **Cryosleep passenger population per side**

![Cryosleep passenger population per side](/spaceship-titanic/images/Cryosleep%20passenger%20population%20per%20side.png)
Passengers put in cryosleep on each side of the spaceship are almost equal on both sides, leading to an assumption that both sides have equal amounts of cryosleep facilities.

##### **Cryosleep population per Deck**

![Cryosleep population per Deck](/spaceship-titanic/images/Cryosleep%20population%20per%20Deck.png)
Here we notice that in deck T, there is no one put in cryosleep, this could mean that there are either no cryosleep facilites in that deck or passengers who can afford the available cryosleep facilities.

#### **VIP**

##### **Percentage of VIP passengers per Home Planet**

![Percentage of VIP passengers per Home Planet](/spaceship-titanic/images/Percentage%20of%20VIP%20passengers%20per%20Home%20Planet.png)
Earth has the least amount of vip passengers and Europa has the highest amount of vip passengers. It can however be noticed that the vip population coming from each planet did not exceed 8% percent of the total planetal population

##### **Vip population per deck**

![Vip population per deck](/spaceship-titanic/images/Vip%20population%20per%20deck.png)
Here we can solidify our hypothesis, that due to the lack of vip passengers in deck T there are no facilities.

#### **Services**

##### **Total Spent on VR-Deck per Deck**

![Total Spent on VR-Deck per Deck](/spaceship-titanic/images/Total%20Spent%20on%20VR-Deck%20per%20Deck.png)
Passengers coming from Earth in deck A spent the most on VR-Decks, and overall passengers from mars spent very little on them.

##### **Total Spent on Food Court per Deck**

![Total Spent on Food Court per Deck](/spaceship-titanic/images/Total%20Spent%20on%20Food%20Court%20per%20Deck.png)
Passengers coming from Europa in deck C spent the most in Food Courts, and overall passengers from mars spent very little on them.

##### **Total Spent on Spas per Deck**

![Total Spent on Spas per Deck](/spaceship-titanic/images/Total%20Spent%20on%20Spa%20per%20Deck.png)
Passengers coming from Earth in deck A spent the most on Spas, and overall passengers spent less on them.

#### **Transported**

#### **Transported population based on Home Planet**

![Transported population based on Home Planet](/spaceship-titanic/images/Transported%20population%20based%20on%20Home%20Planet.png)
The home planet with most transported passengers is Europa with 65.88% being transported, with Mars following up with 52.3% and Earth with the least casualities of 42.74%

#### **Transported Population per Deck**

![Transported Population per Deck](/spaceship-titanic/images/Transported%20Population%20per%20Deck.png)
Deck suffered the least casualities with 20% being transported, and decks B and C have the most casualities at 73.43% and 68.01% respectively. This could mean that the reason for the transportation is concentrated within decks B and C.

## Modeling

### LogisticRegression

`accuracy_score(y_test, log.predict(X_test))`

using the logistic regression model, the model predicted on the test set with an accuracy of 0.779.

### RandomForestClassifier

`accuracy_score(y_test, rnd_frst.predict(X_test))`
the random forest classifier model resulted in a prediction accuracy of 0.774
