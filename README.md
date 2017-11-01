# CNN-cifar10

The project uses mid-level Tensorflow API to build a CNN for image recognition.

## Architecture

The architecture we used is Conv1->Norm1->Pool1->Conv2->Norm2->Pool2->Conv3->Conv4->Norm3->Pool3->Fully_Conne ct1->Fully_Connect2->Dropout->Logits

Conv1 has 32 filters [5,5]

Norm1, Norm2, Norm3 are local-response-normalization Layers

Pool1, Pool2, Pool3 have pool size = [2,2], strides = 2

Conv2 has 64 filters [5,5]

Conv3 has 128 filters [3,3]

Conv4 has 128 filters [3,3]

Fully_Connect1 has size 2048

Fully_Connect2 has size 1024

The architecture of the network could be seen below:
![ScreenShot](https://s1.postimg.org/5pazh8x5lb/CNN-cifar10-architecture.png)

## Other information regarding the CNN

Normalization is performed on input data **before training**

Activation Function: **Elu** (for Conv layers only)

Optimizer: **RMS Prop Optimizer**

Learning Rate: **0.0005 for 3000 steps, 0.00025 for 2000 steps, 0.0001 for 2000 steps**

Batch Size: 128

Dropout Probability: **0.5**

L2 regularization parameter: **0.1**

Duration of training: ~70 minutes

Size of training data: 45000 * 32 * 32 * 3 (no data augmentation)

Output at stage 8000 is

step: 8000, training accuracy: 1, loss: 0.007492, validation accuracy: 0.775600

The final validation accuracy is **0.7758**

The train accuracy, validation accuracy and loss could be seen below
![ScreenShot](https://s1.postimg.org/1yzv7z99qn/Train-acc.png)
![ScreenShot](https://s1.postimg.org/5pazh8xsqn/Validation-acc.png)
![ScreenShot](https://s1.postimg.org/168ye9rwdb/Loss-graph.png)

The historgrams of CNN layers and the last fully-connected layer could be seen below
![ScreenShot](https://s1.postimg.org/16mzq8svq7/Histogram.png)
