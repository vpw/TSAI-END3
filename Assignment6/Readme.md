# TSAI END3 Assignnmet 6

## Assignment:

        Assignment (300 points):
            Train model we wrote in the class on the following two datasets taken from this link (Links to an external site.): 
                http://www.cs.cmu.edu/~ark/QA-data/ (Links to an external site.)
                https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs (Links to an external site.)
            Once done, please upload the file to GitHub and proceed to share the things asked below:
                Share the link to your GitHub repo (100 pts for code quality/file structure/model accuracy) (100 pts)
                Share the link to your readme file (100 points for proper readme file)
                Copy-paste the code related to your dataset preparation for both datasets.  (100 pts)
                If your model trains and gets to respectable accuracy (200 pts). 

## Datasets
### [Question Answer dataet from Wikipedia articles](http://www.cs.cmu.edu/~ark/QA-data/)

From the readme: There are three directories, one for each year of students: S08, S09, and S10.

I selected the last directory (S10) for QA samples as all three seem to have similar Q&A and the last one had more additions.

I replaced the Lang class with a QA class.

The output after train_iters was:

                1m 39s (- 23m 16s) (5000 6%) 2.3081
                3m 12s (- 20m 53s) (10000 13%) 1.7417
                4m 49s (- 19m 17s) (15000 20%) 1.2353
                6m 28s (- 17m 49s) (20000 26%) 0.8678
                8m 7s (- 16m 15s) (25000 33%) 0.6389
                9m 47s (- 14m 41s) (30000 40%) 0.5226
                11m 28s (- 13m 7s) (35000 46%) 0.4685
                13m 9s (- 11m 30s) (40000 53%) 0.4545
                14m 51s (- 9m 54s) (45000 60%) 0.4171
                16m 32s (- 8m 16s) (50000 66%) 0.4236
                18m 12s (- 6m 37s) (55000 73%) 0.4039
                19m 53s (- 4m 58s) (60000 80%) 0.3955
                21m 32s (- 3m 18s) (65000 86%) 0.3919
                23m 11s (- 1m 39s) (70000 93%) 0.3846
                24m 49s (- 0m 0s) (75000 100%) 0.3579

And the random evaluation output was:

> does fender make cymbals ?
= no
< null <EOS>

> do many such drums have six to ten tension rods ?
= yes .
< yes . <EOS>

> what is the national language in malaysia ?
= null
< null <EOS>

> what instrument was produced after the xylophone in the s ?
= null
< null <EOS>

> is finnish threatened by english ?
= no finnish is not threatened by english .
< no finnish is not threatened by english . <EOS>

> who laid out a street plan for the expanded settlement ?
= william richardson and alcalde francisco de haro .
< william richardson and alcalde francisco de haro . <EOS>

> where is jakarta located
= on the northwest coast of java
< northwest coast of java <EOS>

> what was built to play in both b and a keys ?
= piccolo trumpets
< piccolo trumpets <EOS>

> null
= null
< null <EOS>

> was amedeo avogadro was born in turin ?
= yes
< yes <EOS>

### [Quora questions dataset](https://data.quora.com/First-Quora-Dataset-Release-Question-Pairs)


