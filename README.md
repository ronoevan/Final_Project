# Final_Project
- May 2023 in the Ironhack, Berlin
# Coronavirus GENE - VARIANT Caller App and Machine Learning Approaches for Efficient Genomic Surveillance and Prediction Analyses  

## By Evans
## Dataset: hCoV-19 (Coronavirus) complete genome Sequences from GISAID database!

##  Table of Contents

1. [Problem](#2)
2. [Goals of the project¶](#3)
3. [Data Gathering and Methodology](#4) 
4. [Data Analytics and Conclusion](#5) 
5. [Time Plan from May 10 to May 19](#6) 
6. [References](#7)
   
# Problem
## 1. CORONAVIRUS pandemic is still with us! And hence Genomic surveillance is still ON!
## 2. Genome analysis from huge data sets is computationally intensive and takes time.
## 3. And this may delay responses to emerging deadly variants.

# Goals of the project
## 1. Build a python-based App/GUI for gene - variant calling to make the process of genomic surveilance and variant tracking more efficient.
## 2. Apply  Machine Learning Tools to predict variant, new(novel)/recurrent gene mutations in sequences.

# Data Gathering and Methodology
1. Dataset is publicly available in GISAID dataset (https://gisaid.org/).
2. Description of the dataset

**The column headings and their descriptions are listed here:**

**width:** The length of the genome as a string.

**names:** name of the genome. The GISAID names of genomes have in them date and country of origin

**seqs:** string of the genome cDNA. 

**Derived columns: Other columns are derived by using the hCoV-19 python-based App

**date:** date derived from column 'name'. 

**country:** country derived from column 'name'.

**gene_cdna:** cDNA coding sequences of gene retrieved from the seqs

**gene_cdna_width:** length of cDNA coding sequences of gene retrieved from the seqs.

**gene_aa:** amino acid (aa) coding sequences translated from gene retrieved from the seqs

**gene_aa_width:** length of amino acid (aa) coding sequences translated from gene retrieved from the seqs.

**type:** whether the sequence id a wild type or a variant.


**variant_columns:** variant calling. What name of variant it is, otherwise its 'Other'.

3. **Download complete genome datasets** from the GISAID database for samples collected in  Germany from Jan 2021 to April 2023.
    - complete genome sequences and with complete date of collection 
4. Selected Python libraries will be used for EDA, data wrangling, GUI development and ML algorithms. 

## **Do data cleaning:**
    - identify and remove, where applicable the genomes with high sequence coverage, drop columns that are of low importance and may have noisy data e.g. non cDNA characters like N and X (for cDNA allowed characters are: ATCG)
    - decide on the interesting features to keep for prediction analysis
## **Carry out EDA and provide dataset summary:** 
    - Interesting feature for lengths of cDNA and lengths of protein Amino acids    
## **Reveal the bigger picture:** 
     - Relate the data to the opportunity for hCov-19 genomic survelillance.
     - Conclusion/Recommnedation about the prediction on its robustness on the prediction and if there are open questions.
     - Conclusion.
     

# Data Analytics and Conclusion
### What the gene -variant caller App does?
- Read fasta files
- Variant calling  
- gene calling, the 12 genes from fasta files
- Viewtree for the data
- sort the treeview by the first column 'entry'
- Clear viewtree content
- Search tool for the tree content
- Export the treeview data as csv file
- Filter the dated data by date
- view other standard data from csv, text, excel files

### What do the ML analyses reveal?
- gene mutation prediction?
- Recurrent mutation?
- variant predictions?
-
   -- Accuracy
   -- Recall
   -- Precision
   -- R square
### The bigger picture for the future?
- Gene-Variant GUI App
- ML analyses
       
## Time Plan from May 10 to May 19 

### 1st Day Wednesday May 10, 2023
- Present the proposed Project
- Gather data
- Preliminary data exploration subset of dataset for ML analysis
- Pipeline for ML analysis 
- Work on the App to refine it 
### 2nd Day:Thursday May 11, 2023 
- Collating the datasets
- Exploring the dataset
- Further preliminary data exploration subset of dataset for ML analysis
- Pipeline for ML analysis for different models
- Finalize the App for variant calling to capture most of the Variants of Concern (VOC) or subvariants since November 2021
###  3rd Day: Friday May 12, 2023  
- gene and variant calling for bigger dataset
- Collating the datasets
- Exploring and checking usefulness
### 4th Days: Monday May 15, 2023  
- Gather final data for ML datasets from data got from by gene/variant calling
- EDA for genome selections for ML analysis
- EDA for feature selection for Ml analysis
### 5th Day: Tuesday May 16, 2023 
- ML analysis 
### 6th Day: Wednesday May 17, 2023 
- ML analysis
- Final Results Interpretation
- Presentation Preparation
### 7h Day: Thursday May 18, 2023
- Final Results Interpretation
- Presentation Preparation
### 8th Day: Friday May 19, 2023
- Presentation of Final Project


#  References
