
# Aircraft Safety Analysis

Embraer, a Brazilian airline company that produces private jets in addition to commercial aircrafts, is looking to enter the United States market by purchasing an aircraft of the lowest potential risk



## Business Understanding
This notebook is for a company named Embraer, a Brazilian airline company that produces private jets in addition to commerical aircrafts, looking to enter the U.S. market by purchasing an aircraft of the lowest potential risk.

Embraer requests that we only analyze accidents or airplanes with a reciprocating engine type that occurred in the United States. The make cannot be an amateur build and Embraer only relies on data with the top ten highest count of sample data. Embraer is not looking to purchase an airplane that is used for commercial enterprises.
## Data Understanding
This data is from the National Transportation Safety Board that includes aviation accident data from 1962 to 2023 about civil aviation accidents and selected incidents in the United States and international waters. Each aviation accident has a unique event ID associated with it and contains additional information in each row from the type of aircraft, the make, the model, and any safety and injury metrics to account for.

This dataset has 31 columns and 90348 rows. The column datatypes contain 5 floats and 26 objects. For relevance for this project I will clean up the data to include columns worth examining to solve my business understanding problem.

Some initial limitations in this dataset include missing values, as only the Investigation.Type column contains the full 90348 rows. I will fill these NaN values based off how I see fit. For example, an NaN for an airplane under Number.of.Engines will be replaced with a 1 as airplanes need at least 1 engine and NaN values for injury counts will be filled with 0.0 as this probably means no injuries were reported.
## Data Preparation
To filter my data to my stakeholder's specific requests, I've narrowed my data down to just airplane accidents with reciprocating engines that were not amateur built that occurred in the United States. Additionally, my stakeholder only trusts data that has the ten highest counts of data. I've narrowed down this as well. This data will help me determine the lowest risk Make for my stakeholder to purchase.
## Exploratory Data Analysis
Determining the lowest risk make can be best determined by analyzing the average number of engines per make (typically a higher number of engines correlates to a lower risk), the average number of fatal injuries per make accident, the average number of serious injuries per make accident, the average number of minor injuries per make accident, and the average number of uninjured per make accident. The following visualizations depict the makes over top ten reported counts of data.
<img width="402" alt="Screenshot 2024-04-02 at 8 17 50 AM" src="https://github.com/justinnllee/Aircraft_Safety_Analysis/assets/63434512/ab02476c-5f1d-437e-bf31-ec3525a26042">


Once selecting the lowest risk make, we determine if one or more engines are preferable for a lower risk.

Next, keeping in mind number of engines for the lowest risk make, the lowest risk model is analyzed and selected.
<img width="599" alt="Screenshot 2024-04-02 at 8 17 09 AM" src="https://github.com/justinnllee/Aircraft_Safety_Analysis/assets/63434512/40befa12-6109-417a-a448-9a51ba93bbf7">


The following graphs are bar charts that also showcase the interquartile region of each value count.
## Conclusion
This analysis leads to three recommendations for selecting the lowet risk aircraft for Embraer to purhcase

1) The Cessna make. The Cessna make is the lowest risk make averaging more than one engine in the top ten counts of Embraer's analysis criteria when analyzing average injury counts in fatal, serious and minor injuries.

2) Select a Cessna model averaging more than one engine. In looking at the top ten data counts of Cessna models per Embraer's criteria, two models average more than one engine. The 140 and 150. These two models average zero injuries for average fatal, serious and minor injuries. Cessna models with one or fewer engines average 0.175 fatal injuries per Embraer's criteria.

3) Purchase the Cessna 140 model. Now that we've established the higher number of engines is lower risk, the 140 averages a lower risk than the 150 in fatal, minor and uninjured counts. The 150 only averages a lower risk in serious injury counts than the 140 but not by much.
## Limitations
After concluding my analysis, some limitations to this study should be noted.

1) My stakeholder only requested data with the ten highest counts reported. If accidents of other private enterprise Makes were reported in this dataset that also met the other criteria of my stakeholder, we could have had a more in-depth analysis. This dataset was very abundant on the Cessna make compared to other makes we analyzed.

2) This dataset was limited in numerical data to compare amongst each other. Performing a describe action at the start of our analysis showed that only five columns of data were numerical. I utilized all numerical data in my analysis, but more numerical columns could have led to a better analysis.

3) There were a lot of NaN values in this dataset. To account for this, I removed all NaN rows under the Number.of.Engines column and turned all NaN values under the injury columns to 0.0. If these NaN values had reliable data values in place of them at the start, it could have led us to a better analysis.
## Next Steps
Further analysis could yield additional insights to further improve our selection of the lowest risk aircraft:

1) More even distribution of accident reports among the makes present in the data. Some makes accident report sample size far outweighed other makes. This would lead to more reliable data to base our decision off of for one make compared to other makes.

2) Analyzing more numerical data. By analyzing more numerical data, we could create more visualizations and avenues to look into for our analysis. We only have five numerical data columns in this dataset.

3) Working around the missing NaN values. By having a full dataset we could perform a stronger analysis, rather than relying on my intuition on how to account for NaN values in each column.
## Links
[Click here to view Tableau visualization]([https://public.tableau.com/views/Phase1FinalProject/Phase1Dashboard?:language=en-US&publish=yes&:sid=&:display_count=n&:origin=viz_share_link](https://public.tableau.com/views/Phase1FinalProjectEdit/Phase1Dashboard?:language=en-US&publish=yes&:sid=&:display_count=n&:origin=viz_share_link))

[Click here to view presentation slides](https://docs.google.com/presentation/d/1TdO0IpjlnPGsd5YozP1ll-xYN5N3niOlkkZOwGwPuq4/edit?usp=sharing)
