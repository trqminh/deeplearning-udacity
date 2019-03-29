ref: https://github.com/vanhuyz/udacity-dl/blob/master/3_regularization.ipynb
# Note
+ l2 and dropout
![](https://github.com/1612374/deeplearning-udacity/blob/master/assign3/l2%20and%20dropout.jpg)
+ lr_decay
![](https://github.com/1612374/deeplearning-udacity/blob/master/assign3/lr_decay.jpg)


# Code
+ L2 regularization
```
tf.nn.l2_loss(weight)
```
+ Dropout
```
layer = tf.nn.dropout(layer, keep_prob = keep_prob)
```
+ Learning rate decay
```
global_step = tf.Variable(0)
starter_learning_rate = 0.5
learning_rate = tf.train.exponential_decay(starter_learning_rate, global_step,500,0.96)
optimizer = tf.train.GradientDescentOptimizer(learning_rate).minimize(loss, global_step=global_step)
```
