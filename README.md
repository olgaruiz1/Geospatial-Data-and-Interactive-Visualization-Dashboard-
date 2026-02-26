# Geospatial Data and Interactive Visualization: 
## Drought and Conflicts in Afghanistan (1999–2008)
This repository contains the code and analysis for a geospatial project that explores whether there is a link between agricultural drought, armed conflict and nightlight time (using it as a proxy) in Afghanistan between 1999 and 2008. It includes a full workflow from raw data to an interactive dashboard.

## The dashboard (GIFs)
- Exploring years (year slider updates all charts)
  
![years_exploration](https://github.com/user-attachments/assets/30895369-13ea-4a95-b6a4-0f1db7f47c46)


- Hover (Hover to see cell details)

![hovering](https://github.com/user-attachments/assets/9c108263-fed9-48a2-b8bf-2fe2a106763c)


- Click on map → highlights in scatter and violin

![map click](https://github.com/user-attachments/assets/23a2c8c7-199a-4a0c-bb7b-27575e56bf7f)


- Click on scatter → highlights in map and violin
  
![scatter click](https://github.com/user-attachments/assets/b4a7ebab-dd17-46a5-9cc7-d0678c27e6d4)

## Overview
Afghanistan is a country where most people depend on farming. When drought hits, it can have serious consequences. But does that translate into more conflict? That is the question this project started with.
The analysis combines two datasets:

-	PRIO-GRID: provides drought intensity, nightlights (a rough measure of economic activity) and population inside a grid of cells about 55 km wide.
- UCDP Georeferenced Event Dataset (GED): records of organised violence, each pinned to a specific cell and year.
  
The result is a panel dataset covering 255 cells over 10 years. Then an interactive dashboard was built with Dash and Plotly so users can click, slide and explore how the pieces fit together. This was built in a Jupyter notebook. 

At the end of the README you can find GIFs showing how the dashboard actually looks like. 

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

install them with
pip install -r requirements.txt

## Data sources

- From PRIO-GRID (https://www.prio.org/data) the files 'PRIO-GRID_Yearly_Variables.csv' and 'priogrid_cellshp' are needed.
- From UCDP GED (https://ucdp.uu.se/downloads) the file 'GEDEvent_v25_1.csv' is needed. 

## Usage
1. Clone or download this repository.
2. Create a folder named data in the root directory.
3. Place the downloaded files inside data/ following the structure below.
4. Open the notebook interactive_dashboard.ipynb in JupyterLab.
4. Run the cells in order. The notebook is commented, so you will see what happens at each step.
5. The last cell launches the dashboard. By default it opens inside the notebook, but you can change it to open in a new tab if you prefer.

## Expected file structure
geospatial_data_and_interactive_visualization_dashboard/
│

├── data/

│   ├── PRIO-GRID_Yearly_Variables.csv

│   ├── GEDEvent_v25_1.csv

│   └── priogrid_cellshp/    

│       ├── priogrid_cell.shp

│       ├── priogrid_cell.shx

│       ├── priogrid_cell.dbf

│       └── (other shapefile components)

├── interactive_dashboard.ipynb

├── README.md

└── requirements.txt

## Some design choices
- Dot size uses a logarithmic scale so that a few extreme cells do not drown out the rest.
- On the map, cells with drought data are colored by its intensity; cells without are shown in grey. No misleading color scales.

- Cell IDs are stored in a special property so that when you click a dot, the dashboard knows exactly which cell was selected.
- Plotly's default selection box is removed to keep the view clean, with yellow highlights instead.

## About me
I am Olga Ruiz. I built this project to learn how to handle geospatial data and create interactive dashboards. 


Note: This is an exploratory project, not a causal study. The numbers show patterns, not proof. But I hope the dashboard helps you explore the data.
