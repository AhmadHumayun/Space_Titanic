# Space_Titanic
## Overview
  Space Titanic is a dataset and a competition is available on Kaggle.It contains around 13000 rows and have 14 columns(variables) and its **Target** variable is **Transported** I-e end result is finding if the person is transported to other dimension or not.

## Cleaning NULL Values
  Checked null values in luxury amenities while cryosleep is true because when cryosleep is true luxury amenities should be zero,there were NULL values so i changeed null           values to zero.
  As there were NULL values in CryoSleep for when luxury amenties like RoomService,FoodCourt,ShoppingMall,Spa,VRDeck were zero, it indicated that for them CryoSleep would have       been true, so i changed CryoSleep from NULL to True when RoomService,FoodCourt,ShoppingMall,Spa,VRDeck were zero.
  And i checked CryoSleep NULL values for when luxury amenties like RoomService,FoodCourt,ShoppingMall,Spa,VRDeck had **either of them greater than zero** it indicated that         they were **not in CryoSleep** I-e CryoSleep would be False for them so i changed it to **False** from NULL when either of RoomService,FoodCourt,ShoppingMall,Spa,VRDeck **was     greater than zero**
  Now by checking CryoSleep null values there were 11 remaining null Values and w.r.t luxury amenities like RoomService,FoodCourt,ShoppingMall,Spa,VRDeck **either of them was       NULL while others are zero** so by logic i went with **making null luxury amenity zero** as other four luxury amenity were zero and then **made Cryosleep True** as all luxury     amenities got zero.
  Then i filled the null values of numeric variables, Age,RoomService,Spa,FoodCourt,ShoppingMall,VRDeck by its median.
  Then i added spending column which is total of luxury amenities.
  Checked **VIP** null values w.r.t HomePlanet **Earth** and spending
  There were total 115 VIP null values for HomePlanet **Earth** and among known VIP values there is **zero** VIP true for **Earth**  and among 115, 49 had 0 spending so i made VIP   False for them and among remaining 66, 64 were less than mean of **spending** so i also made VIP False for all null where HomePlanet was Earth.
  Checked **VIP** null values w.r.t HomePlanet **Europa** and spending
  There were 42 VIP null values for HomePlanet Europa and among them 5 had spending value less than spending mean(2500) and were closer to 2000 so i made VIP true for all where     HomePlanet was **Europa**
  Checked VIP null values w.r.t HomePlanet **Mars** and spending
  There were 43 VIP null values for HomePlanet Mars and among them 24 had spending value **zero** so to make things simple i made VIP null values False for when Spending were zero   and remaining true
  There were 3 remaining VIP null as there Homeplanet was null so i amde them False as there spending were less than mean spending
  Then i had NULL values in categorical variables i had few options to deal with that, i choose 2 methods I-e first drop all NULL values and second replace NULL values with new     dummy value.
