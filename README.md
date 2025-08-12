# QA system from scratch in Python

Repository of building Question and Answer chatbot system from scratch or other NLP techniques

* Transformer_Arch.ipynb: Tranformer architecture from https://github.com/nlp-with-transformers/notebooks
* QA_transformer_from_scratch.ipynb:
  * Extractive QA system
  * *Using the above transformer encoder architecture + adding a QA head to build a QA model.
  * Trained on the SQuAD train dataset.
  * Add simple vector store and KNN search capability.
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
