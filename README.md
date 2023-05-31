# Final_Project: Efficient hCoV-19 Variant Identification Made Easy: Introducing the Gene-Variant Caller App integrated with ML Model
# Abstract
The emergence of human coronavirus (hCoV-19) variants raises concerns about their impact on transmissibility, virulence, diagnostic tools, and vaccine efficacy. Genomic surveillance is crucial for early detection, characterization of these mutations, and timely implementation of effective control strategies. In this study, the gene-variant caller app, a user-friendly tool for hCoV-2 genomic analysis was developed. The app integrates a trained Random Forest Machine Learning (ML) model to complement the application in variant identification. To validate its accuracy, publicly available worldwide genomic data from the GISAID (Global Initiative on Sharing All Influenza Data) database collected from April 1st to May 17th 2023 to track the emergence of Omicron subvariant Arcturus (XBB.1.16) were used. The results demonstrate the gene-variant caller's and ML model’s efficiency in identifying hCoV-19 variants from hCoV-19 genomic sequences. The Gene-Variant Caller app is a standalone tool that facilitates efficient tracking and identification of variants in large genomic datasets. It can be used to complement other existing tools to address the emergence of deadly hCoV-19 variants. The initial version of the app is now publicly available for Windows operating system. User feedback is encouraged to enhance its future development.
 

## By Evans Rono, PhD. Email: ronoevan@gmail.com
###May 2023: in the Ironhack, Berlin:
### Coronavirus GENE - VARIANT Caller App and Machine Learning Approaches for Efficient Genomic Surveillance and Prediction Analyses
### Dataset: hCoV-19 (Coronavirus) complete genome Sequences from GISAID database!

##  Table of Contents

1. [Problem](#2)
2. [Goals of the project¶](#3)
3. [Data Gathering and Methodology](#4) 
4. [Data Analytics and Conclusion](#5) 
5. [Time Plan from May 10, 2023 to May 19, 2023](#6)
6. [How to use the Gene-Caller App version 1.0a or 1.0b](#7)
7. [References](#8)
   
# Problem
## 1. CORONAVIRUS pandemic is still with us! And hence Genomic surveillance is still ON!
## 2. Genome analysis from huge data sets is computationally intensive and takes time.
## 3. And this may delay responses to emerging deadly variants.

# Goals of the project
## 1. Build a python-based App/GUI for gene - variant calling to make the process of genomic surveilance and variant tracking more efficient.
## 2. Apply  complementary Gene-Variant calling with a Machine Learning Tools trained to predict variant, new(novel)/recurrent gene mutations in the sequences.

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
### What the gene -variant caller App aimed to do?
- Read fasta files
- Variant calling  
- gene calling, the 12 genes from fasta files
- Viewtree for the data
- sort the treeview by the first column 'index'
- Clear viewtree content
- Search tool for the tree content
- Export the treeview data as csv file
- Filter the dated data by date
- Import/Export: To view or save standard data in csv files

### What do the ML analyses reveal?
- gene mutation prediction?
- Recurrent mutation?
- variant predictions?
-
   -- Accuracy
   -- Recall
   -- Precision
   -- R square
   
   
## Results: With different classifiers

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
       
# Time Plan from May 10, 2023 to May 19, 2023

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

### 4th Days: Monday May 15, 2023:  DONE
- Further expoloration and validation of Machine Learning Algorithms in final data for ML datasets from data got from by gene/variant calling
- Implement the GUI App to capture the modeling and prediction functions.
### 5th Day: Tuesday May 16, 2023:  DONE
- ML analysis continued 
### 6th Day: Wednesday May 17, 2023:  DONE
- ML analysis
- Preliminary Results Interpretation
- Draft of Presentation Preparation
### 7h Day: Thursday May 18, 2023:  DONE
- Final Results Interpretation
- Final Presentation Preparation
### 8th Day: Friday May 19, 2023:  DONE
- Presentation of Final Project. The project was voted among the top 3 best projects.

# Features, functionality and how to use the Gene-Caller App version 1.0a and version 1.0b
- It should be downloaded together with the saved pickle file.
- The saved pickle file is the trained ML Random Forest model and should be saved together in the same folder with the app.
- This will allow the App to access it when running the model for variant prediction.
- Two initial versions (v1.0a and v1.0b) with and without a console. 
- In v1.0a, genome and spike nucleotide columns are retained in the analysis, recommended when analysing less than 10,000 complete genome sequences. 
- While v1.0b drops these columns for faster downstream analysis, recommended when analysing  over 10,000 complete genome sequences. 
- Users of v1.0b can trace back the nucleotides using genome names.
- The console option is valuable for user to identify errors that may arise during the analysis.
- App has the ability to read GISAID Fasta files, which are widely used for storing hCoV-19 genome sequences. 
- The app does data cleaning and preprocessing capabilities to ensure that the data is properly formatted and ready for analysis. 
- The app offers a specialized gene-variant calling feature that is specifically designed for the GISAID dataset.
- The app supports gene-variant calling not only for GISAID sequences but also for other Fasta cDNA sequence data. 
- Users can extract specific genes of interest from the genome sequences using the app's gene extraction feature. 
- The app utilizes a trained Random Forest machine learning model to complement Gene-Variant Caller in identifying variants.
- The users to compare the results and performance of the Caller itself with the Random Forest machine learning model.
- The app does variant tracking, allowing users to monitor and analyze the prevalence and dynamics of specific variants over time.
- A keyword search functionality is integrated into the app, enabling users to quickly locate specific information within the dataset. 
- The app's graph plotting feature also provides an intuitive way to visualize the spread and distribution of variants within the dataset.
- Data CSV import and export functionalities are available.
- Users working with GISAID dataset, can filter the data based on date ranges. 
- Other features include sorting functionality of the treeview display of the dataset using the first column ‘index’ 
- Ability to clear the treeview and search area
- Overall, the Gene-Variant Caller App provides researchers and analysts with a comprehensive suite of tools and features to support their study of hCoV-19 genomic variations. 
- It empowers users to uncover valuable insights and contribute to a deeper understanding of the virus.
- The Gene-Variant Caller app is a standalone tool that facilitates efficient tracking and identification of variants in large genomic datasets.
- It can be used to complement other existing tools to address the emergence of deadly hCoV-19 variants. 
- The initial version of the app is now publicly available for Windows operating system. 
- User feedback is encouraged to enhance its future development.
- The Gene-Variant Caller App is finally unveiled: https://drive.google.com/file/d/1wJr9bk5hVIZVILIrAmkMrqCHItT51y6O/view?usp=drive_web




#  References
