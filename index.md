# SMAFIRA Shared Task: <br> Assessing the similarity of the research goal

Some countries have strict legislation regarding the authorization of animal testing. 
For instance,   some require that researchers should comply with the so-called [3R principles](https://caat.jhsph.edu/the-principles-of-humane-experimental-technique/), i.e., strategies for   the replacement to non-animal approaches, reduction of the number of animals,   and refinement of the methods to reduce animal suffering. 
Further, many countries require researchers   to carry out a through literature search to ensure that alternative approaches are currently not available.

The [SMAFIRA project](https://www.bf3r.de/en/smafira___artificial_intelligence_for_finding_alternative_methods-297876.html) aims at supporting researchers to finding alternatives methods to animal experiments.
Recently, we released our [SMAFIRA Web tool](https://smafira.bf3r.de/) [1], which allows researchers to performance such a search.
The input to the tool is a PubMed identifier (PMID), hereafter called “reference article”, that represent the animal experiment for which they want to find an alternative method. 
The tool retrieves up to 200 similar articles, as available in PubMed, and present these as list of results. 

One of the processing tasks that is currently being carried out for the articles in SMAFIRA tool is the re-ranking of the articles based on the similarity of the research goal, as compared to the reference article. 
There are three possible values for the similarity: similar, uncertain, or not similar.

We propose a shared task for collaborative annotation of training data in the scope of the [BioNLP workshop](https://aclweb.org/aclwiki/BioNLP_Workshop).
We will release a list of various reference articles, grouped according to some pre-selected diseases (MeSH terms). 
The participants will validate the top 10 similar articles, either automatically, with any system of their choice, or manually using the SMAFIRA tool.

## Important dates

- Release of the test data: Dec/2024-Jan/2025
- Submissions of annotations: End of February, 2025
- Direct paper submission deadline: March 1, 2025 (To be confirmed)
- Pre-reviewed ARR commitment deadline: March 25, 2025 (To be confirmed)
- Notification of acceptance: April 3, 2025 (To be confirmed)
- Camera-ready paper due: May 2, 2025 (To be confirmed)
- Proceedings due (hard deadline): June 30, 2025
- Workshop dates: July 31st - August 1st 2025

## Data and annotation tool

### Available data
  
We previously released [four case studies](https://github.com/SMAFIRA/c_corpus) [2], which can be used by for any purpose, e.g., evaluation or few-shot approaches. 
We previously used this dataset for the evaluation of various similarity methods [3].
The mapping between the labels in the case studies and the similarity values is the following: 

- similar: equivalent "++", partially equivalent “+(+)”, noteworthy “+”
- not similar: limbo “L”, not equivalent “-”

### Annotation tool

The [SMAFIRA Web tool](https://smafira.bf3r.de/) is freely accessible and no login is necessary. 
Instead, the annotators can bookmark the URL of their session for later annotation or share the URL with other colleagues for a collaborative annotation.

### Test data

We pre-selected a list of 21 diseases, e.g., “Neoplasms” or “Musculoskeletal Diseases”, and their respective MeSH terms. 
We performed searches in Pubmed based on each disease, e.g., (Musculoskeletal Diseases[MeSH Major Topic]) 
AND (Models, Animal[MeSH Major Topic]), and manually selected five reference articles. 
The selected reference articles should describe a proper animal experiment and cannot be a review. 

For instance, the article with [PMID 37775153](https://pubmed.ncbi.nlm.nih.gov/37775153/) belongs to the topic of “Musculoskeletal Diseases” and studies the effect of the L-arginine metabolism on arthritis and inflammation-mediated bone loss. 
It proposes three methods, including transgenic mice (i.e., an animal experiment), but also in vitro methods.

## Annotation tasks

We will release the list of PMIDs, i.e., the reference articles. 
The participants will be free to pick any of the reference articles from any of the topics and perform annotation for the top 10 articles. 
A valid submission to the shared task should consist of the annotation of all articles in the top 10 for a particular reference article. 
The participants can submit annotations for as many reference articles as they wish.
The eannotation can be carried out manually or automatically.
For each of them, we will consider two types of evaluation:
(a) annotations of reference articles for a pre-selected list of five topics, in order to allow a better computation of an inter-annotation agreement; and 
(b) annotation of reference articles for any of the topics.

### Manual annotation task

The participant should enter the PMID into the SMAFIRA tool and validate the top 10 articles from the list (as ordered by the "SMAFIRA Rank", the default ranking) . 
By clicking on one PMID of the list, the tool opens a comparison page between the reference article (on the left) and the clicked article (on the right).
The participant should carefully read both abstract and assess the similarity of their research goal.
The annotation consist of simply clicking on one of one of the option at the top of the page: green thumb up (similar), thumb up/down (uncertain), or thump down (not similar).
It is possible to go back to the list of results at any time and navigate between the articles using the next/previous arrows, both found at the top of the page.
The annotation can be exported using the "export feedback" button on the top right side of the page for the list of results.
After the annotation, the participants should submit the session URL or the annotations to the organizers, either by e-mail of using a submission system (still to be decided).

### Automatic annotation task

The participant should enter the PMID into the SMAFIRA tool, export the list of results, and automatically annotate the top 10 articles, using the system(s) they chose or developed for this aim.

## Annotation guidelines

Only the title and the abstract of a PubMed article is currently shown in SMAFIRA, and annotation will be restricted to these. 
The annotation consists of assessing the similarity between the research goals of the two articles, i.e., the reference article and one of the articles from the top 10 list. 
The similarity is defined by a tree-value scale, namely, similar, uncertain, or not similar, as currently available in the SMAFIRA tool. 

More details about the assessment of the similarity will be available shortly.

## Teams and participants

We will allow the participation of single participants or teams. 
All participants should provide an institutional e-mail, e.g., from the university, institute, or company in which they work or study.
The participants may submit a paper to the shared task track of the BioNLP workshop and attend the event. 
Further, we plan to publish an overview paper of the shared task in a journal, and the participants with valid submissions will be invited as co-authors.

## Evaluation

We will compare the annotations from the participants using metrics for inter-annotator agreement (IAA), e.g., the kappa coefficient. 
We will rank the participants (individuals and teams) in terms of agreement to others and in terms of the number of annotated reference articles. 
  
## References
  
[1] Daniel Butzke et al. [SMAFIRA: a literature-based web tool to assist researchers with retrieval of 3R-relevant information](https://journals.sagepub.com/doi/full/10.1177/00236772241237608). Laboratory Animals, 2024, Aug;58(4):369-373. 

[2] Daniel Butzke et al. [SMAFIRA-c: A benchmark text corpus for evaluation of approaches to relevance ranking and knowledge discovery in the biomedical domain](https://europepmc.org/article/ppr/ppr121819). Pre-print 2020.
    
[3] Mariana Neves et al. [Is the ranking of PubMed similar articles good enough? An evaluation of text similarity 
    methods for three datasets](https://aclanthology.org/2023.bionlp-1.11/). In: The 22nd Workshop on Biomedical Natural Language Processing and BioNLP Shared Tasks. Toronto, Canada: Association for Computational Linguistics, July 2023, pp. 133–144.



