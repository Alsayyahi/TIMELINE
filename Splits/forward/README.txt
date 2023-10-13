Step-by-step instructions to replicate the results reported in the paper on TIMELINE corpus:


1. Given the annotated corpus, the data have been pre-processed to be accepted by the baseline models we used (as illustrated in the paper). Each relation out of () relations that have been tagged (as listed in annotated_relations.csv) has been processed to be be in the following formate:
[doc_id: "Document 1",
sample_id: "L0",
pair: ["ei1", "ei2"],
label: 1,
[
BERT embedding: [[------],[------],[------],....], #BERT embedding for every token in the sentence(s) involving both events
POS embedding: [0,1,2,....],
Features: [0,1,2,......], #Not used in this work 
reversed label?:  false, #In the forward data, the value will be false. In the backward data, the value will be true.
index l_s: 10, #the index of the first event involved in the relation
index l_e: 10, #the index of the first event involved in the relation( it will be the same as index l_s if the event consist of one trigger word, and it will be (index l_s+1) if the event consist of two trigger words)
index r_s: 13, #the index of the second event involved in the relation
index r_e: 13, #the index of the second event involved in the relation(will be the same as index r_s if the event consist of one trigger word, and it will be (index l_s+1) if the event consist of two trigger words)
predict index?: True
]]
2. The models can be found from this GitHub link: ()
3. Once the models are downloaded into your machine, place the three pickle files located in forward folder in the following directory: () and place the three pickle files located in the backward folder in the following directory: ().
Note: the main difference between forward data and backward data is the labels are reversed (the label is reversed and the value of the reversed label? is false in the forward data and is true in the backward data). For further explanation, refer to the paper that proposes these models: ()
4. Go to the code directory, and run the following command:
python train_all.py






Note: Ampere A100 machine from Paperspace: https://www.paperspace.com/ have been used to run our experiment.