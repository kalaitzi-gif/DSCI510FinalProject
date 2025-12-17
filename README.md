**DSCI510FinalProject**
This GitHub Repository (and/or zip file) contains the files necessary for completion of the DSCI510 final project for the Fall 2025 semester, taught by Professor Itay Hen.

The team member for this project is Maria Popovic. Email, GitHub username, and USC ID are below.

**Email:** kalaitzi@usc.edu

**Github username:** kalaitzi-gif

**USC ID:** 2532568719

Below, I outline the necessary components for completing this project.

**Requirement Installation for Project**

**The requirements for this project are the following libraries (via terminal):**

**1.) Import pandas library (to load, filter, and save dataset)**
- Loaded library via rendering statement in terminal 'import pandas' (as pd)
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




**Data Collection Procedure**

To obtain the Dartmouth Early Warning Project Risk Forecasting data necessary for this project, navigate to the Dartmouth Early Warning Project (DEWP) "Reports & Downloads" wepage: https://earlywarningproject.ushmm.org/reports-and-downloads. Next, under "Downloads", locate the banner entitled "All 2025-26 Data (CSV)". Under that banner, click "All worldwide data," and a CSV file of global risk forecasts will be automatically downloaded.

To obtain the World Bank API data necessary for this project (i.e., global indicator names, codes, and values), navigate to the World Bank "About the Indicators API Documentation" webpage: https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation Next, under the "About the Indicators API," there will be a hyperlinked "Basic Call Structure," Clicking this will take the user to the webpage instructing how to construct a basic API call to the base url to scrape indicator names and indicator codes (i.e., scraping the 'Population, total' indicator requires the user to pass the indicator code, in this case "SP.POP.TOTL" into the bease url). In turn, this will generate the raw JSON format of the indicator's name, value, and code.

For this project, the above was done for the following indicators ("Indicator name → Indicator Code"):

1.) GDP growth (annual %) → (NY.GDP.MKTP.KD.ZG)

2.) GDP per capita (constant 2015 US$) → (NY.GDP.PCAP.KD)

3.) Population growth (annual %) → (SP.POP.GROW)

4.) Population, total → (SP.POP.TOTL)

5.) Urban population (% of total population) → (SP.URB.TOTL.IN.ZS)

The exact processes utilized for cleaning the data necessary for this project are detailed in the section headers of each file


**Data Cleaning Procedure**

First, we import the pandas and json libraries. Next, we load the "WorldwideData_sra_2025.csv" file obtained in our 'get_data.py' file. We clean this file by filtering columns of interest, which include the following risk factors:

ISO3
risk_in_2024
riskrank
year
freediscussion
religiousfreedom
efindex
discrimpop

Then, we define the five official Caucasus countries via their ISO3 country codes (ISO3166) for filtering Dartmouth EWP data, listed below ("country -- ISO3 code"):

Armenia -- ARM
Azerbaijan -- AZE
Georgia -- GEO
Iran -- IRN
Russia --RUS


Next, we create and save a separate, filtered dataframe containing only the risk factors/columns of interest and the aforementioned countries, thereby properly narrowing the scope of our analysis for the next stage. This stage will analyze these data to reflect the risk of ongoing mass killing in the Caucasus countries.

3.) STEP C: Loads, cleans, filters, and saves processed WB API data in raw JSON format to reflect desired indicator names and indicator codes.

In this step, we load the "RAW_WB_Caucasus_2025.json" file, which was obtained from our "get_data.py" file. We clean this file by first defining the five official Caucasus countries via their ISO3 country codes (ISO3166), listed below ("country -- ISO3 code"):

Armenia -- ARM
Azerbaijan -- AZE
Georgia -- GEO
Iran -- IRN
Russia --RUS

Next, we filter our indicators of interest, which include the following ("Indicator Name - Indicator Code"):

GDP -- NY.GDP.PCAP.KD --> (Gross Domestic Product)
GDP Growth -  NY.GDP.MKTP.KD.ZG --> (GDP Growth)
Total Population - SP.POP.TOTL --> (Total Population)
Urban Population (%) - SP.URB.TOTL.IN.ZS --> ('Urban Population (%))
Population Growth - SP.POP.GROW --> (Population Growth)

Next, we loop through each country, appending the above indicators and their corresponding values for the current country.

4.) STEP D: Standardizes column names across the DEWP CSV file and the raw WB JSON file to merge the files in preparation for analysis in 'run_analysis.py'.

In this step, we convert our WB JSON data from long to wide format. Next, we merge (outer) our processed 'filtered_dartmouth_df' with our processed 'wb_records_wide', based on the union of keys from both dataframes ('Country' and 'Year')

The exact processes utilized for cleaning the data necessary for this project are detailed in the section headers of each file




**Data Analysis Procedure**

First, we import the pandas and numpy libraries. Next, we load the "merged_wb_dartmouth_df" file obtained in our 'clean_data.py' file. Next, we clean this file by first defining the five official Caucasus countries via their ISO3 country codes (ISO3166), listed below ("country -- ISO3 code"):

Armenia -- ARM
Azerbaijan -- AZE
Georgia -- GEO
Iran -- IRN
Russia --RUS

****Data Statistics Procedure****

Then, we perform descriptive statistics on our combined DEWP risk factors and WB Indicators, listed below.
The output of these statistics includes elements such as count, mean, standard deviation, 25th percentile, 50th
percentile, and the 75th percentile of each of the listed risk factors and indicators below

risk_in_2024 --> select DEWP "country's Estimated Risk for 'onset of intrastate mass killing in 2024-25'"

freediscussion --> select DEWP "Citizens' ability to openly discuss political issues."

efindex --> select DEWP variable representing percentage of "Ethnic Heterogeneity." 

religiousfreedom --> select DEWP variable showing whether or not there is "Freedom of Religion." 

discrimpop --> select DEWP variable representing "Portion of Population Coded as Being Discriminated Against (%)"

GDP growth (annual %) --> select WB 'GDP Growth' indicator 

GDP per capita (constant 2015 US$) --> select WB 'GDP per capita (constant 2015 US$)' indicator 

Population growth (annual %) --> select WB 'Population growth (annual %)' indicator

Population, total --> select WB 'Population, total' indicator 

Urban population (% of total population) --> select WB 'Urban Population (%)' indicator 


Next, we save these descriptive statistics for these risk factors/indicators

**Per-Country Averages Procedure**

The third step involves generating a Pearson correlation between a given country's risk for experiencing ongoing mass killing and its current GDP per capita. This involves selecting the relevant columns, listed below:

Country
risk_in_2024_mean (generated from step c above)
GDP per capita (constant 2015 US$)_mean

We save these correlations to a CSV file

**Correlations Procedure**

The third step involves generating a Pearson correlation between 'risk_in_2024_mean' and all other DEWP risk factors and WB Indicators. This involves selecting the averages of all DEWP risk factors and WB indicators, listed below:

risk_in_2024_mean --> select average of "country's Estimated Risk for 'onset of intrastate mass killing in 2024-25'", (Source 8)
freediscussion_mean --> select average of "Citizens' ability to openly discuss political issues" (Source 9)
efindex_mean --> select average of variable representing percentage of "Ethnic Heterogeneity" (Source 9)
religiousfreedom_mean --> select average of variable showing whether or not there is "Freedom of Religion" (Source 9)
discrimpop_mean --> select variable representing "Portion of Population Coded as Being Discriminated Against (%)" (Source 9)
GDP growth (annual %)_mean --> select average of WB 'GDP Growth' indicator (Source 28)
GDP per capita (constant 2015 US$)_mean --> select average of WB 'GDP per capita (constant 2015 US$)' indicator (Source 10)
Population growth (annual %)_mean --> select average of 'Population growth (annual %)' (Source 11)
Population, total_mean --> select average of 'Population, total' indicator (Source 12)
Urban population (% of total population)_mean --> select average of 'Urban Population (%)' indicator (Source 13)

This generates correlations across the Caucasus region, showing how each WB indicator is associated with a country's risk for experiencing ongoing mass killing

Detailed data analysis for this project is documented via comments in the 'run_analysis.py' file.




****Data Visualizations Procedure****

First, we import the pandas and matplotlib libraries. Next, we generate three visualizations for each descriptive statistic calculated above

**bar chart**
compares the average risk of a given country experiencing ongoing mass killing in 2024 (Risk Score)

to generate this bar chart by sorting each coutnries; ris fromhighest to lowest
nexty we creat eh abr chart via plt.bar ,specify its axes via (x is cuntry) (y is average risk in 2024) then we add relevant tiles

**scatterplot**
shows association between a given country's Gross Domestic Product (GDP) per Capita and its respective Risk Score

**horizontal bar chart**
shows which WB Indicators are most strongly correlated with a country's risk fo experiencing ongoing mass killing in 2024


Detailed data visualization for this project is documented via comments in the 'visualization_results.py' file.

























