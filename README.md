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
   
	- To align Ookla data at the census trac level for Florida
	- Map the FCC and Ookla datasets at census tract level
	- For maps, visualize availability (FCC) / performance (Ookla) and access (ACS) for each state

2. Second Task Group
   
	- Conduct EDA on NYC Permit Dataset
	- What about other cities have similar open datasets for street construction permits related to internet fiber?
	- What additional open datasets can you find that may be relevat to exploring construction for internet fiber or 5B?


# Data

We were given 3 preprocessed datasets, ACS (Census), FCC, Ookla, to begin work with, accompanied by shapefiles.

The ACS database had numerous columns, but I chose to keep the following columns for analysis and/or visualization:

- `f_black` = fraction of population black (`n_black` / `population`)
- `f_hispanic` = fraction of population Hispanic (`n_hispanic` / `population`)
- `f_ba` = fraction of population with Bachelor's (`n_ba` / `den_ba`)
- `f_broadband` =  fraction of households with broadband access (`n_broadband` / `households`)
- `f_computer` = fraction of households with computer access (`n_computer` / `households`)
- `population` = total population
- `mhi` = median household income
- `n_children` = number of children
- `households` = number of households

The FCC database had the following columns:

- `tract`: 11-digit tract FIPS code
- `max_dn`: average maximum advertised downstream speed offered by provider in census tract by block
- `max_up`: average maximum advertised upstream speed offered by provider in census tract by block
- `dn10`:	average count of providers offering advertised downstream greater than 10 by block
- `dn100`: average count of providers offering advertised downstream greater than 100 by block
- `dn250`: average count of providers offering advertised downstream greater than 250 by block
- `fiber_100u`: average count of providers offiering fiber by block


The Ookla database had the following columns"




# Mapping at the Census Tract Level

The shapefiles may contain the following:

`STATEFP`: State FIPS Code (2-digit)
`COUNTYFP`: County FIPS Code (2-digit)
`TRACTCE`: Census Tract Code (4-digit base number and 2-digit suffix)
`AFFGEOID`
`GEOID`: `STATEFP` + `COUNTYFP` + `TRACTCE`
`NAME`: from `TRACTCE`, base number.suffix
`LSAD`: Legal/Statistical Area Description codes
`ALAND`: land area
`AWATER`: water area
`geometry`: designed to store shapely geometry objects

There are 4906 rows in the shapefile, as well as 4906 unique rows of GEOID's. The state FIPS code is 36, and there are 62 county FIPS code in NY.  The AFFGEOID seems to be the GEOID affixed with 1400000US in front of each GEOID.  There are values given for land area, water area, and most importantly the geometry of the tract boundaries. An LSAD of CT tells us that we are dealing on the level of the Census Tract.

Each GEOID consists of the state FIPS code, its county FIPS code, and then the tract FIPS code, which apparently in itself is not unique and can be repeated, so 2 + 3 + 6 digits in total for the three components or an 11-digit tract FIPS code that is unique for every tract.

The NAME represents a census tract code that split into a 4-digit and 2-digit suffix placed after the decimal. Census tract numbers can consist of up to 6 digits:  up to a 4-digit basic number and optional 2-digit suffix, i.e. 1457.02. When used as name, any leading zeroes are eliminated and the suffix is appended if designated. 

Within the standard census geographic hierarchy, census tracts never cross state or county boundaries, but may cross the boundaries of county subdivisions, places, urban areas, voting districts, congressional districts. 


# Tableau visualizations:

## NYC Visualizations

[Link to Tableau Public NYC 1](https://public.tableau.com/views/DataKIndCDACProjectVisualization-NYCMetro2/Dashboard2?:language=en-US&:display_count=n&:origin=viz_share_link)

[Link to Tableau Public NYC 2](https://public.tableau.com/views/DataKIndUCCDACProjectPreliminaryEDA-NYCMetro/NYCMetroArea?:language=en-US&:display_count=n&:origin=viz_share_link)

<img src='images/nyc_tableau.png'>

## Chicago Visualizations

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