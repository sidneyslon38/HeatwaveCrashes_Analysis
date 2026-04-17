# HeatwaveCrashes_Analysis

## Hypothesis

Given that instances of gun violence and other forms of crime increase with heat, I wanted to see if the same could be said for pedestrian injuries and car crashes. I originally thought that the hotter the temperature, the more pedestrian injuries from car crashes would occur.

## Steps for finding the data

I gathered data from the [Open NYC Data portal](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95/about_data) and [National Weather Service](https://www.weather.gov/wrh/climate?wfo=okx). The vehicle collision data was filtered to only include collisions between January 2021 and December 2025, a five-year time span and the most recent collision data that includes the entire year of reports. 2026 was not included, as there are still 8 more months left of the year.

Overall car crashes are not considered accurate for analyses, as many fly under the radar in the data set. These rows come from individual NYPD reports. 

However, pedestrian injuries are considered much more accurate, hence why that was the main factor for this analysis. Each injury instance is considered a "serious" injury, which is defined by New York State law.

## Loading in the data

I imported both data sets, one of which can be viewed in this repository's data folder as a CSV file. The Motor Vehicle crashes data is too large for this repository, but can be easily downloaded from the Open NYC Data portal.

Using pandas, a python library, I filtered through both data sets and combined them to compare monthly pedestrian injuries and monthly temperature averages. 

## Analysis

To view steps I took during the analysis, both analysis notebooks, which can be found in this repository's [notebooks](https://github.com/sidneyslon38/HeatwaveCrashes_Analysis/tree/main/notebooks) folder, are annotated with comments so that steps can be replicated.

## Results

To view detailed findings, you can read the [results](https://github.com/sidneyslon38/HeatwaveCrashes_Analysis/blob/main/output/analyses_results.md) file, found in this repository's output folder.

## Additional Notes

Generative AI using Claude Haiku 4.5 was used to assist me during the analysis process. No code was written by AI itself, and the chatbot was only used to provide advice and help me understand how to format the code. Specifically, I used it for help to convert daily crash dates into monthly crash data.

The prompt for this was as follows: 
"I'm comparing monthly heat data to crash data, I need to turn this filtered dataframe from daily to monthly.

I want to create a new dataframe that takes the CRASH DATE (in datetime64) and turn into it months, while making a sum column of pedestrian injury counts and pedestrian deaths."

It's response:
"Use .dt.to_period('M') to extract year-month for grouping from the CRASH DATE column"

I also used AI for help combining the two datasets. The temperature data was originally formatted as a table, so AI reccomended I use:

".melt(id_vars=['Year'], var_name='Month', value_name='Temperature')"

This "melted" the data into long form data that could be combined with the other data frame.

Once months had been mapped to their respective numbers (1-12), to combine the two data frames, I used .merge, which was also reccomended by AI.

Specifically, I needed help understanding how "left_on" and "right_on" worked for combining, which essentially helps the code know which dataframe to prioritize as the main one.

Finally, AI helped me learn how to use the correlate function, and the matplotlib.pyplot to create a visual scatter plot. 

It imported the matplotlib.pyplot for me, and helped me format the code correctly. The plot can be defined using "plt.X" for the legend, title, xlabel, ylabel, plot and scatter data.