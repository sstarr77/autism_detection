# Detecting the Presence of Autism Spectrum Disorder

-----------


## What is Autism Spectrum Disorder
NIH describes Autism Spectrum Disorder as being: "A neurological and developmental disorder that affects how people interact with others, communicate, learn, and behave. Although autism can be diagnosed at any age, it is described as a “developmental disorder” because symptoms generally appear in the first two years of life." 


## Background
This project has an impact on my life because of my twin brother, who is on the spectrum. Initially, the project was going to be an autism prediction app; where upon the answering of a questionnaire on family history, a reply would autogenerate telling the user what percentage chance that their offspring would have of having autism spectrum disorder. This would have been done by inspecting the most syndromic genes in ASD using the Safari ASD gene database, and linking the genes to other disorders or diseases that share the same genetic makeup. 
Upon research, I discovered that similar assessements has already been done. Also, that it was a bigger task than expected. Mainly because there was no way to prove my theory. Therefore, I switched to solely using the gene data from the database to determine rather of not I could predict the presence of autism in an individual, and not if that individual would have offspring with ASD. My secodary data (SFARI data) became the primary data used for this project. Initially, I was worried this was not going to be enough data. But, I was able to construct an XGB Classification Model with 94% accuracy.


## XGBoost Machine Learning Algortihm
an XGBoost Classification Model is used heavily in production environments for it's speed and performance. It stands for eXtreme Gradient Boosting and is based on decision trees. For this project, I imported the XGBClassifier from the xgboost library-- which is scikit-learn's API for XGBClassification. 


## Library Requirements
For this project, I mainly used **numpy**, **scikit-learn**, **pandas**, and **xgboost**. 


## Process
The process:
 - Load the data from SFARI database
 - Get features and labels
 - Scale the features (and dummy the features)
 - Split the dataset
 - Build the XGBClassifier
 - Calculate the model accuracy
 
 
## Dataset
For this project, I used the SFARI human gene database. This is a database specifically for the autism research community. It is cenetered on genes implicated in autism susceptibility. 


## Detailed Discoveries  
- My model showcased that the relationship between the two variables represent a genetic network. This means that there are multiple inputs for multiple outputs. In other words, my data had a many-to-many relationship with itself. What this means is that multiple chromosomes show multiple ASD related syndromes. 

- There were 793 syndromic cases, and 239 non-syndromic cases.

- There were 477 score 3 genes, 206 score 1 genes, 198 score 2 genes, and 150 actual syndromic genes.

- The overall most reported gene score is gene score number 1 (high confidence). 

- The most common gene score in those with ASD based on this dataset is gene score 3 (suggestive evidence). 

- The main gene mutated in individuals with syndromic ASD tends to be the X gene. 

- There are multiple chromosomes with multiple syndromic chromosome frequencies.

- The most common overall mutated gene in the dataset is gene number 2.

- The rare, syndromic, functional gene category had the highest number of reports. 


-------------------------------  

# In a Nutshell
I was able to use an XGBClassification Model to detect ASD in an individual upon inspection of their genes with 94% accuracy. 


# Future Work
Future work would consist on answering deeper questions such as rather or not each syndrome listed on one chromosome tends to be the same. In other words, what are the other variants of ASD? Or in what further ways does ASD manifest itself in genotype and phenotype? Also answering the question of why there be reports of ASD if the gene is not syndromic? For example: If a child had ASD but had no symptoms or syndromes... were they diagnosed only looking at genes? These are just a few of the questions I would love to answer in the future.
I would love to take this further into an application. Where someone could potentially take their gene data they receive from 23andMe or ancestry.com and input it, whereas the output would be rather or not the individual has ASD.
