# Task 1

## Assignment

1. Train BERT using the code mentioned here (https://drive.google.com/file/d/1Zp2_Uka8oGDYsSe5ELk-xz6wIX8OIkB7/view?usp=sharing) on the Squad Dataset for 20% overall samples (1/5 Epochs). 
2. Show results on 5 samples. 

Readme with training log snippets and 5 sample results along with BERT description must be available.

# BERT

BERT is a language representation model and stands for Bidirectional Encoder Representations from Transformers. 
BERT is designed to pre-train deep bidirectional representations from unlabeled text by jointly conditioning on both left and right context in all layers. 
As a result, the pre-trained BERT model can be fine-tuned with just one additional output layer to create state-of-the-art models for a wide range of tasks, such as question answering and language inference, without substantial task-specific architecture modifications.

BERT overcomes drawbacks of previous models by introducing 

1. MLM (Masked Language Model) - The masked language model randomly masks some of the tokens from the input, and the objective is to predict the original vocabulary id of the masked word based only on its context. Unlike left-to- right language model pre-training, the MLM ob- jective enables the representation to fuse the left and the right context, which allows us to pre- train a deep bidirectional Transformer.
2. NSP (Next Sentence Prediction) - which jointly pre-trains text pair representations. 

This enables pre-training representations which reduce the need for many heavily-engineered task specific architectures.

There are two steps in the BERT framework - Pre-training and Fine-tuning.

During pre-training, the model is trained on unlabeled data over different pre-training tasks. For fine-tuning, the BERT model is first initialized with the pre-trained parameters, and all of the parameters are fine-tuned using labeled data from the downstream tasks. Each downstream task has separate fine-tuned models, even though they are initialized with the same pre-trained parameters. 

An example for Question answwering task is demonstrated in this assignment.

# Training logs

# Output of 5 samples
