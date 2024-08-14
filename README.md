## Project Description
This GitHub repository is a combination of the analyses that were used to detect hybrids in the offspring of 9 _Quercus muehlenbergii_ trees sampled at the Morton Arboretum in Fall of 2022. These analyses were performed through 2022 - 2024 by a combination of collaborators: Ash Hamilton, Mikaely Evans, and Emily Schumacher. Our study was mostly concerned with quantifying the levels of hybridization within the botanic garden collections of Morton Arboretum white oaks to provide a model system for protecting oaks in living collections without producing hybrid offspring. 

We performed a study analyzing the parentage of acorns produced by maternal <i>Quercus muehlenbergii</i> individuals at the Morton Arboretum to identify if (1) any offspring individuals were hybrids and (2) what factors contribute to the parentage of offspring produced in living collections. We collected a total of 385 seeds, grew them to seedling stage, and sampled leaf tissue from the seedlings. Using 13 microsatellite loci, we performed parentage analysis using CERVUS software. Following this analysis, we produced multiple figures comparing the distance between candidate fathers, mothers, and hybrid production. 

## Project Workflow 
This project went through several stages, and so the workflow through the data files is described below: 

<b>Geographic analyses:</b> This was a preliminary stage of analyses that were performed to determine which botanic garden was a suitable model for our experimental question. These analyses were conducted using the RScripts stored in the "Geographic Analysis" file in the Analysis folder, with the data files used in the Data_Files/Geographic_Files pathway. The resulting CSV files are stored in the Results/Geographic_Analyses pathways.
- We examined 3 different botanic garden model systems: the UC Davis campus, Starhill Arboretum, and the Morton Arboretum. This stage of the process examined these arboretums for a few different traits:
    - At least 10 individuals of a specific oak species within breeding distance (350 m) that were producing acorns in the summer of 2022.
- Following the stage of this analysis we determined that the Morton Arboretum was the best suited to our study design.

<b>Parentage analyses</b>: Once the Morton Arboretum was selected as the study location, _Quercus muehlenbergii_ was selected as the model species because it was the only oak species observed with 10 individuals over 10 years of age (reproductive age in oaks) within the study area that were producing at least 10 acorns. We sampled as many acorns as possible (with a goal of at least 10 acorns) and potting a minimum of 10 acorns. Acorns and leaf tissue for maternal individuals were sampled in Fall 2022, and then leaf tissue all white oak individuals within a 350 m radius from all maternal individuals were sampled in summer 2023 and summer 2024. DBH measurements were collected in summer 2024. Genetic data was collected from individuals in 2023 - 2024 which were used to perform parentage analysis in CERVUS. Below is a description of how files were created to be run in CERVUS and then how the resulting files from CERVUS were processed in R. 
- Preparing files for CERVUS: Genotype files generated from Geneious were processed in the RScript <u>01_data_cleaning_for_parentage.R</u> were used to generate the input files for parentage analysis in CERVUS. The input file used in this script was a genepop file (.genepop) and it was marked as a "clean" data file if once individuals were removed for having 25% missing genotypes. In this script, there is also a step for creating files with and without the full loci used to genotype individuals. "all_loci" files refer to data files with all 13 loci run on individuals in these data, whereas "red_loci" files refer to genotype files that have 4 loci removed because they were identifed to have high frequencies of null alleles (>15%). The results of this script are stored in the <u>Data_Files/CERVUS_Files</u> pathway.  
- CERVUS_Files: All files used to run parentage analysis in CERVUS are stored in the <u>CERVUS_Files</u> folder, which has separate folders for "all_loci" and "red_loci" data files, as these parentage runs were done separately. There is a separate folder for <u>Input_Files</u> which house a genotype_df.csv, an offspring_df.csv,  
- Parentage analysis result generation: The other RScripts in the <u>Parentage_Analysis</u> folder are to process the results of parentage analysis. The <u>02_data_cleaning_post_parentage.R</u> script is used to process the results of the CERVUS parentage runs - stored in the <i>par_sum</i> files - to produce figures and tables for the manuscript. This script includes also creating data files with the designation HCF. HCF stands for "high confidence father" which are candidate father assignments that were made with pairwise and trio LOD scores > 0. This resulted in four <u>par_sum</u> data files - overall four scenarios to determine the impact of null alleles and confidence of parentage assignments on the final figures. This RScript was initially written by Mikaely Evans and Ash Hamilton but then udpated to loop over all data file scenarios by Emily Schumacher.
    - Final figures for the manuscript were generated in the <u>03_figures.R</u> RScript. This code was generated by Mikaely Evans.  
  
## Folder Descriptions

### Analysis:
This folder is divided into 3 separate analysis sections that cover a different set of analyses. 
- Geographic_Analysis
    - 01_geographic_analysis_prep.R
        - Description: This R Script was used to visualize oak species in botanic gardens Starhill Arboretum, UC Davis Campus, and the Morton Arboreutm. These data files were used to generate color coded maps stored in the project guide for this project. 
    - 02_garden_summary_dfs.R
        - Description: This R Script was used to generate overview data frames of the oak species in Starhill Arboretum, UC Davis Campus, and the Morton Arboreutm - oak individuals above 10 years of age to visualize candidate sampling areas.    
    - 03_TMA_all_trees.R
        - Description: This script was used to visualize candidate sites for acorn sampling once the Morton Arboretum was decided to be the best site for this project.
- Parentage_analysis
    - 01_data_cleaning_for_parentage.R
    - 02_data_cleaning_post_parentage.R
    - 03_figures.R
- STRUCTURE
    
  
### Archive:

### Data_Files:

### Results:
