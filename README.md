# TIMELINE
TIMELINE: Exhaustive Annotation of Temporal Relations Supporting the Automatic Ordering of Events in News Articles

Corpus annotation: 


(1)Getting the raw text of the news articles : 
The corpus consists of 48 news articles collected from the LexisNexis library. You can find in the (Annotated_Articles.xlsx) file the URL/API permalink, article title and the publication date of every article. 

To download the raw text of a specific news article, click on the URL link of a specific article in the (Annotated_Articles.xlsx) file, and the link will direct you to the article page. Then, you can click on the download icon in the top right corner of the page, choose the document format and click download. 

Note: You can access the library through your institution by clicking on the Academic Sign-in.

(2) Events annotation:
Each news article has been broken down into a set of sentences where the end of each sentence is a period symbol (.).
In the (Annotated_Events.csv) file, you can find each event annotated in each sentence.

Note 1: If a specific event occurred more than once in a particular sentence, you can find the order of the occurrence in the (Appearance in the sentence) column. For example, if the sentence contains two events, both of which are "said", and we refer to the second "said" in our annotation, the value in this column will be 2. However, if a specific event is mentioned only once in a particular sentence, the value in the Appearance in the sentence column will be 0. 

Note 2: Before the annotation process, we truncated 2-3 sentences at the end of four news articles (Document 10, Document 43, Document 44 and Document 46) because when the articles were processed to generate the BERT embedding for each token, we received a message that said that BERT has a max length limit of tokens which is 512.

Note 3: The sentence boundaries (first word, last word) for each sentence in each document can be found in the (sentence_boundries.csv) file.

(3) Relations annotation: 
In the (Annotated_Relations.csv) file, you can find the annotated relations where each row contains the event triggers and the events IDs (as listed in the events annotation file). Also, it includes the temporal relations' labels as generated by the temporal relations generation method described in the paper.

Note: The relations labelled "vague" have been discarded (as mentioned in the paper).

