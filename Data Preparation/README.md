# Steps followed for Data Preparation
## Data Preparation and Processing:
<h2>-></h2>
Dataset 1:<br>
File name raw_data1 to raw_data21 is used to get information of each person whose test is done.  https://api.covid19india.org/documentation/csv/
<br>
All Datasets are merged to  have  per day details of each city.
<br>
<h2>-></h2>
Dataset 2:<br>
Dataset containing all the details till date like number of confirmed cases ,recovered and deceased cases per day per district.
https://api.covid19india.org/csv/latest/districts.csv

``` Columns State, District, Confirmed, Recovered, Deceased``` of the latest date are used.<br>
Date 2 Jan is used .<br>
``` Confirmed``` Column represent number of confirmed cases in that district till 2nd Jan 2021.<br>
``` Recovered``` Column represent number of recovered cases in that district till 2nd Jan 2021.<br>
```Deceased``` Column represent number of deaths in that district due to COVID-19 till 2nd Jan 2021.<br>
<br>
<h2>-></h2>
From Dataset1 having details of number of tests done per day is used to calculate maximum type of age group per district. <br>
0-25 –> Children<br>
25-60 -> Young<br>
60+ -> Senior <br>
<br> 
Senior is encoded to 0, Young to 1 and children to 3<br> 
In order to give more importance to Senior Age and comparitively less importance to children type age.<br>
```Age Bracket``` Column is added in Dataset 2 representing “maximum type of affected population in that district”

<h2>-></h2>	From Dataset1 having details of number of tests done per day is used to detect current zone of each district.
<br>Red Zone -> Most Dangerous <br>
Orange Zone<br>
Green Zone ->Least Dangerous<br>
<br>
<br>
Red Zone is encoded as 0 ,Orange as 1 and Green as 2.<br>
```Zone``` column is added in Dataset2 representing current zone of corresponding District.

<h2>-></h2>	From Dataset1 having details of number of tests done per day is used to calculate most responsible reason of virus transmission.
<br>Local or Imported<br>
Imported is encoded as 0 and Local as 1
<br>
<br>
``` Type of Transmission ``` Column is added in Dataset2 representing “most responsible type of transmission”.
<br>
<h2>-></h2>	Calculate the number of confirmed cases per 1000 people in each district, this will give the value of Population Density.
<br>
```Population Density``` Column is added in Dataset2 .
<br>
<h2>-></h2>	This Dataset  https://api.covid19india.org/csv/latest/districts.csv contains number of cases per district each day.
<br>So we will first calculate number of confirmed cases increasing per day in each district and then will take the average rate of transmission of virus  in each district.
<br>If  average rate of transmission is > 200  means rate is very high
<br>If  average rate of transmission <=200 and >50 means rate if high
<br>If  average rate of transmission <=50 means rate is normal.
<br>Very high encoded as 0,high as 1, normal as 2
<br>
<br>
```Transmission rate``` column is added in Dataset2 .
<br>
<h2>-></h2>	 This Dataset  https://api.covid19india.org/csv/latest/districts.csv contains number of cases per district each day.<br>
So we will first calculate number of Deceased cases increasing per day in each district and then will take the average deceased rate in each district.<br>
Deceased Rate value is kept as average deceased rate in order to give more importance to this feature.<br>
<br>
```Deceased Rate``` column is added in Database2.<br>
<br>
<br>
** Column Names in Final Dataset:**<br>
``` **‘State', 'District', 'Confirmed', 'Recovered', 'Deceased', 'Zone', 'Age Bracket',  'Transmission Type', 'Population Density', 'Transmission rate',  'Deceased Rate'** ```               


