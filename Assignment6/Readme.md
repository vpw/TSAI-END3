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

The DB contents are described as:

                The file "question_answer_pairs.txt" contains the questions and answers. The first line of the file contains 
                column names for the tab-separated data fields in the file. This first line follows:

                ArticleTitle    Question        Answer  DifficultyFromQuestioner        DifficultyFromAnswerer  ArticleFile

                Field 1 is the name of the Wikipedia article from which questions and answers initially came.
                Field 2 is the question.
                Field 3 is the answer.
                Field 4 is the prescribed difficulty rating for the question as given to the question-writer. 
                Field 5 is a difficulty rating assigned by the individual who evaluated and answered the question, 
                which may differ from the difficulty in field 4.
                Field 6 is the relative path to the prefix of the article files. html files (.htm) and cleaned 
                text (.txt) files are provided.

We need the fields 2 & 3. We could use the fields 4 & 5 for filtering but I have not done this in this code.

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

### [Quora questions dataset](https://quoradata.quora.com/First-Quora-Dataset-Release-Question-Pairs)

From the dataset description:
        
                Our dataset consists of over 400,000 lines of potential question duplicate pairs. Each line contains IDs for each question in the pair, the full 
                text for each question, and a binary value that indicates whether the line truly cont

![Sample quora dataset](https://qph.fs.quoracdn.net/main-qimg-ea50c7a005eb7750af0b53b07c8caa60)

        Fields:
        
        id - ID of the question pair data entry
        qid1, qid2 - unique IDs of the questions in the quora database
        question1, question 2 - content of the 2 questions per entry
        is_duplicate - whether the 2 questions can be considered duplicate in terms of their meaning
        
We need question1 and question2 fields. Our seq2seq model will take a sampe question and generate another question which may or may not be duplicate. I did this because we are using a seq2seq model. I dont know if we can provide the is_duplicate parameter and based on it generate a duplicate question. 
        
Later I thought of filtering the questions and using only duplicate pairs for training (with is_duplicate == 1), so the model will generate a duplicate question, this reduced the number of samples to 149274 (from 404301).

There is some error in the dataset where some records are split across lines, those were filtered out. The records were further filtered to have max 12 words length which reduced the numbers to 22404.
        
        Read 40908 question pairs
        Trimmed to 22404 question pairs
        Counted words:
        quora_qs 10108
        quora_dupqs 10096
        
        
The output after train_iters:
        
        3m 53s (- 54m 34s) (5000 6%) 4.3584
        7m 41s (- 50m 1s) (10000 13%) 3.8761
        11m 29s (- 45m 59s) (15000 20%) 3.6009
        15m 18s (- 42m 5s) (20000 26%) 3.4004
        19m 9s (- 38m 18s) (25000 33%) 3.2962
        22m 59s (- 34m 28s) (30000 40%) 3.1678
        26m 49s (- 30m 38s) (35000 46%) 3.0587
        30m 39s (- 26m 49s) (40000 53%) 2.9845
        34m 29s (- 22m 59s) (45000 60%) 2.8974
        38m 21s (- 19m 10s) (50000 66%) 2.8274
        42m 12s (- 15m 20s) (55000 73%) 2.7859
        46m 3s (- 11m 30s) (60000 80%) 2.7280
        49m 55s (- 7m 40s) (65000 86%) 2.6517
        53m 47s (- 3m 50s) (70000 93%) 2.6326
        57m 39s (- 0m 0s) (75000 100%) 2.5869
        
Sample evaluation on random questions:

        > should i have snapchat ?
        = should i get snapchat ?
        < should i i have ? <EOS>

        > does green tea really reduces weight ?
        = does green chai tea assist with weight loss ?
        < does green tea burn belly fat ? <EOS>

        > what is the fastest way to lose weight safely ?
        = how can i lose weight quickly ?
        < what is the fastest way to lose weight ? <EOS>

        > what is the best gift you are ever received ?
        = what is the best physical gift you ve ever received ?
        < what is the best gift gift ? <EOS>

        > is it physically possible to travel back in time ?
        = is time travel possible after the discovery of gravitational waves ?
        < is it possible time travel in travel ? <EOS>

        > why does isis never disturb israel ?
        = why isn t isis attacking israel ?
        < why do isis israel israel ? <EOS>

        > which is the best mobile below ?
        = which is best mobile under ?
        < which mobile best mobile best mobile ? <EOS>

        > what is digital marketing exactly ?
        = what are the basics of digital marketing ?
        < what are the marketing on ? <EOS>

        > what would the world be like without electricity today ?
        = what would the world be like without electricity ?
        < what would be world without like ? <EOS>

        > who expects the spanish inquisition ?
        = does anyone expect the spanish inquisition ?
        < who anyone is the worst ? <EOS>

It is seen that though the model comes up with duplicate questions, most of them do not make sense, although training accuracy was 100% (need to check why!).
