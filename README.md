# ada-2021-project-adacadabra

Lien tableau Trello : https://trello.com/invite/b/sVkiju6l/95ca74a3fa2c4efd30a7d1e7ce646f25/milestone-2



### Title :
    
Exploratory analysis of the use of informal language in English speaking newspapers
    
### Abstract:
A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?

<hr> 

### Project idea : 
The dataset could be used to identify an evolution of the use of informal language through time in the media. If put into prospective with the context of use, it could help detect long term changes or phenomena. We will try to understand how the importance of formal language evolves when making public statements. 
By comparing the use of informal language within newspapers rather than across time, it could be possible to evaluate a component of the journalistic quality of different sources or caracteristics of the speaker directly.

### Goals :
Find relations between the use of informal langage and some metadata (politic orientation, occupation,  of the speaker).
    
### Motivations:
The idea for this project was born out of a general observation by a member of the group: the interview or newspaper archives give the impression that the language used was more formal than that used today. In other words, the langage is in constant evolution and the usage of colloquial langage appears more and more frequently in the public debate. For example, the speech of Donald Trump during the two latest US electoral campaign is based on massive utilization of slang words and expressions, as it can be seen in the [nicknames he regularly gave to his opponents](https://en.wikipedia.org/wiki/List_of_nicknames_used_by_Donald_Trump) (like "Sleppy Joe" or "CrazyHillary")
.

Given this intuition, the informal language appears an interesting subject to focus on, and the next step was to study how to easily detect the use of colloquial language. Thanks to research and discussions with a graduate student in English literature, it appears that the usage of informal language is mainly linked to the usage of a specific vocabulary. [reference ?] Therefore, the large number of quotations containing in the Quotebank dataset seems to offer a great opportunity to obtain a general overview on these aspects

<hr>
        
### Story : 

| Step | idea | Description  |
|:---------|:-----------|:-----------|
|1. | Presentation of Quotebank | geographical representation, standard stastitics with fancy representation to present the dataset to the visitor of the page |
|2. | Presentation of the method used to classify the quotes | description of the method and index used, results on the most used words, statistics on the frequency of each entry (Zipf law ?) |
|3. | Exploratory analyisis |explore the relation between the metadata and the classification of the quotes |
|4. | Identify the key correlation | Linear regression with coefficient which could have an influence on the output (informal/formal) | 
|5. | Explanatory study | choose a relation and investigate in depth how is it possible (or not) to explain it |
|6. | Conclusion | Highlight the fact that correlation ≠ to causation, limits on your study |
    
#### Research Questions:
A list of research questions you would like to address during the project. --> link to papers

 - Can the use of informal language provide information about political orientation (via wikidata) ?

 - Does the professional occupation /political party has an influence on the use the colloquial language (via wikidata) ?

 - Do the standard metrics (age, gender, nationality) have any influence on the studied topic (via wikidata) ?

 - Do some newspapers favorize the presence of informal langage or try to limit it ? What does it tell us about journalistic quality of the  data sources (via WHOIS requests) ? --> à reformuler
 
<hr>
    
### Proposed additional datasets:
List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.

- Speakers metadata : Using the provided parquet file, the informations (gender, age, occupation, nationality, religion ...) of each speakers were extracted (cf. `SPEAKERS_METADATA/Retrieve_metadata.ipynb`) The parquet file was converted into a pandas dataframe and the QIDs into meaningful informations thanks to the lookup table provided.

- Newspapers metadata : explain the 

<hr>
    
### Methods :
<center><img src="./test_diagram.drawio.svg"><center>
<center>Process flow diagram of the project</center> 

Defining a sample to handle datasize (see Notebook `Sample_creation.ipynb`)

DataWrangling (see Notebook `Data Wrangling Quotebank.ipynb`)

Suppression of quotes according the following criteria
      
- have meaningless probabilities ($p not in interval [0,1]$)
- is not clearly identified (threshold to be defined: *threshold_min*)
- is probably confused with another speaker (threshold to be defined: *threshold_diff*)
- is not identified (None values)

Classification (see Notebook `comparison_SlangDict_quotes.ipynb`): 
It consist simply to search for a specific word/expression from the dictionnary in each quotes of the dataset. If a match is found, the dictionnary is updated to contain the number of time the word had been found in the quotes. This value is then used to reduce the dictionnary size. Without this reduction all quotes are categorized as colloquial which is not surprising given the size of the dictionary used (>20'000 entries). This is why we will focus on the less frequently occurring terms (occuring in one quote in tousand), which will define a clearer distinction between formal and informal language.

Note that initially other method were also tested without much sucess (Vector space retrieval, word embeddings, ...). They are all presented in the following notebook: `CLASSIFICATION/Segmentation_model/methods_language_processing.ipynb` notebook. 

Analysis : What analysis we will make in M3?
    
#### Proposed timeline 

**22.10 -> 29.10** 

- review of the ideas proposed in M1 for each team member. 
- Data wrangling : - how retrieving the dataset - how to use the metadata from wikidata - how to retrieve informations on papers used --  > link fichier notebook
- Methods : explore the different techniques (PCA, idt) to classify words.

<hr>

**29.10 -> 05.11**

- Creation of common sample set (about 600 000 quotes) to test uniformly our methods (wrangling, classification, analysis)
- Retrieval and data wrangling on metadata from Wikidata. + statistics 
- Compute statistics on the metadata to better understand the quotebank dataset. 
- Data Wrangling on quotations : drop nan, drop quotes with p_attribution smaller than threshold, consistent types, unique identifiers, 

<hr>

**05.11 -> 12.11** 

- Focus on the method to distinguish formal and informal language
- Apply it to the sample 
- Clean readme and notebooks of code

<hr>
    
#### Organization within the team: 
A list of internal milestones up until project Milestone 3.
Platform for collaboration withing the team:
- [link to Trello](https://trello.com/invite/b/sVkiju6l/95ca74a3fa2c4efd30a7d1e7ce646f25/milestone-2)


**01.12 -> 17.12**

- Compute the statistics and vizualisation between dataset and the metadata
- Create a storytelling in the website
    
#### Questions for TAs: 
Add here any questions you have for us related to the proposed project.

