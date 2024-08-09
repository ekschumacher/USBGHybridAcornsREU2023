## Project Description
This GitHub repository is a combination of the analyses that were used to detect hybrids in the offspring of 9 _Quercus muehlenbergii_ trees sampled at the Morton Arboretum in Fall of 2022. These analyses were performed through 2023 - 2024 by a combination of collaborators: Sean Hoban, Ash Hamilton, Mikaely Evans, and Emily Schumacher. Our study was mostly concerned with quantifying the levels of hybridization within the botanic garden collections of Morton Arboretum white oaks to provide a model system for protecting oaks in living collections without producing hybrid offspring. 

We performed a study analyzing the parentage of acorns produced by maternal <i>Quercus muehlenbergii</i> individuals at the Morton Arboretum to identify if (1) any offspring individuals were hybrids and (2) what factors contribute to the parentage of offspring produced in living collections. We collected a total of 385 seeds, grew them to seedling stage, and sampled leaf tissue from the seedlings. Using 13 microsatellite loci, we performed parentage analysis using CERVUS software. Following this analysis, we produced multiple figures comparing the distance between candidate fathers, mothers, and hybrid production. 

## Folder Descriptions

### Analysis:
- Parentage_Analysis
- RScripts
    - 01_data_cleaning_for_parentage.R
    - 02_data_cleaning_post_parentage.R
    - 03_figures.R
    - 04_dist_analysis.R

### Archive:
The Archive folder includes all files that are **not** integral to the analysis of this project. 

  - Data_Files_Archive → This folder contains two duplicate data files that are not used in the final analysis.
  - UHA_Attempted_md_Analysis → This folder contains two folders: UHA_Cervus_Attempts and UHA_PolyPatEx_Attempts. The analysis included in these folders was done with files that had too much missing data so they are not relevant to the rest of our study. The purpose of the files was only for practicing the types of analysis with the data we had at the time. 
  - UHA_nomd_PolyPatEx_Analysis → This folder contains the fully cleaned data set analysis using PolyPatEx. For this project, using the CERVUS analysis gave us better, more accurate parentage assignment results, so we decided against using the PolyPatEx results. All the data and code files can be found here for PolyPatEx analysis.


### Data_Files:
The Data_Files folder includes two subfolers: Clean_Data_Files and Data_Cleaning_Code. The purpose of this folder is to include all the clean data files and to show how they were cleaned. These cleaned data files were used in the  paternity analysis to produce our final results.

  - Clean_Data_Files → This folder contains two subfolders, Clean_csv and Clean_xlsx. The files are the same, just in two different forms. These files are the results from the Data_Cleaning_Code folder.
  - Data_Cleaning_Code → The Data_Cleaning_Code folder contains an important script: UHA_datacleaning.R, written by Emily Schumacher. This R script cleans the data in order to make it useable for the analysis. The files directly involved with the data cleaning R script are "UHA_Final_Scores.arp", "UHA_Final_Scores.gen", and "UHA_Final_Scores_nomd_genalex.csv". The other csv files that were not directly involved with this script have minor adjustments made to them so they can be used in analysis as well. These files are "UHA_Final_Scores_nomd_df.csv" and "UHA_Final_Scores_GenAlEx.csv".

### Results:
