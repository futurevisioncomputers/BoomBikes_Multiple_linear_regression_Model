# BoomBikes Demand Analysis and Prediction
> Bicycle-sharing system, bike share program,[1] public bicycle scheme,[2] or public bike share (PBS) scheme,[3] is a shared transport service in which bicycles are made available for shared use to individuals on a short-term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" and return it at another dock belonging to the same system. Docks are special bike racks that lock the bike, and only release it by computer control. The user enters payment information, and the computer unlocks a bike. The user returns the bike by placing it in the dock, which locks it in place. Other systems are dockless.


## Table of Contents
* [Problem Statement](#problem-statement)
* [General Info](#general-information)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## Problem Statement
Bicycle sharing system 

### Business Understanding

A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

### Business Goal:

You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

### Business Risk:

- No or less demand and high supply
- High demand and no or less supply

### Requirement:

- Which variable are significant in predicting the demand for shared bikes
- How well those variabe describe the bike demands 

## General Information
- Steps for crreating a linear regression model :
<ol>
    <li>Data Visualization</li>
      <ol>
        <li>Perform EDA to understand various variables.</li>
        <li>Check the correlation between the variables.</li>
      </ol>
    <li>Data Preparation</li>
      <ol>
        <li>Create dummy variables for all the categorical features.</li>
        <li>Divide the data to train & Test.</li>
        <li>Perform Scaling.</li>
        <li>Divide data into dependent & Independent variables.</li>
      </ol>
    <li>Data Modelling & Evaluation</li>
      <ol>
        <li>Create Linear Regression model using mixed approach (RFE & VIF/p-value).</li>
        <li>Check the various assumptions.</li>
        <li>Check the Adjusted R-Square for both train & Test data.</li>
        <li>Report the final model.</li>
      </ol>
</ol>
- Data Set : day.csv 

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
<div class="alert alert-block alert-danger">
    <span style='font-family:Georgia'>
        <b>EDA on Continuous Variable: </b>
        <ol>
            <li>CNT : Average demand for the bike is <b>~4508 per day</b></li>
            <li>DTEDAY : Does not have much affect on the demand</li>
            <li>TEMP : <b>20-40</b>degress temperature have a higher average rental bike per day than overall average rental<br>
            20-40 have a higher average rental bike per day than 0-20</li>
            <li>ATEMP : <b>25-40</b>degress temperature have a higher average rental bike per day than overall average rental<br>
            25-40 degress temperature have a higher average rental bike per day than 0-25</li>
            <li>HUM : <b>20-30</b> humidity levels have a higher average rental bike per day than overall average rental<br>
            20-30 humidity levels have a higher average rental bike per day than other levels</li>
            <li>WINDSPEED : <b>0-10</b> windspeed levels have a higher average rental bike per day than overall average rental<br>
            0-10 windspeed levels have a higher average rental bike per day than other levels</li>
        </ol>
        <b>EDA on Categorical Variable: </b>
        <ol>
            <li>SEASON : <b>Fall, Summer and Winter</b> have a higher average rental bike per day than overall average rental<br>
            Fall and Summer have a higher average rental bike per day than Winter and Spring</li>
            <li>YR : <b>2019 year</b> have a higher average rental bike per day than overall average rental<br>
            2019 year have a higher average rental bike per day than 2018 year</li>
            <li>MNTH : <b>6,9,8,7,5 and 10 months</b> have a higher average rental bike per day than overall average rental<br>
            6,9,8,7,5 and 10 have a higher average rental bike per day than 4,11,3,12,2,1</li>
            <li>HOLIDAY : <b>Non Holidays</b> have a higher average rental bike per day than overall average rental<br>
            Non Holidays have a higher average rental bike per day than Holidays</li>
            <li>WEEKDAY : <b>Weekday 2,3,4,5,6</b> have a higher average rental bike per day than overall average rental<br>
            Weekday 2,3,4,5,6 have a higher average rental bike per day than Weekday 1,2</li>
            <li>WORKINGDAY : <b>Working day</b> have a higher average rental bike per day than overall average rental<br>
            Working day have a higher average rental bike per day than Non Working Day</li>
            <li>WEATHERSIT : <b>Clear, Few clouds, Partly cloudy, Partly cloudy Weather</b> have a higher average rental bike per day than overall average rental<br>
            Clear, Few clouds, Partly cloudy, Partly cloudy Weather have a higher average rental bike per day than Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist, Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds</li>
        </ol>
    </span>    
</div>
<div class="alert alert-block alert-info">
    <span style='font-family:Georgia'>
        <b>Different Models with R2 values:</b>
        <ol>
            <li>Model Created All Variables<br>R2 = <b>0.732</b><br>Adj R2 = 0.729</li>
            <li>Model Created with top 15 variables using RFE<br>R2 = <b>0.845</b><br>Adj R2 = 0.840</li>
            <li>Model Created droping humidity due to VIF value > 5<br>R2 = <b>0.839</b><br>Adj R2 = 0.834</li>
            <li>Model Created droping temp due to VIF value > 5<br>R2 = <b>0.764</b><br>Adj R2 = 0.769<br>
               As dropping the temp we are lossing 7% of the variance </li>
            <li>Model Created droping winter due to High p-value > 5<br>R2 = <b>0.764</b><br>Adj R2 = 0.759</li>
            <li>Model Created droping July due to High p-value > 5<br>R2 = <b>0.763</b><br>Adj R2 = 0.758</li>
            <li>Model Created droping windspeed due to High p-value > 5<br>R2 = <b>0.745</b><br>Adj R2 = 0.740</li>
            <li>Model Created droping workingday due to High p-value > 5<br>R2 = <b>0.737</b><br>Adj R2 = 0.733</li>
            <li>Model Created droping Saturday due to High p-value > 5<br>R2 = <b>0.736</b><br>Adj R2 = 0.733</li>
            <li>Model Created droping June due to High p-value > 5<br>R2 = <b>0.732</b><br>Adj R2 = 0.729</li>
        </ol>
    </span>    
</div>
<div class="alert alert-block alert-info">
    <span style='font-family:Georgia'>
        <b>R2 value for Test Data</b><br>
        R2 = <b>0.7507</b>
    </span>    
</div>

<div class="alert alert-block alert-warning">
    <span style='font-family:Georgia'>
        <b>Coefficents for the variables</b>
        <ul>
            <li>August                       0.056657</li>
            <li>Mist & Cloudy                0.090778</li>
            <li>November                     0.097024</li>
            <li>yr                           0.246033</li>
            <li>spring                       0.284583</li>
            <li>Light Snow and Light Rain    0.310657</li>
            <li>const                        0.501079</li>
        </ul>
        <b>Based on the coefficient values for each of the variables the top 3 features contributing towards demand are:</b>
        <ul>
            <li>weathersit_Light Snow and Light Rain</li>
            <li>season_spring</li>
            <li>yr</li>
        </ul>
    </span>    
</div>
# Final Model Equation

<div class="alert alert-block alert-success">
    <span style='font-family:Georgia'>
        <b>Decisive Factor whether an applicant will be Defaulter:</b> <br>
            <h1 style="font-size:5vw"><b>cnt = const * 0.501 + yr * 0.246 + spring * -0.285 + August * 0.057 + November * -0.097 + Light Snow and Light Rain * -0.311 + Mist & Cloudy * -0.091 + 0</b></h1>  
    </span>    
</div>

## Technologies Used
- pandas - 1.4.4
- numpy - 1.21.5
- matplotlib - 3.2.2
- seaborn - 0.11.2
- plotly - 5.8.0

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This project was group case study for an online advance course.
- https://seaborn.pydata.org/
- https://plotly.com/
- https://pandas.pydata.org/
- https://learn.upgrad.com/


## Contact
Created by [@futurevisioncomputers] - feel free to contact me!




