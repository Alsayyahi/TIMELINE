Step-by-step instructions to replicate the results reported in the paper:

1. Given the annotated corpus, the data have been pre-processed to be accepted by the baseline models we used (as illustrated in the paper). Each sample has been processed to be in the following format:
[doc_id: "Document 1",
sample_id: "L0",
pair: ["ei1", "ei2"],
label: 1,
[
BERT embedding: [[------],[------],[------],....], #BERT embedding for every token in the sentence(s) involving both events
POS embedding: [0,1,2,....],  #POS tag embedding for every token in the sentence(s) involving both events
Features: [0,1,2,......], #Not used in this work 
reversed label?:  false, #In the forward data, the value is (false). In the backward data, the value is (true).
index l_s: 10, #the index of the first event involved in the relation
index l_e: 10, #the index of the first event involved in the relation( it will be the same as index l_s if the event consists of one trigger word, and it will be (index l_s+1) if the event consist of more than one trigger word)
index r_s: 13, #the index of the second event involved in the relation
index r_e: 13, #the index of the second event involved in the relation(will be the same as index r_s if the event consists of one trigger word, and it will be (index l_s+1) if the event consists of more than one trigger word)
predict index?: True
]]

2. The models can be found from this GitHub link: https://github.com/PlusLabNLP/Deep-Structured-EveEveTemp

3. Once the models are downloaded into your machine, place the three pickle files located in the forward folder in the following directory: (/output_data/matres_output/all_bertemb) and place the three pickle files located in the backward folder in the following directory: (/output_data/matres_output/all_backward_bertemb).
Note: the main difference between forward data and backward data is the labels are reversed (the label is reversed, and the value of the reversed label? is (false) in the forward data and is (true) in the backward data). For further explanation, refer to the paper that proposes these models (Deep Structured Neural Network for Event Temporal Relation Extraction, 2019)

4. Go to the code directory and run the following command:
python train_all.py

Note: Ampere A100 machine from Paperspace: https://www.paperspace.com/ have been used to run our experiment.
