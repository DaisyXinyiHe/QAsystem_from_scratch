# QA system from scratch in Python

Repository of building Question and Answer chatbot system from scratch or other NLP techniques

This repository contains an extractive Question Answering system supported by a vector store with question and context information. 

How QA model was trained: 
* Encoder transformer architesture was used
* A QA head was added to the encoder. This predicts the start and the end of the answer based on the question and the context. 
* SQuAD dataset was used to train the model

How to make inference: 
* First, we state a question. 
* Then we use cosine similarity and KNN to search in the vector store of questions that are similar to the question ask. With this method, we retrieve the context. 
* We put the question and the context together into the QA system to predict answers to the questions. 

This project serve as a basis to understand how QA system work. The next step is to replicate with more sophisticated technilogy, such as a pre-tained model with generative capability and Vector DB with HNSW capability. 

* Transformer_Arch.ipynb: Tranformer architecture from https://github.com/nlp-with-transformers/notebooks
* QA_transformer_from_scratch.ipynb:
  * Extractive QA system
    * Meaning model predict start and end of an answer sentence extracted from context according to question query. 
    * Using the above transformer encoder architecture + adding a QA head to build a QA model.
    * Trained on the SQuAD train dataset.
  * Add simple vector store and KNN search capability.
    * Use cosine similarity in KNN search to calculate similarity between questions. Based on the questions, retrieve the context. 
    * Sources:
    * https://sarabesh.medium.com/how-i-built-a-vector-db-with-hnsw-from-scratch-a311b6eac082
    * https://medium.com/@vidiptvashist/building-a-vector-database-from-scratch-in-python-6bd683ba5171
    * https://machinelearningmastery.com/tutorial-to-implement-k-nearest-neighbors-in-python-from-scratch/
  * However, need to refine tokenizer as the model cannot handle words it has never seen before.
    * Possible solutions:
      * Lemmantization
      * BERT use word piece tokenizer. Or Sentence piece tokenizer
  * Need to add reader
  * Check out beam search and decoder srtcutures for generative QA system.

