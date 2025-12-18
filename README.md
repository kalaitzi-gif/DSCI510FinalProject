**DSCI510FinalProject**
This GitHub Repository (and/or zip file) contains the files necessary for completion of the DSCI510 final project for the Fall 2025 semester, taught by Professor Itay Hen.

The team member for this project is Maria Popovic. Email, GitHub username, and USC ID are below.

**Email:** kalaitzi@usc.edu

**Github username:** kalaitzi-gif

**USC ID:** 2532568719

Below, I outline the necessary components for completing this project.

**Installation Requirements for Project**

**The requirements for this project are the following libraries (via terminal):**

**1.) Import pandas library (to load, filter, and save dataset)**
- Loaded library via rendering statement in terminal "import pandas" (as pd)
- Utilized in 'get_data.py', 'clean_data.py', 'run_analysis.py', 'visualize_results.py.'

**2.) Import requests module to retrieve webpage**
- Loaded library via rendering statement in terminal "import requests"
- Utilized in 'get_data.py.'

**3.) Import JSON module to relay API responses and work with JSON-formatted files**
- Loaded  library via rendering statement in terminal "import json"
- Utilized in 'get_data.py', 'clean_data.py.'

**4.) Import numpy library (for mathematical functions: linear algebra, random numbers)**
- Loaded library via rendering statement in terminal "import numpy" (as np)
- Utilized in 'run_analysis.py', 

**5.) Import the matplotlib library for visualization of plotting**
- Loaded via rendering statement in terminal "import matplotlib" (as plt)
- Utilized in 'visualize_results.py.'




**Code Running Procedure**

In the terminal, navigate to the directory where the project folder is located. This can be done by utilizing the 'cd' terminal command, which stands for 'change directory'.
For example, to navigate to the directory where this project is located, one could type the following command into the terminal ("cd" followed by file path):

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject"

**For each required code block of this project, one would navigate to the following directories in the terminal**

**1.) To retrieve and run 'get_data.py', navigate to the following directory using the path below:**

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/data/raw"

To run the 'get_data.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python get_data.py"

**2.) To retrieve and run 'clean_data.py', navigate to the following directory using the path below:**

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/data/processed"

To run the 'clean_data.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python clean_data.py"

**3.) To retrieve and run 'run_analysis.py', navigate to the following directory using the path below:**

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/src"

To run the 'run_analysis.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python run_analysis.py"

**4.) To retrieve and run 'visualize_results.py', navigate to the following directory using the path below**

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/src"

To run the 'visualize_results.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python visualize_results.py"




**Data Collection Description**

To obtain the Dartmouth Early Warning Project Risk Forecasting data necessary for this project, navigate to the Dartmouth Early Warning Project (DEWP) "Reports & Downloads" webpage: https://earlywarningproject.ushmm.org/reports-and-downloads. Next, under "Downloads", locate the banner entitled "All 2025-26 Data (CSV)". Under that banner, click "All worldwide data," and a CSV file of global risk forecasts will be automatically downloaded.

To obtain the World Bank API data necessary for this project (i.e., global indicator names, codes, and values), navigate to the World Bank "About the Indicators API Documentation" webpage: https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation Next, under the "About the Indicators API," there will be a hyperlinked "Basic Call Structure," Clicking this will take the user to the webpage instructing how to construct a basic API call to the base url to scrape indicator names and indicator codes (i.e., scraping the 'Population, total' indicator requires the user to pass the indicator code, in this case "SP.POP.TOTL" into the bease url). In turn, this will generate the raw JSON format of the indicator's name, value, and code.

For this project, the above was done for the following indicators ("Indicator name → Indicator Code"):

- GDP growth (annual %) → (NY.GDP.MKTP.KD.ZG)

- GDP per capita (constant 2015 US$) → (NY.GDP.PCAP.KD)

- Population growth (annual %) → (SP.POP.GROW)

- Population, total → (SP.POP.TOTL)

- Urban population (% of total population) → (SP.URB.TOTL.IN.ZS)




**Data Collection Procedure**

Steps for the Data Collection Procedure are below:


**STEP A: Import Libraries**

1.) Import pandas, requests, and json libraries (as described above)


**STEP B: Load and save DEWP global risk scores**

2.) 'WorldwideData_sra_2025.csv', showing global risks of countries experiencing ongoing mass killing.

3.) Save raw file in original CSV, "RAW_Caucasus_RiskData_2025.csv"


**STEP C: Load and save WB API data**

3.) Define the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country [ISO3 code]"):

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)


4.) Define WB indicators of interest in a dictionary (Indicator names (key) and WB indicator codes (value)), listed below ("Indicator name → Indicator Code")

- GDP per capita, PPP (constant 2021 international $) → NY.GDP.PCAP.KD

- GDP Growth (annual %) → NY.GDP.MKTP.KD.ZG

- Total Population → SP.POP.TOTL

- Urban population (% of total population) → SP.URB.TOTL.IN.ZS

- Population Growth (annual %) → SP.POP.GROW

- Government Effectiveness (Estimate) → GE.EST

- Rule of Law → RL.EST

- Secondary School Enrollment (% gross) → SE.SEC.ENRR

- Human Capital Index (HCI) (scale 0-1) → HD.HCI.OVRL


As noted in the final report, the following indicators were selected for the remainder of the project.

- GDP growth (annual %) → (NY.GDP.MKTP.KD.ZG)

- GDP per capita (constant 2015 US$) → (NY.GDP.PCAP.KD)

- Population growth (annual %) → (SP.POP.GROW)

- Population, total → (SP.POP.TOTL)

- Urban population (% of total population) → (SP.URB.TOTL.IN.ZS)


5.) Run a nested loop over the above indicator names and indicator codes

6.) Parse WB API response into JSON format, convert into Python object

7.) Save WB API indicator data as a raw JSON file


The exact processes utilized for data collection necessary for this project are detailed in the section headers of each file




**Data Cleaning Procedure**

Steps for the Data Cleaning Procedure are below:

**STEP A: Import Libraries**

1.) Import pandas and json libraries (as described above)




**STEP B: Load, clean, filter, and save processed DEWP data to reflect
Caucasus countries' risk data for experiencing ongoing mass killing.**

2.) Load the "WorldwideData_sra_2025.csv" file obtained in the 'get_data.py' file

3.) Clean "WorldwideData_sra_2025.csv" file via column filtration of the following risk factors from the CSV file:

- ISO3 Country Code

- risk_in_2024 → DEWP "country's Estimated Risk for 'onset of intrastate mass killing in 2024-25'"

- riskrank → **INPUT LABEL HERE**

- year → **INPUT LABEL HERE**

- freediscussion → DEWP "Citizens' ability to openly discuss political issues."

- religiousfreedom → select DEWP variable showing whether or not there is "Freedom of Religion."

- efindex → select DEWP variable representing percentage of "Ethnic Heterogeneity."

- discrimpop → select DEWP variable representing "Portion of Population Coded as Being Discriminated Against (%)."

4.) To continue cleaning the Dartmouth EWP data, define the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country [ISO3 code]"):

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)

5.) Create and save a separate, filtered dataframe containing only the aforementioned risk factors of interest and the aforementioned countries. This step properly narrows the scope of  analysis required for Step 3 of this project (Data Analysis, "run_analysis.py"), which will analyze these data to reflect the risk of ongoing mass killing in the Caucasus countries.




**STEP C: Load, clean, filter, and save processed WB API data in raw JSON format
to reflect desired indicator names and indicator codes.**

Loads, cleans, filters, and saves processed WB API data in raw JSON format, reflecting the desired indicator names and indicator codes.

6.) Load the "RAW_WB_Caucasus_2025.json" file (obtained in Step 1, Data Collection, in the "get_data.py" file)

7.) Clean "RAW_WB_Caucasus_2025.json" file by the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country [ISO3 code]"):

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)

8.) Filter WB indicators of interest, which include the following ("Indicator Name - Indicator Code"):

- GDP growth (annual %) → (NY.GDP.MKTP.KD.ZG)

- GDP per capita (constant 2015 US$) → (NY.GDP.PCAP.KD)

- Population growth (annual %) → (SP.POP.GROW)

- Population, total → (SP.POP.TOTL)

- Urban population (% of total population) → (SP.URB.TOTL.IN.ZS)

9.) Loop through each country via "for loop", appending the above indicators and their corresponding values for the current country into a specified list of dictionaries.

10.) Convert the list of nested dictionaries, containing the following components for each country:

- Country
- Indicator Name
- Indicator Code
- Year
- Indicator Value




**STEP D: Standardize columns across DEWP CSV file and raw WB JSON file to
merge the files in preparation for analysis in 'run_analysis.py'.**

11.) Convert raw WB JSON data from long to wide format 

12.) Perform outer merge on processed 'filtered_dartmouth_df' file with processed 'wb_records_wide' file, based on the union of keys from both dataframes ('Country' and 'Year')

13.) Save merged file

The exact processes utilized for cleaning the data necessary for this project are detailed in the section headers of each file




**Data Analysis Procedure**

Steps for the Data Analysis Procedure are below:

**STEP A: Import Libraries**

1.) Import numpy and pandas libraries (as described above)




**STEP B: Load merged Dartmouth EWP (DEWP) and World Bank API file**

2.) Load the "merged_wb_dartmouth_df" file obtained in Step 2 of this project (Data Cleaning, "clean_data.py")

3.) Begin cleaning "merged_wb_dartmouth_df" by defining the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country [ISO3 code]")

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)




**STEP C: Generate Descriptive Statistics on DEWP Risk Factors and WB Indicators Per Caucasus Country.**

4.) Perform the following descriptive statistics on "merged_wb_dartmouth_df" (below), for each of the quantitative DEWP risk factors and WB indicators (under "Combined DEWP Risk Factors and WB Indicators"):

**Descriptive Statistics**

This data analysis step is performed to properly set up a bar chart comparing the average risk of a given country to experience ongoing mass killing in 2024-2025 (as shown in Step 4 of this project, "Data Visualization," in 'visualize results.py').

- Count
- Mean
- Standard deviation
- 25th percentile
- 50th percentile
- 75th percentile
- Maximum
- Minimum


**Combined DEWP Risk Factors and WB Indicators**

Below are the outputs of the DEWP risk factors and WB indicators after running descriptive statistics on each.

- risk_in_2024_mean

- freediscussion_mean

- efindex_mean

- religiousfreedom_mean

- discrimpop_mean

- GDP growth (annual %)_mean → WB 'GDP Growth' indicator

- GDP per capita (constant 2015 US$)_mean → WB 'GDP per capita (constant 2015 US$)' indicator

- Population growth (annual %)_mean → WB 'Population growth (annual %)' indicator

- Population, total_mean → WB 'Population, total' indicator

- Urban population (% of total population)_mean → WB 'Urban Population (%)' indicator 

5.) Save these descriptive statistics for these risk factors and indicators as a CSV file




**STEP D: Generate averages per Caucasus country for the WB Indicator of Gross Domestic Product (GDP) and its respective DEWP Risk Score.**

**Per-Country Averages Procedure**

This data analysis step is performed to properly set up a scatterplot showing the correlation between GDP and risk for each country (as shown in Step 4 of this project, "Data Visualization," in 'visualize results.py').

6.) Generate a Pearson correlation between a Caucasus country's risk score and its current GDP per capita. This involves selecting the relevant columns, listed below:

- Country
- risk_in_2024_mean (generated from Step C above)
- GDP per capita (constant 2015 US$)_mean

7.) Save these correlations to a CSV file




**Correlations Procedure**

This data analysis step is performed to properly set up a horizontal bar chart showing which WB Indicators are most strongly correlated with a country's risk of experiencing ongoing mass killing in 2024-2025 (as shown in Step 4 of this project, "Data Visualization," in 'visualize results.py').

8.) Generate a Pearson correlation between 'risk_in_2024_mean' and all other DEWP risk factors and WB Indicators. This involves selecting the averages ("..._mean" variables)of all DEWP risk factors and WB indicators, listed below:

- risk_in_2024_mean → Average of "country's Estimated Risk for 'onset of intrastate mass killing in 2024-25'"

- freediscussion_mean → Average of "Citizens' ability to openly discuss political issues"

- efindex_mean → Average of variable representing percentage of "Ethnic Heterogeneity"

- religiousfreedom_mean → Average of variable showing whether or not there is "Freedom of Religion"

- discrimpop_mean → Average variable representing "Portion of Population Coded as Being Discriminated Against (%)"

- GDP growth (annual %)_mean → Average of WB 'GDP Growth' indicator

- GDP per capita (constant 2015 US$)_mean → Average of WB 'GDP per capita (constant 2015 US$)' indicator

- Population growth (annual %)_mean → Average of 'Population growth (annual %)'

- Population, total_mean → Average of 'Population, total' indicator

- Urban population (% of total population)_mean → Average of 'Urban Population (%)' indicator


This procedure generates correlations across the Caucasus region, showing how strongly, positively, weakly, or negatively each DEWP risk factor and WB indicator is associated with a country's risk for experiencing ongoing mass killing. Generating these descriptive statistics, per-country averages, and Pearson correlations across the DEWP risk factors and AB indicators is necessary for completing Step 4 of this project (Data Visualization, "visualize_results.py").

Detailed data analysis for this project is documented via comments in the 'run_analysis.py' file.




****Data Visualizations Procedure****

Steps for the Data Visualizations Procedure are below:

**STEP A: Import pandas and matplotlib libraries**

1.) Import pandas and matplotlib libraries (as described above)

2.) Generate three visualizations for each descriptive statistic calculated above

**STEP B: Generate Bar Chart - 2024 RISK SCORES BY COUNTRY**

This bar chart compares the average risk of a given country experiencing ongoing mass killing in 2024-2025 (Risk Score)

3.) To generate the bar chart, begin by selecting the "Country" as the label and the "risk_in_2024_mean" to serve as the bar height.

4.) Sort the visualization of countries from highest risk to lowest risk

5.) Generate the bar chart, specifying x-axis ("Country"), y-axis ("risk_in_2024_mean"), and title, "2024 Average Risk by Caucasus Country." 

6.) Save bar chart as a .png file as "Bar_Risk_by_Country"

**STEP C: Generate Scatterplot -  GDP PER CAPITA vs. RISK SCORE**

This scatterplot shows the association between a given country's Gross Domestic Product (GDP) per Capita and its respective Risk Score

7.) To generate the scatterplot, begin by creating a dataframe with one row per country, one economic indicator, and one risk outcome per country 

8.) Generate the scatterplot, specifying x-axis data position as "GDP per capita (constant 2015 US$)_mean" and specifying the y-axis data position as "risk_in_2024_mean", and title, "2024 Average Risk by Caucasus Country"

6.) Save scatterplot as a .png file as "Scatter_Risk_GDP"

**STEP D: Generate Horizontal Bar Chart - WB INDICATORS VS RISK SCORE**

This Horizontal Bar Chart shows which DEWP risk factors and WB Indicators are most or least correlated with a country's risk of experiencing ongoing mass killing in 2024-2025.

7.) To generate the horizontal bar chart, begin by sorting the visualization from negative to positive risk correlations.

8.) Generate the  horizontal bar chart, specify the x-axis as "Risk Score Correlation", specify the y-axis as "Average Risk Score", and specify the title as "Risk Factors, Indicators vs. Risk Score."

6.) Save scatterplot as a .png file as "Horizontal_Bar_Indicator_Risk"

Detailed data visualization for this project is documented via comments in the 'visualization_results.py' file
