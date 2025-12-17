**DSCI510FinalProject**
This GitHub Repository contains the files necessary for completion of the DSCI510 final project for the Fall 2025 semester.

The team member for this project is Maria Popovic. Email, GitHub username, and USC ID are below.

**Email:** kalaitzi@usc.edu

**Github username:** kalaitzi-gif

**USC ID:** 2532568719

Below, I describe how to fulfill the necessary components for completing this project

**How to install requirements for the project**

The requirements for this project are the following libraries (via terminal):

1.) pandas library (to load, filter, and save dataset) --> used in 'get_data.py', 'clean_data.py', 'run_analysis.py', 'visualize_results.py.'
loaded via rendering statement in terminal 'import pandas' (as pd)

2.) import requests module to retrieve webpage --> used in 'get_data.py.'
loaded via rendering statement in terminal 'import requests.'

3.) # import JSON module to relay API responses and work with JSON-formatted files --> used in 'get_data.py', 'clean_data.py.'
loaded via rendering statement in terminal 'import jso.n'

4.) import numpy library (for mathematical functions: linear algebra, random numbers) --> used in 'run_analysis.py', 
loaded via rendering statement in terminal 'import numpy' (as np)

5.) Import the matplotlib library for visualization of plotting
loaded via rendering statement in terminal 'import matplotlib' (as plt) --> used in 'visualize_results.py.'


**How to run the code**

In the terminal, navigate to the directory where the project folder is located. This can be done by utilizing the 'cd' terminal command, which stands for 'change directory'.
for example:

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject"

For each required code block of this project, one would navigate to the following directories in the terminal


1.) To retrieve and run 'get_data.py', navigate to the following directory using the path below:

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/data/raw"

To run the 'get_data.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python get_data.py"


2.) To retrieve and run 'clean_data.py', navigate to the following directory using the path below:

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/data/processed"

To run the 'clean_data.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python clean_data.py"


3.) To retrieve and run 'run_analysis.py', navigate to the following directory using the path below:

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/src"

To run the 'run_analysis.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python run_analysis.py"

4.) To retrieve and run 'visualize_results.py', navigate to the following directory using the path below

"cd /Users/mariakalaitzidis/Documents/USC/Fall2025Courses/DSCI510/FinalProject/MP_FinalProject/src"

To run the 'visualize_results.py' file, type the following in the terminal ("python", followed by the file you wish to run):

"python visualize_results.py"

**how to get the data**

To obtain the Dartmouth Early Warning Project Risk Forecasting data necessary for this project, navigate to the following website: https://earlywarningproject.ushmm.org/reports-and-downloads. Next, under "Downloads", locate the banner entitled "All 2025-26 Data (CSV)". Under that banner, click "All worldwide data," and a CSV file of global risk forecasts will be automatically
downloaded.

To obtain the World Bank API data necessary for this project, navigate to the following website: https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation Next, under the "About the Indicators API," there will be a hyperlinked "Basic Call Structure," Clicking this will take the user to the webpage instructing how to construct a basic API call to the base url () to scrape indicator names and indicator codes **(i.e., scraping the '--' indicator requires the user to input the indicator code, in this case '---' into the bease url, '---base url with code')**. In turn, this will generate the raw JSON data corresponding to that indicator.

For this project, the above was done for the following indicators:
**1.) INDICATOR NAME AND CODE**
**2.) INDICATOR NAME AND CODE**
**3.) INDICATOR NAME AND CODE**
**4.) INDICATOR NAME AND CODE**
**5.) INDICATOR NAME AND CODE**

Detailed data collection for this project is documented via comments in the 'get_data.py' file.

**how to clean data**

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


Next, we create and save a separate, filtered dataframe containing only the risk factors/columns of interest and the aforementioned countries, thereby properly narrowing down our analysis scope for the next stage. This stage will analyze these data to reflect the risk of ongoing mass killing in the Caucasus countries.

3.) STEP C: Loads, cleans, filters, and saves processed WB API data in raw JSON format to reflect desired indicator names and indicator codes.

In this step, we load the "RAW_WB_Caucasus_2025.json" file, which was obtained from our "get_data.py" file. We clean this file by defining the five official Caucasus countries via their ISO3 country codes (ISO3166), listed below ("country -- ISO3 code"):

Armenia -- ARM
Azerbaijan -- AZE
Georgia -- GEO
Iran -- IRN
Russia --RUS

Next, we filter our indicators of interest, which include the following ("Indicator Name - In dicator Code"):

4.) STEP D: Standardizes column names across the DEWP CSV file and the raw WB JSON file to
merge the files in preparation for analysis in 'run_analysis.py'.


The exact processes utilized for cleaning the data necessary for this project is detailed in the section headers of each file


Detailed data cleaning for this project is documented via comments in the 'clean_data.py' file.


**How to run the analysis**



Detailed data analysis for this project is documented via comments in the 'run_analysis.py' file.

**How to produce the visualizations**



Detailed data visualization for this project is documented via comments in the 'visualization_results.py' file.

























