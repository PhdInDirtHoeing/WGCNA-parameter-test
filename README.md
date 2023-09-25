# WGCNA-parameter-test
An automated pipeline for determining best parameters and confirming scale-free structure of transcriptome data for use in Whole Genome Correlation Network Analysis

# Workflow Outline

### This script is primarily for the purpose of finding an appropriate cutoff for excluding the lowest expressed genes from the data set based on the power value (soft power) and mean connectivity (k) as calculated by the WGCNA functions. This is done by arranging the genes in order from most expressed to least expressed during preliminary cleaning steps, and then choosing what percentage of genes you'd like to include. This script allows you to input percentages in a list that will be looped through to the point of generating modules. Parameters including soft power, mean connectivity, number of modules, and number of unassigned genes will be written into a table for each percentage so that the one with the best percentage can be chosen. You will need to input other parameters including CutHeight (set at 0.10 by default), Deep Split (set at 4 by default), and Minumum Module Size (set at 100 by default). Note that the loop only cycles through a list of percentages, so if you want to test different settings for the other parameters you'll need to run the code again each time. 


## 1. Load libraries and read in input files

### A. Normalized TPM data in .csv format (Tested using DeSeq2 for normalization) formated with gene ids in the first column and sample names as column labels
### B. List of samples (one sample name per replicate group) in the first column as a .csv file

## 2. Prepare and subset data as needed

### A. Cleaning data
### B. Option to include or not include lncRNAs

## 3. Select input parameters

### A. Percent list
### B. Min mod size, Cut Height, and Deep Split
### C. Option to print pdfs or not for each percentage

## 4. Run loop to test percentages

## 5. Choose best percentage 

### A. Option to automatically detect best percentage or enter manually
### B. Option to delete saved .Rdata files and/or all other files associated with percentages that you're not using

## 6. Load .Rdata file that you will use

## 7. Eigengenes (NOTE: This section requires customization)

### A. Calculate eigengenes
### B. Graph eigengenes

## 8. Get Module Stats

### A. Get a list of genes in each module as a .csv file
### B. Create a graph of gene frequency in each module
### C. Option to include or not include lncRNA stats in part 2A above will affect generation of lncRNA specific plots

## 9. Generate Edge and Node files

### A. Generate edges and nodes for each module
### B. Generate a list of file names for both edges and nodes
### C. Generate node statistics to determine cutofff stringency 

## 10. Genes of interest

### A. Option to pull a table identifying modules where genes of interest exist 

## Bonus content


