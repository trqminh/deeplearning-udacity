## Skip-gram model


### Model
![](https://github.com/1612374/deeplearning-udacity/blob/master/assign5/skipgram.jpg)


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

+ The num_skip mean how many time use one to reuse the data, because you choose randomly the word nearby so use the data one
time is not fair.

+ And finally, you can use all the data at input or divide it to mini-batch depend on your data.


### Outputs

+ For each word in the input, we have probabilities of all the words in the dataset which one has the highest probability is
the nearest

