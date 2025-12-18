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




**Data Collection Procedure --> STANDARDIZE STEPS TO MATCH THE REST OF THE PAHSES**

To obtain the Dartmouth Early Warning Project Risk Forecasting data necessary for this project, navigate to the Dartmouth Early Warning Project (DEWP) "Reports & Downloads" webpage: https://earlywarningproject.ushmm.org/reports-and-downloads. Next, under "Downloads", locate the banner entitled "All 2025-26 Data (CSV)". Under that banner, click "All worldwide data," and a CSV file of global risk forecasts will be automatically downloaded.

To obtain the World Bank API data necessary for this project (i.e., global indicator names, codes, and values), navigate to the World Bank "About the Indicators API Documentation" webpage: https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation Next, under the "About the Indicators API," there will be a hyperlinked "Basic Call Structure," Clicking this will take the user to the webpage instructing how to construct a basic API call to the base url to scrape indicator names and indicator codes (i.e., scraping the 'Population, total' indicator requires the user to pass the indicator code, in this case "SP.POP.TOTL" into the bease url). In turn, this will generate the raw JSON format of the indicator's name, value, and code.

For this project, the above was done for the following indicators ("Indicator name → Indicator Code"):

- GDP growth (annual %) → (NY.GDP.MKTP.KD.ZG)

- GDP per capita (constant 2015 US$) → (NY.GDP.PCAP.KD)

- Population growth (annual %) → (SP.POP.GROW)

- Population, total → (SP.POP.TOTL)

- Urban population (% of total population) → (SP.URB.TOTL.IN.ZS)

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

- risk_in_2024 --> DEWP "country's Estimated Risk for 'onset of intrastate mass killing in 2024-25'"

- riskrank --> **INPUT LABEL HERE**

- year --> **INPUT LABEL HERE**

- freediscussion --> DEWP "Citizens' ability to openly discuss political issues."

- religiousfreedom --> select DEWP variable showing whether or not there is "Freedom of Religion."

- efindex --> select DEWP variable representing percentage of "Ethnic Heterogeneity."

- discrimpop --> select DEWP variable representing "Portion of Population Coded as Being Discriminated Against (%)"

4.) To continue cleaning the Dartmouth EWP data, define the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country (ISO3 code)"):

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)


5.) Create and save a separate, filtered dataframe containing only the aforementioned risk factors of interest and the aforementioned countries. This step properly narrows the scope of  analysis required for Step 3 of this project (Data Analysis, "run_analysis.py"), which will analyze these data to reflect the risk of ongoing mass killing in the Caucasus countries.

**STEP C: Load, clean, filter, and save processed WB API data in raw JSON format
to reflect desired indicator names and indicator codes.**

Loads, cleans, filters, and saves processed WB API data in raw JSON format, reflecting the desired indicator names and indicator codes.

1.) Load the "RAW_WB_Caucasus_2025.json" file (obtained in Step 1, Data Collection, in the "get_data.py" file)

2.) Clean "RAW_WB_Caucasus_2025.json" file by the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country (ISO3 code):

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)

3.) Filter WB indicators of interest, which include the following ("Indicator Name - Indicator Code"):

- GDP growth (annual %) → (NY.GDP.MKTP.KD.ZG)

- GDP per capita (constant 2015 US$) → (NY.GDP.PCAP.KD)

- Population growth (annual %) → (SP.POP.GROW)

- Population, total → (SP.POP.TOTL)

- Urban population (% of total population) → (SP.URB.TOTL.IN.ZS)



4.) Loop through each country via "for loop", appending the above indicators and their corresponding values for the current country into a specified list of dictionaries.

5.) Convert the list of nested dictionaries, containing the following components for each country:

- Country
- Indicator Name
- Indicator Code
- Year
- Indicator Value


**STEP D: Standardize columns across DEWP CSV file and raw WB JSON file to
merge the files in preparation for analysis in 'run_analysis.py'.**

6.) Convert raw WB JSON data from long to wide format 

7.) Perform outer merge on processed 'filtered_dartmouth_df' file with processed 'wb_records_wide' file, based on the union of keys from both dataframes ('Country' and 'Year')

8.) Save merged file

The exact processes utilized for cleaning the data necessary for this project are detailed in the section headers of each file






**Data Analysis Procedure**

Steps for the Data Analysis Procedure are below:

**STEP A: Import Libraries**

1.) Import numpy and pandas libraries (as described above)

**STEP B: Load merged Dartmouth EWP (DEWP) and World Bank API file**

1.) Load the "merged_wb_dartmouth_df" file obtained in Step 2 of this project (Data Cleaning, "clean_data.py")

2.) Begin cleaning "merged_wb_dartmouth_df" by defining the five officially recognized Caucasus countries by respective ISO3 country codes (ISO3166), listed below ("country (ISO3 code)")

- Armenia (ARM)

- Azerbaijan (AZE)

- Georgia (GEO)

- Iran (IRN)

- Russia (RUS)

****Descriptive Statistics Procedure****

3.) Perform the following descriptive statistics (below) on "merged_wb_dartmouth_df", for each of the quantitative DEWP risk factors and WB indicators (under "Combined DEWP Risk Factors and WB Indicators" ):

**Descriptive Statistics**

- Count
- Mean
- Standard deviation
- 25th percentile
- 50th percentile
- 75th percentile
- Maximum
- Minimum

**Combined DEWP Risk Factors and WB Indicators**

- risk_in_2024

- freediscussion

- efindex

- religiousfreedom

- discrimpop

- GDP growth (annual %) → WB 'GDP Growth' indicator

- GDP per capita (constant 2015 US$) → WB 'GDP per capita (constant 2015 US$)' indicator

- Population growth (annual %) → WB 'Population growth (annual %)' indicator

- Population, total → WB 'Population, total' indicator

- Urban population (% of total population) → WB 'Urban Population (%)' indicator 


3.) Save these descriptive statistics for these risk factors and indicators, as a CSV file

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

























