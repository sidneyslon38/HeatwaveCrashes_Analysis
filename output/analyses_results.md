# The Results

## Analysis 1

I wanted to compare average monthly temperature in New York City, collected by the [National Weather Service](https://www.weather.gov/wrh/climate?wfo=okx), to pedestrian injuries from vehicle collisions, collected from police reports and available on the [Open NYC Data portal](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95/about_data).

To view all steps leading up the analyses, please navigate to the README document.

I first filtered the Motor Vehicles Collisions data from daily, to monthly numbers, by combining all instances of pedestrian injuries or death by month. The new file now contained 60 rows, or 60 months between Jan 2021 and Dec 2025, and the sum of pedestrian injuries and sum of deaths each month.

Then, I combined the data with the existing monthly temperature averages by the 'YR-M' column.

Once the two were combined, I was able to run a correlation of the two columns.

Originally, my hypothesis was that in the heat, pedestrian injuries will go up. However, there was actually a weak negative correlation (-0.3) between the two, which means that between 2021 and 2025, the data showed that pedestrian injuries decreased in hotter months. 

I compared average total pedestrian injuries on a monthly basis, and found a much stronger correlation (0.6) there. This essentially confirmed that as the months progress from 1 to 12, pedestrian injuries increased. Earlier months like Spring and Summer had lower average total injuries, whereas later months like Fall and Winter had higher average total injuries. 

Of course, this is just a correlation, but months 10-12 had much higher total average injuries than the other months.

## Analysis 2

Surprised by the results and feeling a bit discouraged, I decided to try again with the temperature data, but this time compared contributing factors. Specifically, I wanted to compare if instances of road rage that led to a pedestrian injury resulted in a correlation to higher temperatures.

Following similar steps to what I did in Analysis 1, I filtered and combined the two datasets.

By correlating total monthly pedestrian injuries caused by road rage, and average monthly temperature, I found a weak positive correlation (0.24), which means that while the two do increase with each other on average, the relationship is not statistically strong. Likely, there are other factors causing pedestrian injuries from road rage beyond heat.

## Conclusions

While heat is proven to lead to increases in events of gun violence and other forms of crime, it seems that pedestrian injuries from car crashes is not one of them. Instead, the data seems to show that more pedestrians are injured in colder months: this is potentially due to the fact that more people are traveling in the winter for holidays and/or more people leave the city in the summer. More reporting would need to be done to understand these correlations better.

The relationship between road rage and pedestrian injuries was weak, however there are also considerations in the data. Specific instances of "road rage" are defined by the police officer making the report, and some could argue that "reckless driving" would be another potential area to look at. This would involve including things like speeding into the mix, however "reckless driving" is not strictly defined in terms of contributing factors in the reports. 

Another consideration is that while pedestrian injuries are seen as fairly accurate data, total car crashes are not. Transportation Alternatives representatives have told me that many car crashes fly under the radar, which points to undercounting in total numbers, whereas pedestrian injuries are more strictly tracked. Yet, there may be stronger correlations with total car crashes and temperature.