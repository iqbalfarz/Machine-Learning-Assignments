# Image Document Classification using Transfer Learning in CNN

**NOTE: Use Google Colab to run this project,[Click Here](https://colab.research.google.com/drive/13A4TuM8gO-AodUfL0AUkq5fvXii_xebn?usp=sharing) to open jupyter notebook.**

## Problem Statement
Classifying the documents among 16 given classes.

It is a multi-class classification problem.

## Data
__Dataset__: Dataset contains few thousand photos of documents belonging to 16 classes

__Data Distribution:__ 
![image](https://user-images.githubusercontent.com/32350208/122882842-384cb280-d35a-11eb-9528-4ad63ace91ba.png)

_Data distribution(in number)_
<pre>
'0': 3016,
'1': 2994,
'10': 3002,
'11': 2992,
'12': 3006,
'13': 3007,
'14': 3006,
'15': 2996,
'2': 2993,
'3': 3005,
'4': 2994,
'5': 2999,
'6': 2985,
'7': 3000,
'8': 3003,
'9': 3002
</pre>

__Sample Data__:

![image](https://user-images.githubusercontent.com/32350208/122882997-5d412580-d35a-11eb-8d70-6dd1b93ef734.png)

__Dataset Format__:

Dataset is given in the form of Nested Folders containing photos. 

Another dataframe is given with the path of images and their corresponding labels.

__Sample Dataframe__:

|Index  |Path                                             |Label|
| :---  |  :----:                                         | ---:|               
|10155	|imagesj/j/i/w/jiw43c00/89638854_8861.tif	        |6    |
|45402	|imagesb/b/x/k/bxk05e00/2040785858.tif	          |10   |
|34244	|imagesi/i/u/d/iud42e00/2500090606_2500090631.tif	|12   |
|46324	|imagesp/p/v/z/pvz46c00/2505161384_1385.tif	      |1    |
|25642	|imagesf/f/q/c/fqc66d00/504315522+-5526.tif	      |3    |

__Load dataset:__

I used `tf.keras.preprocessing.image.ImageDataGenerator()` and `flow_from_dataframe()` to load the dataset and do some preprocessing.

## Callbacks
* __ModelCheckpoint__: Used to save the model on best found metrics value.
* __decayLR(custom)__: Used to decay the learning rate with some constraints.
* __TerminateOnNaN__ : Used to terminate training if the value of weights/bias becomes NaN
* __EarlyStopping__  : Used to stop training on given circumstances(Stop the training if validation accuracy is not increasing).
* __TensorBoard__    : Used to track the loss, weights, and bias distributions.
## Models

__Model 1__:
<pre>
1. Use <a href='https://www.tensorflow.org/api_docs/python/tf/keras/applications/VGG16'>VGG-16</a> pretrained network without Fully Connected layers and initilize all the weights with Imagenet trained weights. 
2. After VGG-16 network without FC layers, add a new Conv block ( 1 Conv layer and 1 Maxpooling ), 2 FC layers and a output layer to classify 16 classes. You are free to choose any hyperparameters/parameters of conv block, FC layers, output layer. 
3. Final architecture will be <b>INPUT --> VGG-16 without Top layers(FC) --> Conv Layer --> Maxpool Layer --> 2 FC layers --> Output Layer</b>
4. Train only new Conv block, FC layers, output layer. Don't train the VGG-16 network. 
</pre>
![image](https://user-images.githubusercontent.com/32350208/122886056-3f28f480-d35d-11eb-9daa-127b2d0cf6f0.png)

__Model 2__:
<pre>
1. Use <a href='https://www.tensorflow.org/api_docs/python/tf/keras/applications/VGG16'>VGG-16</a> pretrained network without Fully Connected layers and initilize all the weights with Imagenet trained weights.
2. After VGG-16 network without FC layers, don't use FC layers, use conv layers only as Fully connected layer. any FC layer can be converted to a CONV layer. This conversion will reduce the No of Trainable parameters in FC layers. For example, an FC layer with K=4096 that is looking at some input volume of size 7×7×512 can be equivalently expressed as a CONV layer with F=7,P=0,S=1,K=4096. In other words, we are setting the filter size to be exactly the size of the input volume, and hence the output will simply be 1×1×4096 since only a single depth column “fits” across the input volume, giving identical result as the initial FC layer. You can refer <a href='http://cs231n.github.io/convolutional-networks/#convert'>this</a> link to better understanding of using Conv layer in place of fully connected layers.
3. Final architecture will be VGG-16 without FC layers(without top), 2 Conv layers identical to FC layers, 1 output layer for 16 class classification. <b>INPUT --> VGG-16 without Top layers(FC) --> 2 Conv Layers identical to FC --> Output Layer</b>
3. Train only last 2 Conv layers identical to FC layers, 1 output layer. Don't train the VGG-16 network. 
</pre>
![image](https://user-images.githubusercontent.com/32350208/122886192-5b2c9600-d35d-11eb-8977-cc0bb26617b6.png)


__Model 3__:
<pre>
1. Use same network as Model-2 '<b>INPUT --> VGG-16 without Top layers(FC) --> 2 Conv Layers identical to FC --> Output Layer</b>' and train only Last 6 Layers of VGG-16 network, 2 Conv layers identical to FC layers, 1 output layer.
</pre>
![image](https://user-images.githubusercontent.com/32350208/122886764-de4dec00-d35d-11eb-8676-97d2897e3837.png)

## Metrics
* I used **Accuracy** as a metric. Our dataset is balanced, so, there is no problem to use accuracy as a metric.

## Performance of Models

| Model   | Accuracy(%) |
| :---    | ---:        |
| Model 1 | 73.28       |
| Model 2 | 72.00       |
| Model 3 | 06.25       |

## Run 
Use Google Colab to run this Notebook.

## Credits
* [AppliedAICourse](https://www.appliedaicourse.com): For teaching an in-depth Machine Learning and Deep Learning.

## Summary
For Model1 and Model2 we get good accuracy. 
But, for Model3 we are not getting good result because we are training last 6 layers of VGG.
As we know Our dataset is different than ImageNet dataset, that is the reason we are not getting good result in the case of 3rd Model.


