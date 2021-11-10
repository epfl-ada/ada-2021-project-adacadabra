# ada-2021-project-adacadabra

Lien tableau Trello : https://trello.com/invite/b/sVkiju6l/95ca74a3fa2c4efd30a7d1e7ce646f25/milestone-2



#### Title :
    
Exploratory analysis of the use of informal language in English speaking newspapers
    
#### Abstract:
A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?

<hr> 

#### Project idea : 
The dataset could be used to identify an evolution of the use of informal language through time in the media. If put into prospective with the context of use, it could help detect long term changes or phenomena. We will try to understand how the importance of formal language evolves when making public statements. 
By comparing the use of informal language within newspapers rather than across time, it could be possible to evaluate a component of the journalistic quality of different sources or caracteristics of the speaker directly.

#### Goals :
Find relations between the use of informal langage and some metadata (politic orientation, occupation,  of the speaker).
    
#### Motivations:
The idea for this project was born out of a general observation by a member of the group: the interview or newspaper archives give the impression that the language used was more formal than that used today. In other words, the langage is in constant evolution and the usage of colloquial langage appears more and more frequently in the public debate. For example, the speech of Donald Trump during the two latest US electoral campaign is based on massive utilization of slang words and expressions, as it can be seen in the nicknames he regularly gave to his opponents (like "Sleppy Joe" or "CrazyHillary")
[https://en.wikipedia.org/wiki/List_of_nicknames_used_by_Donald_Trump].

Given this intuition, the informal language appears an interesting subject to focus on, and the next step was to study how to easily detect the use of colloquial language. Thanks to research and discussions with a graduate student in English literature, it appears that the usage of informal language is mainly linked to the usage of a specific vocabulary. [reference ?] Therefore, the large number of quotations containing in the Quotebank dataset seems to offer a great opportunity to obtain a general overview on these aspects
        
#### Story : 
1. present quotebank : geographical representation, standard stastitics.
2. Results on informal language classification : method and index used, graphical repartition (PCA, clustering)...
3. Statistical analysis : depending on the results, focus on an interesting relation with metadata
    
#### Research Questions:
A list of research questions you would like to address during the project. --> link to papers

    - Can the use of informal language provide information about political orientation (via wikidata) ?

    - Does the professional occupation /political party has an influence on the use the colloquial language (via wikidata) ?

    - Do the standard metrics (age, gender, nationality) have any influence on the studied topic (via wikidata) ?

    - Do some newspapers favorize the presence of informal langage or try to limit it ? What does it tell us about journalistic quality of the data sources (via WHOIS requests) ? --> à reformuler
    
#### Proposed additional datasets:
List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.

- Speakers metadata : Using the provided parquet file, the informations (gender, age, occupation, nationality, religion ...) of each speakers were extracted (cf. SPEAKERS_METADATA/Retrieve_metadata.ipynb) The parquet file was converted into a pandas dataframe and the QIDs into meaningful informations thanks to the lookup table provided.

- Newspapers metadata : explain the 
    
#### Methods :

[insert the image of drawio diagramm]

Defining a sample to handle datasize (notebook ...)

DataWrangling (see Notebook *Data Wrangling Quotebank.ipynb*)

    * Suppression of quotes according the following criteria
           
           - have meaningless probabilities ($p \notin [0,1]$)
           - is not clearly identified (threshold to be defined: *threshold_min*)
           - is probably confused with another speaker (threshold to be defined: *threshold_diff*)
           - is not identified (None values)

Data evaluation with models (see Notebook *methods_language_processing.ipynb*)

Classification (see Notebook ...): [to be described]

Analysis : What analysis we will make in M3?
    
#### Proposed timeline 

22.10 -> 29.10 : 

    - review of the ideas proposed in M1 for each team member. 
    - Data wrangling : - how retrieving the dataset - how to use the metadata from wikidata - how to retrieve informations on papers used --  > link fichier notebook
    - Methods : explore the different techniques (PCA, idt) to classify words.

<hr>

29.10 -> 05.11

    - Creation of common sample set (about 600 000 quotes) to test uniformly our methods (wrangling, classification, analysis)
    - Retrieval and data wrangling on metadata from Wikidata. + statistics 
    - Compute statistics on the metadata to better understand the quotebank dataset. 
    - Data Wrangling on quotations : drop nan, drop quotes with p_attribution < threshold, consistent types, unique identifiers, 

<hr>

05.11 -> 12.11 

    - Focus on the method to distinguish formal and informal language
    - Apply it to the sample 
    - Clean readme and notebooks of code

    
#### Organization within the team: 
A list of internal milestones up until project Milestone 3.
Link to Trello : https://trello.com/invite/b/sVkiju6l/95ca74a3fa2c4efd30a7d1e7ce646f25/milestone-2

01.12 -> 17.12

    - Compute the statistics and vizualisation between dataset and the metadata
    - Create a storytelling in the website
    
#### Questions for TAs: 
Add here any questions you have for us related to the proposed project.

