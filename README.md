# ada-2021-project-adacadabra

Lien tableau Trello : https://trello.com/invite/b/sVkiju6l/95ca74a3fa2c4efd30a7d1e7ce646f25/milestone-2



- Title :
    
Exploratory analysis of the use of informal language in English speaking newspapers
    
- Abstract: A 150 word description of the project idea and goals. What’s the motivation behind your project? What story would you like to tell, and why?
    
- Project idea :

- Goals : Find relations between the use of informal langage and some metadata (politic orientation, occupation,  of the speaker
    
- Motivations: langue vivante evoluate always, constat que le langage familier (link scienfitc paper) 
        We constated that the informal language is more and more present in the public debate space. [other idea of motivation] For example, the speach of Donal Trump is base on massive utilization of informal words and expressions. The informal language (also called colloquial) is  Therefore, we will try to confirm this hypothesis and underlines some keys predictors. 
        
- Story : 1. present quotebank : geographical representation, standard stastitics. 2. Results on informal language classification : method and index used, graphical repartition (PCA, clustering)... 3. Statistical analysis : depending on the results, focus on an interesting relation with metadata
    
- Research Questions: A list of research questions you would like to address during the project.

--> link to papers 

Does the politic orientation affects the use of informal language ?

Does the occupation place has an influence on using the colloquial language ?

Does the standrd metric (age, gender, nationality) has any influence on the studied topic ?

Do some paper favorize the presence of informal langage or try to limit it ?
    
- Proposed additional datasets (if any): List the additional dataset(s) you want to use (if any), and some ideas on how you expect to get, manage, process, and enrich it/them. Show us that you’ve read the docs and some examples, and that you have a clear idea on what to expect. Discuss data size and format if relevant. It is your responsibility to check that what you propose is feasible.
    
- Methods : 

Taking in account the None

Data evaluation with the ML (?) model

Classification : - 
    
- Proposed timeline 

22.10 -> 29.10 : 
- review of the ideas proposed in M1 for each team member. 
- Data wrangling : - how retrieving the dataset - how to use the metadata from wikidata - how to retrieve informations on papers used --> link fichier notebook
- Methods : explore the different techniques (PCA, idt) to classify words.


29.10 -> 05.11

- Creation of common sample set (about 600 000 quotes) to test uniformly our methods (wrangling, classification, analysis)
- Retrieval and data wrangling on metadata from Wikidata. + statistics 
- Compute statistics on the metadata to better understand the quotebank dataset. 
- Data Wrangling on quotations : drop nan, drop quotes with p_attribution < threshold, consistent types, unique identifiers, 

05.11 -> 12.11 

- Focus on the method to distinguish formal and informal language
- Apply it to the sample 
- Clean readme and notebooks of code

    
- Organization within the team: A list of internal milestones up until project Milestone 3.

01.12 -> 17.12

- Compute the statistics and vizualisation between dataset and the metadata
- Create a storytelling in the website
    
- Questions for TAs: Add here any questions you have for us related to the proposed project.

