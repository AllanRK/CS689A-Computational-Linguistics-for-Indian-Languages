# CS - 689A Assignment 1
# Name - Allan Robey
# Roll No - 22111007

Note:Here all the tasks have been performed on 122MB of data file due to constraints of the system.

## Libraries:

pandas

collections

pandas

matplotlib.pyplot

inltk

re 

conllu 


## Steps to Run Assignment:

1. Extract 22111007_Assignment1.zip in your local system. Then extract the tokens file and token_dict file {7 zip recommended}. These file contain tokens and their frequencies and all the further processing will be done after importing them.

2. Open 22111007.ipynb file in your idle environment. Change the data path according to your file location(second cell).

3. Run according to below Question instruction and information.

## Question 1 :

To perform Unicode Correction-

Before performing unicode correction, I have taken a list of words from the extracted data file and 
removed the punctuation marks

Step1: Here I have taken a list of swar,vyanjan & matra along with a dictionary that maps the matra's
to the corresponding swar.

Step2:For a corresponding word if word[i] is a swar then it doesn't need unicode correction
 
Step3: If word[i] is a vyanjan then a '्' is added to word[i] then I check the following conditions:
       a) if word[i+1] is a vyanjan or a swar then I will correct it by adding a swar 'अ'  to word[i]
       b) if word[i+1] is a matra then I will map the matra to the corresponding swar and add that 
       swar to word[i]
       c) if the corresponding vyanjan word[i] is the last character in the word I add a swar 'अ'  to word[i] 
       d) if word[i+1] is a '्' or some other marks I will pass it

Step4: If word[i] is a matra then I will check if word[i-1] is in [',','_','|','-','(',')','[',']','!','?','"','{','}','^','*','%','/',':-','।','.','़']  if yes then
       then I will map the matra with the corresponding swar.

Example: आ व् ए द् अ न् अ  is the unicode corrected word for आवेदन

## Question 2 :

Here token is considered as a white-spaced separated sequence of characters
and for each token the characters and syllables are found out and storing a list of them and the tokens 
in descending order of their frequencies.

For obtaining syllables 2 methods have been defined get_syllables and get_Vyanjan
for otaining the syllables in a word
if word[k] is a swar it will be considered a syllable
if word[k] is a vyanjan then to obtain the syllables check the following conditions 
by using method get_Vyanjan:

1. if work[k+1] is a vyanjan then return word[k] as syllable
2. if work[k+1] is a swar or a matra  then return word[k]+word[k+1] as syllable
3. if word[k+1] is a '्'  then return word[k]+word[k+1]+get_Vyanjan as a syllable
 i.e recurssively call the get_Vyanjann method to obtain the syllable
4. if word[k] is last character simply return it as a syllable
5. if k exceeds word length return null

After obtaining the list of tokens, characters and syllables the bigram frequencies of tokens, 
characters and syllables have been obtained.

## Question 3 :

BPE for Vocabulary Sizes of 1k, 2k, 3k
References:"https://towardsdatascience.com/byte-pair-encoding-the-dark-horse-of-modern-nlp-eb36c7df4f10"

Step 1. Initialized the vocabulary.

Step 2. Each word in the corpus is then represented as a combination of the characters along with </w> 
to indicate the end of word token 

Step 3. Then the character pairs in all tokens of the vocabulary have been counted iteratively.

Step 4. Every occurrence of the most frequent character pair have been merged

Step 5. Adding the new character n-gram to the vocabulary.

Step 5. Step 4 has been then repeated until the desired number of merge operations have been completed
 or the desired vocabulary size have been achieved which is indicated by a hyperparameter.


For each token found, the characters and syllables have been obtained.
Store them in a list and tokens in descending order of their frequencies.

Then bigram frequencies of tokens, syllables and characters have been obtained.

## Question 4 :

Precision, Recall and F-score has been computed.

## Question 5 :

Extracting a list of lemmas found in the UD-tagged files.
For this conllu module has been used to parse the annotations and to store it in sentences
Lemma has been extracted as sentences[i][j]['lemma']

## Question 6 :

Determined whether frequency of whitespace-separated words, BPE tokens, syllables, characters and lemma 
found in Question 2, 3 and 5 follows Zipfian distribution.

Here the expected Zipfian distribution have been ploted which follows Zipf's rule as - the most frequent word 
will occur approximately twice as often as the second most frequent word, three times as often as the 
third most frequent word, etc.
Then the frequency of whitespace-separated words, BPE tokens, syllables, characters and lemma 
found in Question 2, 3 and 5 have been shown as Histogram.
If the Histogram follows or nearly follows the expected Zipfian distribution then it has been concluded that
it follows Zipfian distribution.

## Question 7 :

Here the surface form has been stripped from the last until it matches the lemma 
if it matches the lemma then the stripped part has been returned as the suffix.
Displaying top 50 suffix.

The stripped suffix  are then compared with list of suffix which are correct form of suffix
according to knowledge of Hindi as suffix_from_knowledge = ['टिक', 'होन','लेन ','घट','गाङी ','सुत ','दया ','औना ','नी','ना ','आन','आई ','वट',
'ई','आहट','आव','औती','ना','ई ','य ','ता']  As it falls under categories of suffix in hindi as given below were considered:
1)कृत्तवाचक कृत प्रत्यय (Krit krit Pratyay)
2) कर्मवाचक कृत प्रत्यय (Karmvachak krit Pratyay)
3) भाववाचक कृत प्रत्यय (Bhavvachak krit pratyay)
4) करणवाचक कृत प्रत्यय (karanvachak krit pratyay)
5) संस्कृत प्रत्यय (Sanskrit pratyay)




 











