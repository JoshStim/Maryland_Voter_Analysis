# Maryland Voter Analysis

Baltimore City’s voter turnout is approximately 10% lower than the Maryland state average, with historically marginalized communities facing systemic barriers to voting. This report analyzes demographic and socio-economic differences between Baltimore and other Maryland counties to identify key factors contributing to this turnout gap.

## Data

Data for this study were obtained from two sources: the L2 Voter Database and the American Community Survey (ACS).

### L2 Voter Database

L2 is a trusted source of up-to-date voter data for all 50 states in the US. For the current analysis, we obtained 2022 registered voter data for Maryland at the census-block level. For each of the 83,827 unique census blocks provided, we obtained the following metrics on registered voters:

  - **Registered voter counts x election**: The number of registered voters for the 2020 and 2022 general and primary elections

  - **Votes cast x election**: The number of votes cast for the 2020 and 2022 general and primary elections

  - **Gender counts among registered voters**: The number of registered voters in 2022 in each of the following gender bins: Male, Female, or "Unknown"

  - **Age bins among registered voters**: The number of registered voters in 2022 in each of the following age bins: 18-19, 20-24, 25-29, 30-34, 35-44, 45-54, 55-64, 65-74, 75-84, 85-older

  - **Ethnicity counts among registered voters**: The number of registered voters in 2022 in each of the following primary ethnicity bins: European, Hispanic, African American, Eastern Asian, Other, and Unknown

### American Community Survey (ACS)

ACS is a survey conducted by the US Census that provides detailed social, economic, housing, and demographic information from a sample of households in all 50 US states, the District of Columbia, and Puerto Rico. Using `tidycensus` in R, we extracted the 5-year average, ending in 2022, for a subset of ACS variables for each census tract in Maryland. These variables are described below:

  - **Means of transportation to work (`B08006`)**: This data table contains information on peoples' primary method of transportation to work. The universe is people who are 16 years or older. For each Maryland census tract, we extracted count estimates for people who drive to work alone (`B08006_002`), use public transportion (`B08006_008`), bicycle to work (`B08006_014`), walk to work (`B08006_015`), taxi to work (`B08006_016`), and work from home (`B08006_017`).

  - **Educational attainment (`B15003`)**: This data table contains information on educational attainment (i.e., highest level of education attained). The universe is people who are 25 years or older. For each Maryland census tract, we extracted count estimates for people whose maximum eduational attainment was a high school diploma (`B15003_017`), a GED or alternative credential (`B15003_018`), less than 1 year of college (`B15003_019`), one or more years of college but not degree (`B15003_020`), an associate's degree (`B15003_021`), a bachelor's degree (`B15003_022`), a master's degree (`B15003_023`), a graduate professional degree (`B15003_024`), or a doctorate degree (`B15003_025`).

  - **Median household income (`B19013`)**:

  - **Employment status (`B23025`)**:
