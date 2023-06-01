# CS - 689A Assignment 2
# Name - Allan Robey
# Roll No - 22111007

##Libraries used - 

conllu
operator
collections
headpq

## Steps to run the assignment-

1. Extract 22111007_Assignment2.zip in your local system{7 zip recommended}.
2. Open Assingment2_22111007_Question1.ipynb and Assingment2_22111007_Question1.ipynb file in your idle environment. Change the data path according to your file location(second cell).
3. Run according to below Question instruction and information.


----------------------------------------QUESTION - 1---------------------------------------------------------

######################Question 1-a :

To find the frequencies of POS tags of words--

For this conllu module has been used to parse the annotations and to store it in sentences.
The pos tag has been extracted as sentences[i][j]['upos']
Frequency of POS tags of words and frequency of POS tags of each word has been determined.


######################Question 1-b :

To list the 50 most frequent words corresponding to each POS tag

######################Question 1-c :

To find the frequencies of gender, case and number of words separately
gender = sentences[i][j]['feats'].get('Gender',None)
case = sentences[i][j]['feats'].get('Case',None)
number = sentences[i][j]['feats'].get('Number',None)

######################Question 1-d :

To list the 50 most frequent combinations of gender, case and number as a 3-tuple
Frequencies has been considered in 2 cases:
case 1: When either of gender, case or number cannot be none
case 2: When either of gender, case or number can be none

######################Question 1-e :

To find the frequencies of POS tags corresponding to only head words
The value of sentences[i][j]['misc']['ChunkType'] is used to determine whether a corresponding word is a head 
word or not.

######################Question 1-f :

To find the directed POS tag tuples, i.e., <ti, tj >. For each such 2-tuple, list thefrequencies separately
for each relation R as well as total.
The dependancy relation can be determined using sentences[i][j]['deprel']


######################Question 1-g :

For each dependency relation R, list the frequencies separately for each 2-tuple<ti, tj> as well as total.


----------------------------------------QUESTION - 2---------------------------------------------------------

######################Question 2-a :

Fine-tune the pre-trained BERT model for the UPOS prediction task 
by tuning the different hyper-parameters of the model such as batch-size, epoch and learning-rate to obtain 
higher accuracy. 

######################Question 2-b :

To list precision, recall, F-score (both micro and macro)
Precision, Recall and F-score has been obtained on both validation dataset and test dataset.
macro_precision = (precision1 + precision2)/2
macro_recall = (recall1 + recall2)/2
macro_f_score = 2*(macro_precision * macro_recall) /(macro_precision + macro_recall)




