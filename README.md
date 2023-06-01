# Final_Project: 
# Efficient hCoV-19 Variant Identification Made Easy: Introducing the Gene-Variant Caller App integrated with ML Model
# Abstract
The emergence of human coronavirus (hCoV-19) variants raises concerns about their impact on transmissibility, virulence, diagnostic tools, and vaccine efficacy. Genomic surveillance is crucial for early detection, characterization of these mutations, and timely implementation of effective control strategies. In this study, the gene-variant caller app, a user-friendly tool for hCoV-2 genomic analysis was developed. The app integrates a trained Random Forest Machine Learning (ML) model to complement the application in variant identification. To validate its accuracy, publicly available worldwide genomic data from the GISAID (Global Initiative on Sharing All Influenza Data) database collected from April 1st to May 17th 2023 to track the emergence of Omicron subvariant Arcturus (XBB.1.16) were used. The results demonstrate the gene-variant caller's and ML model’s efficiency in identifying hCoV-19 variants from hCoV-19 genomic sequences. The Gene-Variant Caller app is a standalone tool that facilitates efficient tracking and identification of variants in large genomic datasets. It can be used to complement other existing tools to address the emergence of deadly hCoV-19 variants. The initial version of the app is now publicly available for Windows operating system. User feedback is encouraged to enhance its future development.
 

## By Evans Rono, PhD. Email: ronoevan@gmail.com
###May 2023: in the Ironhack, Berlin:
### Coronavirus GENE - VARIANT Caller App and Machine Learning Approaches for Efficient Genomic Surveillance and Prediction Analyses
### Dataset: hCoV-19 (Coronavirus) complete genome Sequences from GISAID database!

##  Table of Contents

1. [Abstract](#1)
2. [Problem](#2)
3. [Goals of the project¶](#3)
4. [Data Gathering and Methodology](#4) 
5. [Data Analytics and Conclusion](#5) 
6. [Time Plan from May 10, 2023 to May 19, 2023](#6)
7. [How to use the Gene-Caller App version 1.0a or 1.0b](#7)
8. [References](#8)
   
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
1. Both the cDNA and Amino acid prediction with spike give >99.5% accuracy.
2. cDNA seq predctions give all the variants predicted on unseen sequence as 'other'.
3. Good enough, the prediction correctly predicted with the Amino acid seqs. So training the model nucleotide sequences was dropped in favour of amino acid sequences.
4. So the better way is to use amino acid sequences for prediction of the variants and probability of getting having new mutations in a sequences consistent to each class (variant).
5. Overally, Random Forest gives the best prediction of >99.5%, and predicts correctly with spike amino acids, and can get the probability of getting new mutations.
6. Because of large sizes of sequences as string, reducing the number by dropping duplicates was helpful to reduce the size of file and time taken to computer and reduces the chances of running out of the memory of the computer.

### 2. Support Vector Machines (SVMs)
1. Gave an accuracy of 99.67%, and give the correct prediction on the correct sequences (new) 
2. But if the sequence of is wrong or dammy sequence, then it predicts it as omicron, which is interesting, and require in-depth investigation. 
3. Hence its robustness in this case was doubtful, even though it has high accuracy in prediction of new sequences. Will come to it later as a side project to find out more about this scenario.

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

# Availability and Implementation of the Gene-Caller App version 1.0a and version 1.0b
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
- **Limitations of Gene Variant Caller App include:**
- Limitation 1. The Gene-Variant calling process, relies on 100% spike sequence coverage for variant identification. During the cleaning process, gene sequences with sequencing errors or low coverage are eliminated.
- Limitaion 2. The need to drop genome columns to reduce processing time for large datasets.  
- Limitation 3. While the study catalogued and used a few known variants, there is a need for improvement by expanding the variant list to include all known and relevant variants, thereby enhancing performance. 
- Limitation 4. Gene-Variant Caller cannot directly identify unknown variant but it groups it among ‘Other’ variants. This requires additional analysis to characterize the new or unknown variants.
- The Gene-Variant Caller App is finally unveiled: https://drive.google.com/file/d/1wJr9bk5hVIZVILIrAmkMrqCHItT51y6O/view?usp=drive_web

# Acknowledgements
I express profound appreciation to the global research community for their dedication to hCoV-19 genome sequencing and open sharing of data through NCBI, GISAID and other website outlets. Special thanks to NCBI and GISAID for providing access to the genomic data repository, pivotal in developing the Gene-Variant Caller App.
I am grateful to my family for their unwavering support during the app's development. Their patience, understanding and encouragement during challenging times, including some sleepless nights have been invaluable.
I immensely thank my mentors Alex Boski, Leo Krohne, and Sandra Hernandez for their guidance. I appreciate the valuable input from colleagues and friends that has significantly enhanced the app.
This project is a result of collective support and collaboration. I am thankful to everyone involved and excited to share the app with the scientific community, hoping it would contribute to hCoV-19 variant analysis and research.



#  References
1. Zhu, N. et al. A Novel Coronavirus from Patients with Pneumonia in China, 2019. New England Journal of Medicine 382, 727–733 (2020).

2.	Cucinotta, D. & Vanelli, M. WHO Declares COVID-19 a Pandemic. Acta Biomed 91, 157–160 (2020).

3.	Gorbalenya, A. et al. The species Severe acute respiratory syndrome-related coronavirus: classifying 2019-nCoV and naming it SARS-CoV-2. Nat Microbiol 5, (2020).

4.	Wu, F. et al. A new coronavirus associated with human respiratory disease in China. Nature 579, 265–269 (2020).

5.	Jamil, S. et al. Genetic variants of SARS-CoV-2: What do we know so far? Am J Respir Crit Care Med 203, (2021).

6.	McCrone, J. T. et al. Context-specific emergence and growth of the SARS-CoV-2 Delta variant. Nature 610, 154–160 (2022).

7.	Khandia, R. et al. Emergence of SARS-CoV-2 Omicron (B.1.1.529) variant, salient features, high global health concerns and strategies to counter it amid ongoing COVID-19 pandemic. Environ Res 209, 112816 (2022).

8.	Hadfield, J. et al. Nextstrain: real-time tracking of pathogen evolution. Bioinformatics 34, 4121–4123 (2018).

9.	GISAID. GISAID. https://www.gisaid.org/ (2023).

10.	O’Toole, Á. et al. Assignment of epidemiological lineages in an emerging pandemic using the pangolin tool. Virus Evol 7, veab064 (2021).

11.	Orton, R. CoV-GLUE: enabled by data from GISAID. https://cov-glue.cvr.gla.ac.uk/index.php (2021).

12.	Elbe, S. & Buckland-Merrett, G. Data, disease and diplomacy: GISAID’s innovative contribution to global health. Global Challenges 1, 33–46 (2017).

13.	Tegally, H. et al. Detection of a SARS-CoV-2 variant of concern in South Africa. Nature 592, 438–443 (2021).

14.	Tegally, H. et al. Sixteen novel lineages of SARS-CoV-2 in South Africa. Nat Med 27, 440–446 (2021).

15.	ECDC. Sequencing of SARS-CoV-2 - first update.
 
https://www.ecdc.europa.eu/en/publications-data/sequencing-sars-cov-2 (2021).

16.	GISAID. Delta variant. https://www.gisaid.org/hcov19-variants/ (2021).

17.	WHO. The effects of virus variants on COVID-19 vaccines. https://www.who.int/news-room/feature-stories/detail/the-effects-of-virus-variants-on-covid-19-vaccines?gclid=CjwKCAjw-sqKBhBjEiwAVaQ9azeXfBJUkJAMRUAYSG-Z9mQziqRWzpkDVBD8-wFLoykiLqqng0YBCBoCKN0QAvD_BwE (2021).

18.	Abdool Karim, S. S. & de Oliveira, T. New SARS-CoV-2 Variants — Clinical, Public Health, and Vaccine Implications. New England Journal of Medicine 384, 1866–1868 (2021).

19.	WHO. XBB.1.16 Initial Risk Assessment. https://www.who.int/docs/default-source/coronaviruse/21042023xbb.1.16ra-v2.pdf (2023).

20.	Foundation., P. S. Python 3.11.3 Documentation. Python 3.11.3 Documentation https://www.python.org/doc/3.11.3/ (2023).

21.	Rono, E. K. Covid-19 genomic analysis reveals clusters of emerging sublineages within the delta variant. bioRxiv 2021.10.08.463334 (2021) doi:10.1101/2021.10.08.463334.
22.	Breiman, L. Random Forests. Mach Learn 45, 5–32 (2001).

23.	Aerzteblatt.de. SARS-CoV-2: New variant XBB.1.16 arrived in the USA and England. Arcturus XBB.1.16 https://www.aerzteblatt.de/nachrichten/142683/SARS-CoV-2-Neue-Variante-XBB-1-16-in-den-USA-und-England-angekommen (2023).

24.	Rono, E. K. Covid-19 genomic analysis reveals clusters of emerging sublineages within the delta variant. bioRxiv 2021.10.08.463334 (2021) doi:10.1101/2021.10.08.463334.

25.	Foundation, P. S. re — Regular expression operations. re — Regular expression operations (2021).

26.	Mckinney, W. Data Structures for Statistical Computing in Python. http://conference.scipy.org/proceedings/scipy2010/mckinney.html (2010).

27.	ViralZone. Sars-CoV-2 circulating variants. Sars-CoV-2 circulating variants https://viralzone.expasy.org/9556 (2023).

28.	Control, E. C. for D. P. and & Union, A. agency of the E. SARS-CoV-2 variants of concern as of 04 May 2023. SARS-CoV-2 variants of concern as of 04 May 2023 https://www.ecdc.europa.eu/en/covid-19/variants-concern (2023).

29.	WHO. WHO announces simple, easy-to-say labels for SARS-CoV-2 Variants of Interest and Concern. (2021).

30.	WHO. Tracking SARS-CoV-2 variants. https://www.who.int/en/activities/tracking-SARS-CoV-2-variants/ (2021).

31.	Cock, P. J. A. et al. Biopython: Freely available Python tools for computational molecular biology and bioinformatics. Bioinformatics 25, 1422–1423 (2009).

32.	Hunter, J. D. Matplotlib: A 2D Graphics Environment. Comput Sci Eng 9, 90–95 (2007).

33.	Waskom, M. seaborn: statistical data visualization. J Open Source Softw 6, 3021 (2021).

34.	Rumelhart, D. E., Hinton, G. E. & Williams, R. J. Learning representations by back-propagating errors. Nature 323, 533–536 (1986).

35.	Rish, I. An Empirical Study of the Naïve Bayes Classifier. IJCAI 2001 Work Empir Methods Artif Intell 3, (2001).

36.	Cortes, C. & Vapnik, V. Support-vector networks. Chem. Biol. Drug Des. 297, 273–297 (2009).

37.	Pedregosa, F. et al. Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research vol. 12 http://scikit-learn.sourceforge.net. (2011).

38.	Foundation, P. S. pickle — Python object serialization. pickle — Python object serialization https://docs.python.org/3/library/pickle.html (2021).

39.	Mendeley. Stay on top of your research. https://www.mendeley.com/reference-management/mendeley-desktop (2023).

40.	Castellano, S. et al. iVar, an Interpretation-Oriented Tool to Manage the Update and Revision of Variant Annotation and Classification. Genes (Basel) 12, 384 (2021).

41.	Wilm, A. et al. LoFreq: a sequence-quality aware, ultra-sensitive variant caller for uncovering cell-population heterogeneity from high-throughput sequencing datasets. Nucleic Acids Res 40, 11189–11201 (2012).



