Things below is how I understand about word2vec model (skip-gram and cbow), so fix me if I am wrong
## Skip-gram model


### Model
![](https://github.com/1612374/deeplearning-udacity/blob/master/assign5/skipgram.jpg)

Softmax regression, not logistic regression with softmax


### Input and labels
#### Generate labels and input from dataset:
+ One word in the vector input has a label.
+ For example: we have the words dataset 
```
data: ['anarchism', 'originated', 'as', 'a', 'term', 'of', 'abuse', 'first', 'used', 'against', 'early', 'working', 'class', 'radicals', 'including', 'the']
```
+ We define two variable: num_skip and skip_window, for example 2 and 3 respectively.

+ The skip_window mean the size of the word near it, if 'as' in the input, we can choose one of six word near it to be an labels
(3 leftside, 3 rightside).

+ Therefore, we have two conditions: batch_size(input_record_size) % num_skip == 0 and num_skip <= 2*skip_window

+ The num_skip mean how many time use one to reuse the data, because you choose randomly the word nearby so use the data one
time is not fair.

+ And finally, you can use all the data at input or divide it to mini-batch depend on your data.


### Outputs

+ For each word in the input, we have probabilities of all the words in the dataset which one has the highest probability is
the nearest

## CBOW model

![](https://github.com/1612374/deeplearning-udacity/blob/master/assign5/cbow_model.jpg)

### Input and labels
#### Generate labels and input from dataset:

+ The inputs are BOWs with size num_cbow, and each input 's label is the context meaning of this BOW from all
the vocabularies.
+ Generate input and label from dataset
+ Pick the label first, that is one word from the dataset, choose the element for CBOW (size: num_cbows) input
which are in the cbow_window of the label (the same as skip gram)
+ So we also have two condition: batch_size % num_cbows == 0 and num_cbows <= 2*cbow_window

### Outputs

+ For each BOWs in the input, we have probabilities of all the words in the dataset which one has the highest probability is
the BOW context meanning

