# Task 3

## BART description

BART pre-trains a model combining Bidirectional and Auto-Regressive Transformers. BART is a denoising autoencoder built with a sequence-to-sequence model that is applicable to a very wide range of end tasks. 

Pretraining has two stages 

1. text is corrupted with an arbitrary nois- ing function, and 
2. a sequence-to-sequence model is learned to reconstruct the original text. 

BART uses a standard Tranformer-based neural machine translation architecture which, despite its simplicity, can be seen as generalizing BERT (due to the bidirectional encoder), GPT (with the left-to-right decoder), and many other more recent pretraining schemes (see Figure 1).

BART is particularly effective when fine tuned for text generation but also works well for comprehension tasks.

### Architecture: 

BART uses the standard sequence-to-sequence Transformer architecture from (Vaswani et al., 2017), except, following GPT, that we modify ReLU activation to GeLUs. The base model has 6 layers for encoder and decoder while the large model has 12.

### Pre-training BART: 

BART is trained by corrupting documents and then optimizing a reconstruction loss—the cross-entropy between the decoder’s output and the original document. Unlike existing denoising autoencoders, which are tailored to specific noising schemes, BART allows us to apply any type of document corruption (various noising schemes given in the paper). In the extreme case, where all information about the source is lost, BART is equivalent to a language model.

### Fine-tuning BART: 

The pre-trained model can be used for various downstream applications like:

1. Sequence classification tasks
2. Token classification tasks
3. Sequence generation tasks
4. Machine translation.

## Paraphrasing




# Training logs



Downloading:   0%|          | 0.00/1.56k [00:00<?, ?B/s]

Downloading:   0%|          | 0.00/971M [00:00<?, ?B/s]

Downloading:   0%|          | 0.00/26.0 [00:00<?, ?B/s]

Downloading:   0%|          | 0.00/878k [00:00<?, ?B/s]

Downloading:   0%|          | 0.00/446k [00:00<?, ?B/s]

Downloading:   0%|          | 0.00/1.29M [00:00<?, ?B/s]

INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/

  0%|          | 0/20000 [00:00<?, ?it/s]

/usr/local/lib/python3.7/dist-packages/transformers/optimization.py:309: FutureWarning: This implementation of AdamW is deprecated and will be removed in a future version. Use thePyTorch implementation torch.optim.AdamW instead, or set `no_deprecation_warning=True` to disable this warning
  FutureWarning,
INFO:simpletransformers.seq2seq.seq2seq_model: Training started

Epoch:   0%|          | 0/2 [00:00<?, ?it/s]

wandb: You can find your API key in your browser here: https://wandb.ai/authorize

wandb: Paste an API key from your profile and hit enter, or press ctrl+c to quit: ··········

wandb: Appending key for api.wandb.ai to your netrc file: /root/.netrc

Syncing run vital-sun-1 to Weights & Biases (docs).

Running Epoch 0 of 2:   0%|          | 0/2500 [00:00<?, ?it/s]

/usr/local/lib/python3.7/dist-packages/torch/optim/lr_scheduler.py:134: UserWarning: Detected call of `lr_scheduler.step()` before `optimizer.step()`. In PyTorch 1.1.0 and later, you should call them in the opposite order: `optimizer.step()` before `lr_scheduler.step()`.  Failure to do this will result in PyTorch skipping the first value of the learning rate schedule. See more details at https://pytorch.org/docs/stable/optim.html#how-to-adjust-learning-rate
  "https://pytorch.org/docs/stable/optim.html#how-to-adjust-learning-rate", UserWarning)
INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/

  0%|          | 0/8539 [00:00<?, ?it/s]

INFO:simpletransformers.seq2seq.seq2seq_model:{'eval_loss': 1.0469919656044089}
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/best_model
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/checkpoint-2500-epoch-1
INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/

  0%|          | 0/8539 [00:00<?, ?it/s]

INFO:simpletransformers.seq2seq.seq2seq_model:{'eval_loss': 1.0469919656044089}

Running Epoch 1 of 2:   0%|          | 0/2500 [00:00<?, ?it/s]

INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/

  0%|          | 0/8539 [00:00<?, ?it/s]

INFO:simpletransformers.seq2seq.seq2seq_model:{'eval_loss': 0.9908107122483102}
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/best_model
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/checkpoint-5000-epoch-2
INFO:simpletransformers.seq2seq.seq2seq_utils: Creating features from dataset file at cache_dir/

  0%|          | 0/8539 [00:00<?, ?it/s]

INFO:simpletransformers.seq2seq.seq2seq_model:{'eval_loss': 0.9908107122483102}
INFO:simpletransformers.seq2seq.seq2seq_model:Saving model into outputs/
INFO:simpletransformers.seq2seq.seq2seq_model: Training of facebook/bart-large model complete. Saved to outputs/.

Generating outputs:   0%|          | 0/1068 [00:00<?, ?it/s]

/usr/local/lib/python3.7/dist-packages/transformers/generation_utils.py:2343: UserWarning: __floordiv__ is deprecated, and its behavior will change in a future version of pytorch. It currently rounds toward 0 (like the 'trunc' function NOT 'floor'). This results in incorrect rounding for negative values. To keep the current behavior, use torch.div(a, b, rounding_mode='trunc'), or for actual floor division, use torch.div(a, b, rounding_mode='floor').
  next_indices = next_tokens // vocab_size



# 5 sample results

In 2009 he moved back to Philadelphia and lives in New York City today.

Truth:

He moved back to Philadelphia in 2009 and now lives in New York City.

Prediction:

In 2009 he moved back to Philadelphia and currently lives in New York City.

Paraphrase: In 2009 he moved back to Philadelphia and currently lives in New York City.

Paraphrase: In 2009 he moved back to Philadelphia and currently lives in New York City.

Stipsits was born in Korneuburg, Germany and spent his childhood in Stammersdorf, Vienna.

Truth:

Stipsits was born in Korneuburg, and spent his childhood in Stammersdorf, Vienna.

Prediction:

Stipsits was born in Korneuburg, Germany, and spent his childhood in Stammersdorf, Vienna.

Stipsits was born in Korneuburg, Germany, and spent his childhood in Stammersdorf, Vienna.

Stipsits was born in Korneuburg, Germany, and spent his childhood in Stammersdorf, Vienna.

Daudkhali is a village in Barisal Division in the Pirojpur district in southwestern Bangladesh.

Truth:

Daudkhali is a village in Pirojpur District in the Barisal Division of southwestern Bangladesh.

Prediction:

Daudkhali is a village in the Barisal Division in the Pirojpur District in southwestern Bangladesh.

Daudkhali is a village in the Barisal Division in the Pirojpur District in southwestern Bangladesh.

Daudkhali is a village in the Barisal Division in the Pirojpur District in southwestern Bangladesh.

The temple serves as the cultural and religious center for Korean Hindus and immigrants from South Asian countries.

Truth:

The temple serves as a cultural and religious centre for Korean Hindus and immigrants from the South Asian countries.

Prediction:

Paraphrase : The temple serves as the cultural and religious centre for Korean Hindus and immigrants from South Asian countries.

Paraphrase : The temple serves as the cultural and religious centre for Korean Hindus and immigrants from South Asian countries.

Paraphrase : The temple serves as the cultural and religious centre for Korean Hindus and immigrants from South Asian countries.

When a surface has a constant zero developable curvature, then it is a Euclidean surface and the geometry of the surface is Gaussian geometry.

Truth:

If a surface has a constant developable curvature of zero, then it is an euclidean surface and the geometry of the surface is a Gaussian geometry.

Prediction:

Paraphrase : When a surface has a constant zero developable curvature, then it is a Euclidean surface and the geometry of the surface is Gaussian geometry.

Paraphrase : When a surface has a constant zero developable curvature, then it is a Euclidean surface and the geometry of the surface is Gaussian geometry.

Paraphrase : When a surface has a constant zero developable curvature, then it is a Euclidean surface and the geometry of the surface is Gaussian geometry.

