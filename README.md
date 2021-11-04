<h1><center><font size="6">DataKind CDAC Project</br>
by Steven Yan</font></center></h1>

<img src="images/DataKind.png">

This is my personal repository of the coding for the various tasks outlined in the project.  Any coding was submitted and reviewed by DataKind Data Leads before submitting to the project organization.

# Overview:

DataKind DataDive events have an orientation session on Friday night for participants across the different time zones in the world.  However, coding doesn't officially begin until Saturday, but groups are coding together for all of Saturday and Sunday to present findings on Sunday late afternoon to the other participants.

There were three projects to select from:

1. **Housing Insecurity:** in conjunction with New America's FLH program, end-goal being to create an open-source set of tools to facilitate collection and analysis of evcition and mortgage foreclosure data
2. **Young Females Impacted by Justice System:** in conjunction with the Delores Barr Weaver Policy Center, which heavily relies on volunteers for data tasks, end-goal being to conduct a series of data extraction, visualization, and exploration tasks
3. **Broadband Access:**  in conjunction with CDAC at UChicago, explained below

DataKind provides the platform and resources for data scientists at any level of expertise to create the code necessary to perform the requested tasks.During the entire event, the volunteers are given support by the DataKind staff, and the staff ultimately present the findings where we are left to produce coding for the objectives.

# Objectives:

1. First Task Group
	- 1a. To align Ookla data at the census trac level for Florida
	- 1b. Map the FCC and Ookla datasets at census tract level
	- 1c. For maps, visualize availability (FCC) / performance (Ookla) and access (ACS) for each state

2. Second Task Group
	- 2a. Conduct EDA on NYC Permit Dataset
	- 2b. What about other cities have similar open datasets for street construction permits related to internet fiber?
	- 2c. What additional open datasets can you find that may be relevat to exploring construction for internet fiber or 5B?

# Tableau visualizations:

## NYC Visualizations

[Link to Tableau Public NYC 1](https://public.tableau.com/views/DataKIndCDACProjectVisualization-NYCMetro2/Dashboard2?:language=en-US&:display_count=n&:origin=viz_share_link)

[Link to Tableau Public NYC 2](https://public.tableau.com/views/DataKIndUCCDACProjectPreliminaryEDA-NYCMetro/NYCMetroArea?:language=en-US&:display_count=n&:origin=viz_share_link)

<img src='images/nyc_tableau.png'>

[Link to Tableau Public Chicago](https://public.tableau.com/views/DataKIndUCCDACProjectPreliminaryEDA-Chicago/Chicagoland?:language=en-US&:display_count=n&:origin=viz_share_link)

<img src='images/tableau_chicago.png'>



# Folder Structure:

	├── README.md                   <- the top-level README for reviewers of this project
	├── joining_datasets.ipynb      <- notebook for developing pipeline for data cleaning
	├── tableau.ipynb               <- notebook for preparing data for Tableau uplaod
	├── pca.ipynb                   <- notebook for PCA on task group 1 data
	├── permits.ipynb               <- notebook for task group 2
	├── _images                     <- folder for JPEGs and PNGs
	├── _data                       <- folder of datasets and shape files (*.csv, *.xlsx, *.geojson, *.shp)
	└── utils.py                    <- script with self-defined functions


# References:

- **Ookla Dataset:**  Ookla aggregates raw Speedtest performance and provides global fixed broadband and mobile (cellular) network performance metrics - https://github.com/teamookla/ookla-open-data
- **FCC 477 Dataset:**  Data are reported at the Census block level, by provider (73M rows total), where salient fields include advertised bandwidths and fiber availability - https://www.fcc.gov/general/measuring-broadband-america
- **ACS Census Data:**  The American Community Survey (ACS)  is a yearly 1% survey of the entire U.S. population - Data at census tract level available via census API and individual level but within PUMAs through IPUMS
  - https://api.census.gov/data/2019/acs/acs5/profile/variables/DP02_0152PE.json
  - https://api.census.gov/data/2019/acs/acs5/profile/variables/DP02_0153PE.json 
  - https://www.census.gov/data/developers/data-sets/acs-5year.html
  - https://usa.ipums.org/usa-action/variables/CIHISPEED
- **Permit Data NYC:**  Includes 150 different types of sidewalk and roadway construction permits to utilities, contractors, government agencies and homeowners - https://data.cityofnewyork.us/Transportation/Street-Construction-Permits/tqtj-sjs8/data
- **Permit Data Chicago:**  Applications to the Chicago Department of Transportation for permits under its jurisdiction - https://data.cityofchicago.org/Transportation/Transportation-Department-Permits/pubx-yq2d



# Contact Information:

<img src="images/mail_icon.png" width="20"> **Email:**  [datascisteven@gmail.com](mailto:datascisteven@gmail.com)

<img src="images/linkedin_icon.png" width="20"> **LinkedIn:**  [https://www.linkedin.com/in/datascisteven](https://www.linkedin.com/in/datascisteven)

<img src="images/github_icon.png" width="20"> **Github:**  [https://www.github.com/datascisteven](https://www.github.com/datascisteven)

<img src="images/Rainbow-Medium.png" width="20"> **Medium:** [https://datascisteven.medium.com](https://datascisteven.medium.com)