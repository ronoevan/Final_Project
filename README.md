# Final_Project
# Coronavirus GENE - VARIANT Caller App and Machine Learning Approaches for Efficient Genomic Surveillance and Prediction Analyses  

## Final_Project May 2023 in the Ironhack, Berlin
## By Evans
## Dataset: hCoV-19 (Coronavirus) complete genome Sequences from GISAID database!

##  Table of Contents
1. [Description of the dataset](#2)

1. [Goals of the project¶](#3)

2. [Data Gathering and Methodology](#4)
   
3. [Data Analytics and Conclusion](#5) 
   
4. [References](#6)

# Problem
## CORONAVIRUS pandemic is still with us! And hence Genomic surveillance is still ON!
## Genome analysis from huge data sets is computationally intensive and takes time.
## And this may delay responses to emerging deadly variants.

# Goals of the project
## Build a python-based App/GUI for gene - variant calling to make the process of gene and variant calling efficient.
## Apply  Machine Learning Tools to predict variant, new(novel)/recurrent gene mutations in sequences.

# Data Gathering and Methodology
1. Dataset is publicly available in GISAID dataset (https://github.com/).
2. **Download complete genome datasets** from the GISAID database for samples collected in  Germany from Jan 2021 to April 2023.
    - complete genome sequences and with complete date of collection 
3. Selected Python libraries will be used for EDA and for data wrangling. 
 
## **Do data cleaning:**
    - identify and remove, where applicable the genomes with sequence coverage, drop columns with low importance and noisy data
    - decide on the interesting features to keep for prediction analysis

## **Carry out EDA and provide dataset summary:** 
    - Interesting feature for lengths of cDNA and lengths of protein Amino acids 

    
## **Reveal the bigger picture:** 
     - Relate the data to the opportunity for hCov-19 genomic survelillance.
     - Recommnedation about the prediction whether on robustness of the prediction and if there are open questions.
     - Conclusion.
     

#  Description of the dataset
The dataset used to complete this project was scraped in 2016 from ebay-Kleinanzeigan (Germany).
The data was made available publicly on the Kaggle by the user 'orgesleka'. 

The dataset contains seventeen columns with over 37 thousand rows of private used car listings for sale; 
the column headings and their descriptions are listed here:

**width:** The length of the genome as a string.

**names:** name of the genome. The GISAID names of genomes have in them date and country of origin

**seqs:** string of the genome cDNA.

## From these columns, other columns are derived by the hCoV-19 python-based App

**date:** date derived from column 'name'.

**country:** country derived from column 'name'.

**gene_cdna:** cDNA coding sequences of gene retrieved from the seqs

**gene_cdna_width:** length of cDNA coding sequences of gene retrieved from the seqs.

**gene_aa:** amino acid (aa) coding sequences translated from gene retrieved from the seqs

**gene_aa_width:** length of amino acid (aa) coding sequences translated from gene retrieved from the seqs.

**type:** whether the sequence id a wild type or a variant.

**variant_columns:** variant calling. What name of variant it is, otherwise its 'Other'.

# Data Analytics and Conclusion

       
## Time Plan

### 1st Day:  
- Gather data 
- EDA for genome selections


###  2nd Day
- gene and variant calling
- EDA for feature selection


### 3rd Days
ML analysis

### 4th Day
- Analsis
- Presentation Preparation

#  References
