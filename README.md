# DATA 512 A1: Data Curation

# Project Description

The goal of this project is to gain experience writing code and creating visualizations with reproducibility in mind. Following this readme and the notebook 
located in the src directory, one should be able to fully replicate the work I have done. 

The project that is used to show this reproducible workflow is visualizing the English Wikipedia web traffic over time using 2 Wikimedia REST APIs. The 
documentation and links to the APIs are listed in the "API Documentation" section below.

The main obstcale that needs to be overcome in this project is combining the legacy and current APIs together into one dataframe that we can use to visualize.
However, following the notes I have made along the way, it should be easy for anyone to be able to recreate the visualize I show below.

# Project Structure
Below is a tree view of how the project is structured. The data is separated into their corresponding sub-directories.
```
.
├── LICENSE.md
├── README.md
├── data
│   ├── data_clean
│   │   └── en-wikipedia_traffic_200712-202109.csv
│   ├── data_raw
│   │   ├── pagecounts_desktop-site_200801-201607.json
│   │   ├── pagecounts_mobile-site_200801-201607.json
│   │   ├── pageviews_desktop_201508-202109.json
│   │   ├── pageviews_mobile-app_201508-202109.json
│   │   └── pageviews_mobile-web_201508-202109.json
│   └── results
│       └── output.png
└── src
    └── hcds-a1-data-curation.ipynb
```
# Dataset
After the preprocessing of the data, a final cleaned dataset is exported. Below is a description of all of the data used to create the visualization.

* Year - Year the data was collected.
* Month - Month the data was collected.
* pagecount_all_views - Sum of desktop and mobile Legacy REST API page views.
* pagecount_desktop_views - Legacy REST API desktop page views.
* pagecount_mobile_views - Legacy REST API mobile page views.
* pageview_all_views - Sum of desktop and mobile current REST API page views.
* pageview_desktop_views - Current REST API desktop page views.
* pageview_mobile_views - Current REST API mobile page views(NOTE: This is a sum of the mobile web page and mobile app page views).

# API Documentation

As mentioned throughout this readme, two REST APIs were used to create the final visualization. Below I briefly discuss both and provide the necessary links to
find additional documentation about each one.

* [Legacy](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
The Wikimedia Legacy "Pagecounts" REST API features page views for the desktop and mobile site spanning from January 2008 to July 2016. The main difference 
among pagecounts and the current pageview data is lack of filtering of self-reported bots, thus automated and human traffic are reported together. 

* [Pageviews (current)](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) 
The Wikimedia Current "Pageviews" REST API features page views for the desktop, mobile web, and mobile app sites. This API captures data from July 2015 to the
most recent completed month. 

# Results
![alt text](https://github.com/PrestonStringham/data-512-a1/blob/master/data/results/output.jpg?raw=true)

# Additional Packages
* [Anaconda](https://www.anaconda.com/) was used as my data science platform. This gives you access to all the packages used in this project as well as Jupyter Notebooks which is necessary to open the single src file. The license agreement for anaconda can be found [here](https://www.anaconda.com/eula-anaconda-individual-edition).
* [Pandas](https://pandas.pydata.org/) was used extensively throughout this project as the main data manipulation tool. Pandas falls under the BSD 3-Clause License.
* [Matplotlib](https://matplotlib.org/) was used for visualization. The license agreement can be found [here](https://github.com/matplotlib/matplotlib/blob/master/LICENSE/LICENSE).

# Licenses and Attribution
The Wikimedia REST API is licensed under the [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/) and GFDL [GFDL](https://www.gnu.org/licenses/fdl-1.3.html) licenses.

The terms of service for the Wikimedia REST API can be founde [here](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions).
