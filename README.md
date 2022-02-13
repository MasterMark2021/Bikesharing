# Bikesharing
Tableau environment.

**Project Overview**
The purpose of this project is to create a visual business proposal using Tableau Public. Data on Citi bike ridership in New York City is analyzed to determine the business prospects of creating a similar business in Des Moines, Iowa. Pandas DataFrames and Tableau Calculated Fields are used to transform the datatypes and format of some columns.

**Changing the Datatype of "tripduration**
While creating the visualizations necessary for this project, it was found necessary to transform the datatype of the "tripduration" column from an integer to a string. This was accomplished through the following steps:

1. The original CSV data file was read and transformed into a dataframe:

citi_bike_data = "201908-citibike-tripdata.csv"
citi_bike_data_df = pd.read_csv(citi_bike_data)

2. The data was converted into the datetime datatype with the following code:

citi_bike_data_df["tripduration(datetime)"] = pd.to_datetime(citi_bike_data_df["tripduration"], unit="s")

3. The updated dataframe is exported as a new CSV file without the index:

citi_bike_data_df.to_csv("aug_2019_citibike_data_datetime.csv", index=False)

**Updating the Gender Column**
The column "Gender" was originally formatted as 0, 1, and 2 to identify genders (Unknown, Male, and Female). To have this column correctly print with letters instead of numbers, the datatype of the column is changed to string and the following code was used to create a calculated field:

if [Gender] = '0' then 'UNKNOWN'
ELSEIF [Gender] = '1' then 'MALE'
ELSEIF [Gender] = '2' then 'FEMALE' END

**Reults and Outcome**
Click on the below to view my complete presentation and analysis!
https://public.tableau.com/app/profile/mark.okoli/viz/NYCCitibikeStory_16447626534450/NYCCitibikeStory?publish=yes
Also refer to the image folders for more information and analysis: https://github.com/MasterMark2021/Bikesharing/tree/main/Output%20Images
The analysis begins with general information, which contains a map of the top starting locations for rides in NYC and a pie chart showing the gender distribution of riders. This dashboard is intended to provide a basic overview of the data.
Total user checkout times are then shown, which is then followed by the same graph filtered by gender. This line graph showcased the large disparity in Male and Female ridership.
Total trips by weekday are visualized as a heatmap. The majority of Monday-Friday trips are 7 AM - 9 AM and 5 PM - 7 PM. When filtering this heatmap by Gender, it is again found that Male ridership far outpaces Female ridership. However, the peak riding hours across all genders are similar.
Finally, user trips by gender is visualized. This chart illustrates that users are much more likely to be subscribers, rather than ordinary customers.

**Summary**
In this analysis, it is found that the majority of Citi bike riders in New York City (NYC) identify as Male. Additionally, these rides typically begin in Ubran and densely populated areas. Bike riding may be an attractive alternative to cars in NYC due to the congested streets and the ease of transportation.

Although this business is popular in NYC due to the heavy traffic, it is not certain that Des Moines will develop the same success. Further research must be done on Des Moines to determine whether car traffic and locational convenience would motivate potential customers to use this service. While NYC has a population density of approximately 27,000 people per square mile, Des Moines only has 2,436 people per square mile. In fact, NYC has nearly 39 times the population of Des Moines.

Link to Story and Worksheets for view where applicable. 

NYC BIke Story Link : https://public.tableau.com/app/profile/mark.okoli/viz/NYCCitibikeStory_16447626534450/NYCCitibikeStory?publish=yes
Worksheet Links:
https://public.tableau.com/app/profile/mark.okoli/viz/CheckoutTimesforUsers_16447627345840/CheckoutTimesforUsers?publish=yes
https://public.tableau.com/app/profile/mark.okoli/viz/CheckoutTimesbyGender_16447627763090/CheckoutTimesbyGender?publish=yes
https://public.tableau.com/app/profile/mark.okoli/viz/TripsbyWeekdayforEachHour_16447628364970/TripsbyWeekdayforEachHour?publish=yes
https://public.tableau.com/app/profile/mark.okoli/viz/CreatetheTripsbyGender/CreatetheTripsbyGender?publish=yes
https://public.tableau.com/app/profile/mark.okoli/viz/UserTripsbyGenderbyWeekday_16447629942790/UserTripsbyGenderbyWeekday?publish=yes
