# Assignment 5

I decided to use the two datasets: 

A. YelpReviewPolarity

Number of lines per split:

    train: 560000

    test: 38000
Number of classes

    2

Labels: 

        0 : Negative polarity.

        1 : Positive polarity.


B. SogouNews

Number of lines per split:

    train: 450000

    test: 60000
Number of classes

    5

Labels:

        0 : Sports

        1 : Finance

        2 : Entertainment

        3 : Automobile

        4 : Technology


I created a class TrainAndTestDataset with the train, evaluate, collate_batch, yield_tokens, predict methods encapsulated and created a new method train_and_test to train through the epochs and test it on the test set. Added a test_sample method to test on a randomly selected text from the test_dataset to check the presdiction.

The final accuracies and sample test results for the two are:

Yelp review polarity:

| end of epoch   5 | time: 80.47s | valid accuracy    0.893 
-----------------------------------------------------------
Checking the results of test dataset. test accuracy    0.897

Sougou news:

| end of epoch   5 | time: 179.07s | valid accuracy    0.936 
-----------------------------------------------------------
Checking the results of test dataset. test accuracy    0.935

