# HotelBookingPrediction_MLProject
This is the final project for my Introduction to Business Analytics Final project, completed at @10/08/2022

# Business Overview
This project will analyze hotel cancellation data. Booking cancellations can be a hassle for the hospitality industry impacting on demand-management decisions. Many hotel chains now implement rigid 24 to 72 hour cancellation policies and overbooking tactics. These two strategies do not always help in maintaining the hotel’s reputation and repeat customers. 
We want to demonstrate that by using machine learning and data mining, it is possible to build models to predict whether or not a customer will cancel their booking. By running the models daily against all reservations on-the-books, a hotel location can discover new information such as the number of room nights predicted to be canceled for each of the following days. Equipped with an accurate demand value, hotel managers can develop more effective overbooking and cancellation policies to accommodate their guests and maximize revenue.

# Modeling Ideas
This is a classification problem and hence the data science task is supervised learning. But we will also use unsupervised learning to explore the data before employing supervised learning. 
Each observation (instance) represents a hotel booking. The Observation contains the following information: hotel type, whether the reservation was canceled or not(is_canceled), lead time, arrival date year, arrival date month, arrival date week number, arrival date day of month, stays in weekend nights, stays in week nights, number of adults specified in the reservation, number of children, babies, meal type, country, market segment, distribution channel, is repeated guest, previous cancellations from that customer, previous bookings not canceled, reserved room type, assigned room type, booking changes, deposit type, agent, company, days in waiting list, customer type, adr, required car parking spaces, total of special requests, reservation status, and reservation status date. 
We chose is_canceled (whether the booking was canceled or not) as our target variable. It is derived from the reservation status(check-out/canceled). Many variables can be used in predicting whether the booking was canceled or not. We will explore some variables like the lead time, hotel type, country of origin, repeat guest, previous cancellations etc. 

# Data Details 
• Give a short description of the data you are planning to use.
The dataset compares various booking information between two hotels: a city hotel and a resort hotel. It has multiple variables (32 columns) and we plan on using whether the booking was canceled or not as the target variable.

• How have you obtained the data? What is the source of the data?
We obtained the data from Kaggle. The original data is originally from the article Hotel Booking Demand Datasets, written by Nuno Antonio, Ana Almeida, and Luis Nunes for Data in Brief, Volume 22, February 2019. Within the article, data were presented as two separate datasets: The first dataset is for resort hotel data which has 79,330 observations and the second is for city hotel data which has 40,060 observations. It contained 31 variables but the version provided on kaggle combines these datasets to form the version that we will use in this project. Thus, our dataset has 119,390 observations with 32 columns.

• Load the data into RapidMiner/Python for EDA
We use info(), describe() to check the data structure and details of each variables, below are our discoveries:
The dataset contains 119,390 rows and the number of the variables is 32
Variables with missing values: 4 variables namely country, agent, company, and children will require data cleansing
Types of variables: the datatype of variables are shown in the screenshot in python and the feature types are as follows:
Categorical - hotel, is_canceled, customer_type, is_repeated_guest, meal, country, market_segment, distribution_channel, reserved_room_type, assigned_room_type, deposit_type, agent, company, reservation_status
Numerical - lead_time, stays_in_weekend_nights, stays_in_week_nights, adults, children, babies, previous_cancellations, booking_changes, previous_bookings_not_canceled, days_in_waiting_list, adr, required_car_parking_spaces, total_of_special_requests, arrival_date_year, arrival_date_month, arrival_date_week_number, arrival_date_day_of_month, reservation_status_date

This is a binary classification problem, and the ratio of the prevalent class (is_canceled = 0) is 0.6296, which means the percentage for reservation not being canceled in the dataset is 62.96%. And we also explored the canceled (is_canceled =1) class in resort and city hotels and the cancellation rates are 27.76% and 41.72% respectively.

