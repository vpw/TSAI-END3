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

***** Running training *****

  Num examples = 26948

  Num Epochs = 1

  Batch size = 16

  Total optimization steps = 1684


Epoch:   0%|          | 0/1 [00:00<?, ?it/s]

Iteration:   0%|          | 0/1684 [00:00<?, ?it/s]/usr/local/lib/python3.7/dist-packages/pytorch_transformers/optimization.py:166: UserWarning: This overload of add_ is deprecated:

	add_(Number alpha, Tensor other)

Consider using one of the following signatures instead:

	add_(Tensor other, *, Number alpha) (Triggered internally at  ../torch/csrc/utils/python_arg_parser.cpp:1050.)

  exp_avg.mul_(beta1).add_(1.0 - beta1, grad)



Iteration:   0%|          | 2/1684 [00:00<13:05,  2.14it/s]

Iteration:   0%|          | 3/1684 [00:01<16:36,  1.69it/s]

Iteration:   0%|          | 4/1684 [00:02<18:24,  1.52it/s]

Iteration:   0%|          | 5/1684 [00:03<19:30,  1.43it/s]

Iteration:   0%|          | 6/1684 [00:04<20:15,  1.38it/s]

Iteration:   0%|          | 7/1684 [00:04<20:47,  1.34it/s]

Iteration:   0%|          | 8/1684 [00:05<21:03,  1.33it/s]

Iteration:   1%|          | 9/1684 [00:06<21:18,  1.31it/s]

Iteration:   1%|          | 10/1684 [00:07<21:30,  1.30it/s]

Iteration:   1%|          | 11/1684 [00:07<21:34,  1.29it/s]

Iteration:   1%|          | 12/1684 [00:08<21:42,  1.28it/s]

Iteration:   1%|          | 13/1684 [00:09<21:44,  1.28it/s]

Iteration:   1%|          | 14/1684 [00:10<21:46,  1.28it/s]

Iteration:   1%|          | 15/1684 [00:11<21:50,  1.27it/s]

Iteration:   1%|          | 16/1684 [00:11<21:46,  1.28it/s]

Iteration:   1%|          | 17/1684 [00:12<21:46,  1.28it/s]

Iteration:   1%|          | 18/1684 [00:13<21:46,  1.27it/s]

Iteration:   1%|          | 19/1684 [00:14<21:46,  1.27it/s]

Iteration:   1%|          | 20/1684 [00:15<21:46,  1.27it/s]

Iteration:   1%|          | 21/1684 [00:15<21:48,  1.27it/s]

Iteration:   1%|▏         | 22/1684 [00:16<21:48,  1.27it/s]

Iteration:   1%|▏         | 23/1684 [00:17<21:49,  1.27it/s]

Iteration:   1%|▏         | 24/1684 [00:18<21:51,  1.27it/s]

Iteration:   1%|▏         | 25/1684 [00:18<21:51,  1.26it/s]

Iteration:   2%|▏         | 26/1684 [00:19<22:00,  1.26it/s]

Iteration:   2%|▏         | 27/1684 [00:20<21:57,  1.26it/s]

Iteration:   2%|▏         | 28/1684 [00:21<22:01,  1.25it/s]

Iteration:   2%|▏         | 29/1684 [00:22<22:00,  1.25it/s]

Iteration:   2%|▏         | 30/1684 [00:22<22:06,  1.25it/s]

Iteration:   2%|▏         | 31/1684 [00:23<22:10,  1.24it/s]

Iteration:   2%|▏         | 32/1684 [00:24<22:14,  1.24it/s]

Iteration:   2%|▏         | 33/1684 [00:25<22:16,  1.24it/s]

Iteration:   2%|▏         | 34/1684 [00:26<22:15,  1.24it/s]

Iteration:   2%|▏         | 35/1684 [00:27<22:15,  1.23it/s]

Iteration:   2%|▏         | 36/1684 [00:27<22:15,  1.23it/s]

Iteration:   2%|▏         | 37/1684 [00:28<22:07,  1.24it/s]

Iteration:   2%|▏         | 38/1684 [00:29<22:07,  1.24it/s]

Iteration:   2%|▏         | 39/1684 [00:30<22:09,  1.24it/s]

Iteration:   2%|▏         | 40/1684 [00:31<22:03,  1.24it/s]

Iteration:   2%|▏         | 41/1684 [00:31<22:02,  1.24it/s]

Iteration:   2%|▏         | 42/1684 [00:32<22:05,  1.24it/s]

Iteration:   3%|▎         | 43/1684 [00:33<22:06,  1.24it/s]

Iteration:   3%|▎         | 44/1684 [00:34<22:06,  1.24it/s]

...

Iteration:  95%|█████████▍| 1598/1684 [22:24<01:12,  1.19it/s]

Iteration:  95%|█████████▍| 1599/1684 [22:25<01:11,  1.18it/s]

Iteration:  95%|█████████▌| 1600/1684 [22:26<01:11,  1.18it/s]

Iteration:  95%|█████████▌| 1601/1684 [22:27<01:10,  1.18it/s]

Iteration:  95%|█████████▌| 1602/1684 [22:28<01:08,  1.19it/s]

Iteration:  95%|█████████▌| 1603/1684 [22:29<01:08,  1.19it/s]

Iteration:  95%|█████████▌| 1604/1684 [22:29<01:07,  1.19it/s]

Iteration:  95%|█████████▌| 1605/1684 [22:30<01:06,  1.19it/s]

Iteration:  95%|█████████▌| 1606/1684 [22:31<01:05,  1.19it/s]

Iteration:  95%|█████████▌| 1607/1684 [22:32<01:04,  1.19it/s]

Iteration:  95%|█████████▌| 1608/1684 [22:33<01:04,  1.19it/s]

Iteration:  96%|█████████▌| 1609/1684 [22:34<01:03,  1.19it/s]

Iteration:  96%|█████████▌| 1610/1684 [22:35<01:02,  1.19it/s]

Iteration:  96%|█████████▌| 1611/1684 [22:35<01:01,  1.19it/s]

Iteration:  96%|█████████▌| 1612/1684 [22:36<01:00,  1.19it/s]

Iteration:  96%|█████████▌| 1613/1684 [22:37<00:59,  1.19it/s]

Iteration:  96%|█████████▌| 1614/1684 [22:38<00:59,  1.18it/s]

Iteration:  96%|█████████▌| 1615/1684 [22:39<00:58,  1.18it/s]

Iteration:  96%|█████████▌| 1616/1684 [22:40<00:57,  1.19it/s]

Iteration:  96%|█████████▌| 1617/1684 [22:40<00:56,  1.18it/s]

Iteration:  96%|█████████▌| 1618/1684 [22:41<00:55,  1.18it/s]

Iteration:  96%|█████████▌| 1619/1684 [22:42<00:54,  1.19it/s]

Iteration:  96%|█████████▌| 1620/1684 [22:43<00:54,  1.18it/s]

Iteration:  96%|█████████▋| 1621/1684 [22:44<00:52,  1.19it/s]

Iteration:  96%|█████████▋| 1622/1684 [22:45<00:52,  1.19it/s]

Iteration:  96%|█████████▋| 1623/1684 [22:45<00:51,  1.18it/s]

Iteration:  96%|█████████▋| 1624/1684 [22:46<00:50,  1.19it/s]

Iteration:  96%|█████████▋| 1625/1684 [22:47<00:49,  1.19it/s]

Iteration:  97%|█████████▋| 1626/1684 [22:48<00:48,  1.19it/s]

Iteration:  97%|█████████▋| 1627/1684 [22:49<00:48,  1.19it/s]

Iteration:  97%|█████████▋| 1628/1684 [22:50<00:47,  1.19it/s]

Iteration:  97%|█████████▋| 1629/1684 [22:51<00:46,  1.19it/s]

Iteration:  97%|█████████▋| 1630/1684 [22:51<00:45,  1.19it/s]

Iteration:  97%|█████████▋| 1631/1684 [22:52<00:44,  1.19it/s]

Iteration:  97%|█████████▋| 1632/1684 [22:53<00:43,  1.19it/s]

Iteration:  97%|█████████▋| 1633/1684 [22:54<00:42,  1.19it/s]

Iteration:  97%|█████████▋| 1634/1684 [22:55<00:42,  1.19it/s]

Iteration:  97%|█████████▋| 1635/1684 [22:56<00:41,  1.19it/s]

Iteration:  97%|█████████▋| 1636/1684 [22:56<00:40,  1.20it/s]

Iteration:  97%|█████████▋| 1637/1684 [22:57<00:39,  1.19it/s]

Iteration:  97%|█████████▋| 1638/1684 [22:58<00:38,  1.19it/s]

Iteration:  97%|█████████▋| 1639/1684 [22:59<00:37,  1.19it/s]

Iteration:  97%|█████████▋| 1640/1684 [23:00<00:37,  1.19it/s]

Iteration:  97%|█████████▋| 1641/1684 [23:01<00:36,  1.18it/s]

Iteration:  98%|█████████▊| 1642/1684 [23:01<00:35,  1.18it/s]

Iteration:  98%|█████████▊| 1643/1684 [23:02<00:34,  1.19it/s]

Iteration:  98%|█████████▊| 1644/1684 [23:03<00:33,  1.19it/s]

Iteration:  98%|█████████▊| 1645/1684 [23:04<00:32,  1.19it/s]

Iteration:  98%|█████████▊| 1646/1684 [23:05<00:32,  1.19it/s]

Iteration:  98%|█████████▊| 1647/1684 [23:06<00:31,  1.19it/s]

Iteration:  98%|█████████▊| 1648/1684 [23:07<00:30,  1.19it/s]

Iteration:  98%|█████████▊| 1649/1684 [23:07<00:29,  1.19it/s]

Iteration:  98%|█████████▊| 1650/1684 [23:08<00:28,  1.19it/s]

Iteration:  98%|█████████▊| 1651/1684 [23:09<00:27,  1.19it/s]

Iteration:  98%|█████████▊| 1652/1684 [23:10<00:26,  1.19it/s]

Iteration:  98%|█████████▊| 1653/1684 [23:11<00:26,  1.19it/s]

Iteration:  98%|█████████▊| 1654/1684 [23:12<00:25,  1.19it/s]

Iteration:  98%|█████████▊| 1655/1684 [23:12<00:24,  1.18it/s]

Iteration:  98%|█████████▊| 1656/1684 [23:13<00:23,  1.19it/s]

Iteration:  98%|█████████▊| 1657/1684 [23:14<00:22,  1.19it/s]

Iteration:  98%|█████████▊| 1658/1684 [23:15<00:21,  1.19it/s]

Iteration:  99%|█████████▊| 1659/1684 [23:16<00:21,  1.19it/s]

Iteration:  99%|█████████▊| 1660/1684 [23:17<00:20,  1.19it/s]

Iteration:  99%|█████████▊| 1661/1684 [23:17<00:19,  1.19it/s]

Iteration:  99%|█████████▊| 1662/1684 [23:18<00:18,  1.19it/s]

Iteration:  99%|█████████▉| 1663/1684 [23:19<00:17,  1.18it/s]

Iteration:  99%|█████████▉| 1664/1684 [23:20<00:16,  1.18it/s]

Iteration:  99%|█████████▉| 1665/1684 [23:21<00:16,  1.18it/s]

Iteration:  99%|█████████▉| 1666/1684 [23:22<00:15,  1.19it/s]

Iteration:  99%|█████████▉| 1667/1684 [23:23<00:14,  1.19it/s]

Iteration:  99%|█████████▉| 1668/1684 [23:23<00:13,  1.19it/s]

Iteration:  99%|█████████▉| 1669/1684 [23:24<00:12,  1.19it/s]

Iteration:  99%|█████████▉| 1670/1684 [23:25<00:11,  1.19it/s]

Iteration:  99%|█████████▉| 1671/1684 [23:26<00:10,  1.19it/s]

Iteration:  99%|█████████▉| 1672/1684 [23:27<00:10,  1.19it/s]

Iteration:  99%|█████████▉| 1673/1684 [23:28<00:09,  1.19it/s]

Iteration:  99%|█████████▉| 1674/1684 [23:28<00:08,  1.19it/s]

Iteration:  99%|█████████▉| 1675/1684 [23:29<00:07,  1.19it/s]

Iteration: 100%|█████████▉| 1676/1684 [23:30<00:06,  1.19it/s]

Iteration: 100%|█████████▉| 1677/1684 [23:31<00:05,  1.19it/s]

Iteration: 100%|█████████▉| 1678/1684 [23:32<00:05,  1.19it/s]

Iteration: 100%|█████████▉| 1679/1684 [23:33<00:04,  1.19it/s]

Iteration: 100%|█████████▉| 1680/1684 [23:33<00:03,  1.19it/s]

Iteration: 100%|█████████▉| 1681/1684 [23:34<00:02,  1.19it/s]

Iteration: 100%|█████████▉| 1682/1684 [23:35<00:01,  1.19it/s]

Iteration: 100%|█████████▉| 1683/1684 [23:36<00:00,  1.19it/s]

Iteration: 100%|██████████| 1684/1684 [23:37<00:00,  1.19it/s]

Epoch: 100%|██████████| 1/1 [23:37<00:00, 1417.31s/it]




# Output of 5 samples

There was an error in the evaluate function which I was unable to resolve (see the notebook) and could not get the output predictions file. Will try to resolve it later if possible!
