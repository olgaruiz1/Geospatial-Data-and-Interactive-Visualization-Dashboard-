# Geospatial Data and Interactive Visualization: 
## Drought and Conflicts in Afghanistan (1999–2008)
This repository contains the code and analysis for a geospatial project that explores whether there is a link between agricultural drought, armed conflict and economic activity (using nightlights as a proxy) in Afghanistan between 1999 and 2008. It includes a full workflow from raw data to an interactive dashboard.

## Overview
Afghanistan is a country where most people depend on farming. When drought hits, it can have serious consequences. But does that translate into more conflict? That is the question this project started with.
The analysis combines two datasets:

-	PRIO-GRID: provides drought intensity, nightlights (a rough measure of economic activity) and population inside a grid of cells about 55 km wide.
- UCDP Georeferenced Event Dataset (GED): records of organised violence, each pinned to a specific cell and year.
  
The result is a panel dataset covering 255 cells over 10 years. Then an interactive dashboard was built with Dash and Plotly so users can click, slide and explore how the pieces fit together.

## Contents
- Clean, documented code for loading, merging and checking the data.
- Exploratory analysis with plots and maps that highlight the main patterns.
- An interactive dashboard with four linked views:
- A map showing conflict intensity (dot size) and drought (color) year by year.
- National trends showing how drought, nightlights and conflicts evolved over the decade.
- A scatter plot comparing drought and conflict for every cell, colored by nightlights.
- A violin plot comparing nightlight distributions between cells with and without conflict.
- A discussion of what the data does and does not tell us and the limitations to keep in mind.

## Requirements
All the code is in a Jupyter notebook. You will need Python and the following libraries:
dash==4.0.0

plotly==6.5.2

pandas==3.0.1

numpy==1.26.4

geopandas==1.1.2

## Usage
1. Clone or download this repository.
2. Place the data files in a folder called "data" next to the notebook.
3. Open the notebook "analysis_dashboard.ipynb" in JupyterLab.
4. Run the cells in order. The notebook is heavily commented, so you will see what happens at each step.
5. The last cell launches the dashboard. By default it opens in a new browser tab, but you can change it to appear inside the notebook if you prefer.

## Repository 
The repository contains:
- a folder called "data" where you should place the downloaded files
- the main notebook "analysis_dashboard.ipynb"
- this README file
- a requirements file listing the needed libraries

## Data sources
- PRIO-GRID: https://www.prio.org/data
- UCDP GED: https://ucdp.uu.se/downloads

## Some design choices
- Dot size uses a logarithmic scale so that a few extreme cells do not drown out the rest.
- On the map, cells with drought data are colored by its intensity; cells without are shown in grey. No misleading color scales.
- Cell IDs are stored in a special property so that when you click a dot, the dashboard knows exactly which cell was selected.
- Plotly's default selection box is removed to keep the view clean, with yellow highlights instead.

## About me
I am Olga Ruiz. I built this project to learn how to handle geospatial data and create interactive dashboards. 


Note: This is an exploratory project, not a causal study. The numbers show patterns, not proof. But I hope the dashboard helps you explore the data.
