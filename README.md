# Deep6mA

Deep6mA is a deep-learning-based framework to predict 6mA-containing sequences. 

# Dependency

- Python3

- numpy==1.14.2

- torch==0.4.0a0+0e24630  (  [pytorch](https://pytorch.org/)  )

- scikit_learn==0.19.1

  

# Content

- data: data of rice for model training ( data of Arabidopsis thaliana, Fragaria vesca and Rosa chinensis for validation on other three species)
- demo_test: 
  - test.fa: data for testing scripts
  - expected results
    - predout.tsv: prediciton results
    
  
- result: 
  - trained_models: trained models for rice(5-fold)
  
    

# Usage

## 1. train model

The script main_train.py is used to train model. The required arguments

- model_type:  cnn-rnn
- pos_fa/neg_fa: the fasta file for positive samples/negative samples ( the length of sequences should be no more than 41bp)
- out_dir: the path of output directory

This script ouput the trained model and prediction result in the out_dir. 

```python
python main_train.py -m model_type -pos_fa pos_fa -neg_fa neg_fa -od out_dir
```

## 2. predict m6A-containing sequences

The script main_test.py is used to predict if a given sequence contain m6A sites. The required arguments

- model_type:  cnn-rnn
- input_fa: a fasta file for test samples ( the length of sequences should be no more than 101bp)
- model_dir: the path of model directory
- out_fn: output file 

This script ouput the prediction scores for given sequences. 

```
python main_test.py -m model_type -in_fa input_fa -md model_dir -outfn out_fn
```



