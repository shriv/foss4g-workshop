# Analysing geospatial connectivity to understand a city
This is the materials repo for the FOSS4G Oceania 2019 workshop. Please follow all the instructions before the workshop. There is no allocated  time for installations during the workshop itself - we have a lot of exciting content to cover!

# Overview
- The workshop has two parts:
  - Foundations
  - Applications

The foundations notebook runs through the necessary technical background for the applications. There are some small Python exercises to figure out during the workshop - but nothing particularly tricky. The exercises do not need to be completed for the notebook to run.

The applications notebook introduces routes and routing. This simple technique can be then used to analyse catchments, accessibility and even identify popular / arterial roads. There are no exercises in this part but there are several discussion questions. The discussions are an integral part of the workshop. They are an opportunity to query if the techniques are useful for particular types of questions and also to learn from each others' experiences.

# Data Download
- [Playgrounds](https://data-wcc.opendata.arcgis.com/datasets/wcc-playgrounds)
  - Download Spreadsheet _and_ Shapefile
- [Suburbs](https://data-wcc.opendata.arcgis.com/datasets/wcc-suburbs-boundaries)
-
# Instructions to run the notebooks
- Download this repo
- Open a terminal and run `conda env create -f environment.yml`
- If you ran the environment command before 10/11/19, please add the following two packages:
  - `conda install -c conda-forge basemap`
  - `conda install -c conda-forge basemap-data-hires`
- If you ran the environment command after 11/11/19, there may be a problem with the basemap installation. If you get an error (related to PROJ) when importing `from mpl_toolkits.basemap import Basemap`, re-install basemap:
  - `conda install -c conda-forge basemap`
- Peter Scarth has provided another workaround for the error. Add the following to the top of the Applications notebook:

  `import requests`

  `import os`

  `os.environ['PROJ_LIB'] = os.path.abspath('../data')`

  `url = 'https://raw.githubusercontent.com/matplotlib/basemap/master/lib/mpl_toolkits/basemap/data/epsg'`

  `r = requests.get(url, allow_redirects=True)`

  `open(os.path.join(os.environ['PROJ_LIB'],'epsg'), 'wb').write(r.content)`
