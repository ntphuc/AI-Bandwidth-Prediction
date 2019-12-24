# AI-Bandwidth-Prediction

| **Title**      |Bandwidth User Prediction |
| ---------- |-------------------|
| **Team**       |Nguyễn Thiện Phúc - thienphuc0510@gmail.com <br/> Hà Quang Chuẩn - haquangchuan@gmail.com |
| **Predicting** |We will build a model to predict the bandwidth and max user for media company devided in three 3 zones (MPG-Miles Per Gallon)|
| **Data**       |Data Set including train and test with time-series format measured from 01/10/2017 to 09/03/2019 <br/> Data link : https://github.com/ntphuc/AI-Bandwidth-Prediction/blob/master/server-flow-prediction.zip|
| **Features**   | <ol> <li>update-time: the date is measured. Ex: 01-10-2017.</li> <li>zone-code: zone is measured. In this project, we have three zones.</li> <li>hour-id: the hour time in a day</li> <li>bandwidth: the bandwidth size is measured in a day</li> <li>max-user: the max-user size is measured in a day</li> <li>count-date: the date index in data-set. Ex: 01/10/2017, count-date starts from 0.</li> <li>day-of-week: the day index in week. Ex: monday is 0</li> 
Features currently available: UPDATE_TIME, HOUR_ID, ZONE_CODE.

Regarding ZONE_CODE, statistics show that there are only 3 types: zone01, zone02, zone03. They are completely separate and have no relationship with each other so we continue to divide it into 3 parts and build 3 separate models for each zone.

With the remaining 2 features about UPDATE_TIME and HOUR_ID time. To better understand the milestones flow in the data, we create a few new features from the existing features:

<li>count_date: Get the first day (October 1, 2017) of the train set as a zero milestone, until the last day in the train set (March 9, 2019) will be 524. </li>

<li>day_of_week: Denotes the day of the week. With values from 0 to 6 corresponding to the days of the week from Monday to Sunday. </li>
</ol>|
| **Models**     |<ol> 
<li>The requirement is BANDWIDTH_TOTAL and MAX_USER predictions. After statistics and plotting data, realize that BANDWIDTH_TOTAL and MAX_USER are closely related. So the team used the same predictive method for both types of labels.</li>
<li>After plotting the data according to the average, median, min and max of each day, the difference between the hours of the day and the days of the week, and the data is linear in the day. Therefore, the model is built around linear regression to solve the problem.</li> 
<li>Starting with building the model for each part as divided, first with the bandwidth of zone 1, for each day, we took the average value of that day (grouped by UPDATE_TIME and calculated mean), plotting and continuing to consider eliminating the sudden increase or decrease (the major abrupt decreases often fall on the annual lunar new year). </li> 
<li>From there we use linear regression learning (by feature count_date) to be able to predict the average value per day. Looking closely, we see that the plot has the same curve as in the quadratic equation so we use the second linear regression according to count_date. </li> 
<li>To be able to predict the exact value of each hour of the day when we know the average value of that day, we use the ratio of the average value of each hour of the week (group by day_of_week, HOUR_ID and mean) with average value per day across the entire train. Finally, using this ratio times the average daily value we find gives us all the predicted results on the test set. </li></ol>|
| **Discussion** |At the first time, we suggest the first linear regression according to count_date. But the result of prediction is not high, and then we convert to model the second linear regression. In addition, at the first time, we intent to calculate Bandwidth, User each hour by calculating the rate between average value per day across the entire train. But the result of prediction is not high, then we calculate the rate between the average value group by day_of_week per average value per day across the entire train.
| **Future**     |Applying the linear regression method into business problems (Sales, Invoice Business Plan, House Pricing Prediction).
|**References**  |[1] https://drive.google.com/open?id=11YxJVWSsxihWqQBpwaQijBdABH7yoKOn <br/> [2]https://www.aivivn.com/contests/4 <br/> [3] https://forum.machinelearningcoban.com/t/aivivn-5-bandwidth-prediction-2-1st-place-solution/5812<br/> [4] https://machinelearningcoban.com/2016/12/28/linearregression/|
| **Results**    |MLP: Testing set Mean Abs Error:  2.04 MPG <br/> Regression Tree score: 0.8772300290913486 <br/> Regression Random Forest score: 0.9084957992180025 |