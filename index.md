

### ** Please join our [discussion forum](https://github.com/smafira-bf3r/smafira-st/discussions) for announcements, questions, etc. **

Some countries have strict legislation regarding the authorization of animal testing. 
For instance,   some require that researchers should comply with the so-called [3R principles](https://caat.jhsph.edu/the-principles-of-humane-experimental-technique/), i.e., strategies for the replacement with non-animal approaches, reduction of the number of animals in individual experiments, and refinement of the experimental procedures to reduce animal suffering. 
Further, many countries require researchers to carry out a thorough literature search to ensure that alternative approaches are currently not available.

The [SMAFIRA project](https://www.bf3r.de/en/smafira___artificial_intelligence_for_finding_alternative_methods-297876.html) aims at supporting researchers for finding alternative methods to animal experiments.
Recently, we released our [SMAFIRA Web tool](https://smafira.bf3r.de/) [1], which allows researchers to perform such a search.
The input to the tool is a PubMed identifier (PMID) of a publication, hereafter called “reference article”, that represents the animal experiment for which one wants to find an alternative method. 
The tool retrieves up to 200 similar articles available in PubMed, and presents these as a list of results. 

One of the processing tasks that is currently carried out for the retrieved articles in SMAFIRA is the re-ranking of the articles based on the similarity of the research goal, as compared to the reference article. 
There are three possible values for the similarity: **similar**, **uncertain**, or **not similar**.

We propose a shared task for collaborative annotation of training data in the scope of the [BioNLP workshop](https://aclweb.org/aclwiki/BioNLP_Workshop).
We will release a list of various reference articles, grouped according to some pre-selected diseases (MeSH terms). 
The participants will validate the top 20 similar articles, either automatically, with any system of their choice, or manually using the SMAFIRA tool.

## Important dates

- Release of the test data (batch1): Jan-Feb/2025
- Release of the test data (batch2): Mar/2025
- Submissions of annotations (batch1): April 30th, 2025
- Submissions of system paper: May 5th, 2025
- Final submissions of system paper: May 20th, 2025
- Submissions of annotations (batch2): July/2025

## Data and annotation tool

### Available data
  
We previously released [four case studies](https://github.com/SMAFIRA/c_corpus) [2], which can be used by for any purpose, e.g., evaluation or few-shot approaches. 
We previously used this dataset for the evaluation of various similarity methods [3].
The mapping between the labels in the case studies and the similarity values is the following: 

- **similar**: equivalent "++", partially equivalent “+(+)” or “+”, noteworthy “n”
- **uncertain**: limbo “L”
- **not similar**: not equivalent “-”

### Annotation tool

The [SMAFIRA Web tool](https://smafira.bf3r.de/) is freely accessible and no login is necessary. 
Instead, the annotators can bookmark the URL of their session for later annotation or share the URL with other colleagues for a collaborative annotation.

### Test data

We pre-selected a list of 21 diseases, e.g., “Neoplasms” or “Musculoskeletal Diseases”, and their respective MeSH terms. 
We performed searches in Pubmed based on each disease, e.g., (Musculoskeletal Diseases[MeSH Major Topic]) 
AND (Models, Animal[MeSH Major Topic]), and manually selected five reference articles. 
The selected reference articles should describe a proper animal experiment and cannot be a review. 

For instance, the article with [PMID 37775153](https://pubmed.ncbi.nlm.nih.gov/37775153/) belongs to the topic of “Musculoskeletal Diseases” and studies the effect of the L-arginine metabolism on arthritis and inflammation-mediated bone loss. 
It proposes three methods, including transgenic mice (i.e., an animal experiment), but also *in vitro* methods.

## Annotation tasks

We will release the list of PMIDs, i.e., the reference articles. 
The participants will be free to pick any of the reference articles from any of the topics and perform annotation for the top 20 articles. 
A valid submission to the shared task should consist of the annotation of all articles in the top 20 for a particular reference article. 
The participants can submit annotations for as many reference articles as they wish.
The annotation can be carried out manually or automatically.

We will release two batches of reference articles:

- batch1: reference articles from a pre-selected list of five topics, in order to allow a better computation of an inter-annotation agreement; and 
- batch2: reference articles from the remaining topics.
  
By the respective deadline, the participants should submit the session URL or the annotations to the organizers, either by e-mail or using a submission system (still to be decided).

### Manual annotation task

Please follow the procedure below:

1. Enter the PMID of one reference article into the SMAFIRA tool (search page).
2. Click on the button "Search for PUBMED similar articles" and the title of the article will be shown for confirmation. Confirm it by clicking on the green button.
3. After some second a list of results is shown. Participants should validate the top 20 articles from the list (as ordered by the "SMAFIRA Rank", the default ranking).
4. By clicking on one PMID of the list, the tool opens a comparison page between the reference article (on the left) and the clicked article (on the right).
5. The participant should carefully read both abstract and assess the similarity of their research goal.
6. The annotation consist of simply clicking on one of one of the option at the top of the page: green thumb up (similar), thumb up/down (uncertain), or thump down (not similar).
7. It is possible to go back to the list of results at any time and navigate between the articles using the next/previous arrows, both found at the top of the page.
8. Export the annotations by clicking on the button "export feedback" on the top right side of the page for the list of results.

### Automatic annotation task

For each batch, we will release a test file that will include the reference articles, and the corresponding similar articles and abstracts.

## Teams and participants

We will allow the participation of single participants or teams. 
All participants should provide an institutional e-mail, e.g., from the university, institute, or company in which they work or study.
The participants may submit a paper to the shared task track of the BioNLP workshop and attend the event. 
Further, we plan to publish an overview paper of the shared task in a journal, and the participants with valid submissions will be invited as co-authors.

## Release of the annotations

All annotations will be made available for the public under an appropriate licence for open data purposes, e.g., [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode).
The annotation will be identified according to their respective team.

## Evaluation

We will compare the annotations from the participants using metrics for inter-annotator agreement (IAA), e.g., the kappa coefficient. 
We will rank the participants (individuals and teams) in terms of agreement to others and in terms of the number of annotated reference articles. 

## Annotation guidelines

Only the title and the abstract of a PubMed article is currently shown in SMAFIRA, and annotation will be restricted to these. 
The annotation consists of assessing the similarity between the research goals of the two articles, i.e., the reference article and one of the articles from the top 10 list. 
The similarity is defined by a tree-value scale, namely, similar, uncertain, or not similar, as currently available in the SMAFIRA tool. 

More details about the assessment of the similarity is described in [2] and we show some examples below.
Please not that the details about disease, aplication, etc are only shown for the understanding of the similarity and should NOT be annotated in the tasks.

| PMID | Reference | Application | Disease | Disease feature | Endpoints |
| --- | --- | --- |
| [19735549](https://pubmed.ncbi.nlm.nih.gov/19735549/) | - | Model development, Disease mechanism | breast cancer, human ductal carcinoma in situ (DCIS)	|	tumor initiation, growth, progress| HER-2 |

| PMID | Similarity | Application | Disease | Disease feature | Endpoints |
| --- | --- | --- |
| [28707729](https://pubmed.ncbi.nlm.nih.gov/28707729/) | similar | Disease mechanism | breast cancer, DCIS | promote invasive growth	| SOX11 |
| [20421921](https://pubmed.ncbi.nlm.nih.gov/20421921/)  | similar  | Disease mechanism | breast cancer, DCIS | progression into invasive	| Atg5, AKT/PI3 Kinase and mTOR |
| [19920187](https://pubmed.ncbi.nlm.nih.gov/19920187/) | uncertain | Disease mechanism; Model development | breast cancer, DCIS | progression into invasive | HGF-secreting mammary fibroblasts |
| [27374087](https://pubmed.ncbi.nlm.nih.gov/27374087/) | uncertain | Disease mechanism | breast cancer, DCIS	| progression into invasive | distinction of aggressive clones |
| [22777354](https://pubmed.ncbi.nlm.nih.gov/22777354/) | not similar | Disease mechanism | breast cancer, DCIS | regulation of tumor cell differentiation | SIM2s |
| [24691501](https://pubmed.ncbi.nlm.nih.gov/24691501/) | not similar | Disease mechanism | breast cancer, DCIS |	myoepithelial cell layer | BXL0124 |

## Contact

- Mariana Neves (mariana.lara-neves@bfr.bund.de)

## Organizers

- Mariana Neves (German Federal Institute for Risk Assessment - BfR)
- Daniel Butzke (German Federal Institute for Risk Assessment - BfR)
  
## References
  
[1] Daniel Butzke et al. [SMAFIRA: a literature-based web tool to assist researchers with retrieval of 3R-relevant information](https://journals.sagepub.com/doi/full/10.1177/00236772241237608). Laboratory Animals, 2024, Aug;58(4):369-373. 

[2] Daniel Butzke et al. [SMAFIRA-c: A benchmark text corpus for evaluation of approaches to relevance ranking and knowledge discovery in the biomedical domain](https://europepmc.org/article/ppr/ppr121819). Pre-print 2020.
    
[3] Mariana Neves et al. [Is the ranking of PubMed similar articles good enough? An evaluation of text similarity 
    methods for three datasets](https://aclanthology.org/2023.bionlp-1.11/). In: The 22nd Workshop on Biomedical Natural Language Processing and BioNLP Shared Tasks. Toronto, Canada: Association for Computational Linguistics, July 2023, pp. 133–144.


