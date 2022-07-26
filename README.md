# EHRs-K-Cluster
Built lazy K-Clustering model on MIMIC-III Electronic Health Records with BERT tokenizer

# Electronic Health Records Data
Data is part of the MIMIC-III demo dataset, containing 299 deidentified Electronic Health Records (EHRs). 

# Data Cleaning
First, duplicate EHRs are removed. Then each EHR (String) is split into sentences/phrases (list). These sentences/phrases are embedded and tokenized using BERT SentenceTransformer. Resulting arrays are padded with np.zeros to achieve uniform dimensions, and flattened to reduce to two dimensions. 

# K-Clustering Model
Cleaned data are fitted to K-Means Clustering model and visualized with 2 variables: number of tokens (before padding) and average embedding value. Number of tokens before padding reflects the length of the EHR, which should correlate strongly with clustering. Average embedding value is calculated for each EHR by taking the average embedding values of each sentence/phrase in the EHR, then taking the aggregated average for the whole EHR. 

# Results
Found two main clusters, allowing for further exploration of characteristics of each cluster. 
