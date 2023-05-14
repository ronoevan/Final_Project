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
   
   
# Results: With different classifiers

### 1. Random Forest Classifier
1. Both the cDNA and Amino acid prediction with spike give >99.5% accuracy
2. But the prediction is correctly predicted with Amino acid seqs.
3. cDNA seq predctions give all the variants predicted on unseen sequence as 'other'.
4. So the better way is to use amino acid sequences for prediction of the variants and probability of getting having new mutations in a sequences consistent to each class (variant).
5. Overally, Random Forest gives the best prediction of >99.5%, and predicts correctly with spike amino acids, and can get the probability of getting new mutations.
6. Because of large sizes of sequences as string, reducing thenumber by dropping duplicates was helpful to reduce the size of file and time taken to computer and reduces the chances of running out of the memory of the computer.

### 2. Support Vector Machines (SVMs)
1. Gave an accuracy of 99.67%, and give the correct prediction on the correct sequences (new) 
2. But if the sequence of is wrong or dammy sequence, then it predicts it as omicron, which is wrong. 
3. Hence not robust in prediction of new sequences.

### 3. Naive Bayes
1. Accuracy of 51.6%
2. Hence not robust enough.

### 4. Neutral Network models
1. All the different neutral network models did not compute in my computer.  The python kernel died
2. Possible because of one-hot encoding that needed alot of computations and increase in dimensionality of the data
3. Hence the memory of the computer became limited.



### The bigger picture for the future?
- Gene-Variant GUI App
- ML analyses
       
## Time Plan from May 10 to May 19 

### 1st Day Wednesday May 10, 2023: DONE
- Present the proposed Project
- Gather data
- Preliminary data exploration subset of dataset for ML analysis
- Pipeline for ML analysis 
- Work on the App to refine it 
### 2nd Day:Thursday May 11, 2023: DONE
- Collating the datasets
- Exploring the dataset
- Further preliminary data exploration subset of dataset for ML analysis
- Pipeline for ML analysis for different models
- Finalize the App for variant calling to capture most of the Variants of Concern (VOC) or subvariants since November 2021
- EDA for genome selections for ML analysis
- EDA for feature selection for Ml analysis
###  3rd Day: Friday May 12, 2023: DONE
- gene and variant calling for bigger dataset
- Collating the datasets
- EDA for genome selections for ML analysis
- EDA for feature selection for Ml analysis
- Exploring and checking usefulness
- Documenting the results from different modeling algorithms

### 4th Days: Monday May 15, 2023  
- Further expoloration and validation of Machine Learning Algorithms in final data for ML datasets from data got from by gene/variant calling
- Implement the GUI App to capture the modeling and prediction functions.
### 5th Day: Tuesday May 16, 2023 
- ML analysis continued 
### 6th Day: Wednesday May 17, 2023 
- ML analysis
- Preliminary Results Interpretation
- Draft of Presentation Preparation
### 7h Day: Thursday May 18, 2023
- Final Results Interpretation
- Final Presentation Preparation
### 8th Day: Friday May 19, 2023
- Presentation of Final Project


#  References
