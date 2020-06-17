# RNN-from-Scratch

Recurrent Neural Network(RNN) are a type of Neural Network where the output from previous step are fed as input to the current step. In traditional neural networks, all the inputs and outputs are independent of each other, but in cases like when it is required to predict the next word of a sentence, the previous words are required and hence there is a need to remember the previous words. Thus RNN came into existence, which solved this issue with the help of a Hidden Layer. The main and most important feature of RNN is Hidden state, which remembers some information about a sequence.

RNN have a “memory” which remembers all information about what has been calculated. It uses the same parameters for each input as it performs the same task on all the inputs or hidden layers to produce the output. This reduces the complexity of parameters, unlike other neural networks.

<img src="https://miro.medium.com/max/1400/1*K6s4Li0fTl1pSX4-WPBMMA.jpeg">

One issue with vanilla neural nets (and also CNNs) is that they only work with pre-determined sizes: they take fixed-size inputs and produce fixed-size outputs. RNNs are useful because they let us have variable-length sequences as both inputs and outputs. Here are a few examples of what RNNs can look like:

<img src="https://miro.medium.com/max/1400/0*toBP1hMLUPqAM-KI.jpg"> 

This ability to process sequences makes RNNs very useful. For example:

Machine Translation (e.g. Google Translate) is done with “many to many” RNNs. The original text sequence is fed into an RNN, which then produces translated text as output.

Sentiment Analysis (e.g. Is this a positive or negative review?) is often done with “many to one” RNNs. The text to be analyzed is fed into an RNN, which then produces a single output classification.

HOW IT WORKS:

Let’s consider a “many to many” RNN with inputs x_0, x_1, … x_n that wants to produce outputs y_0, y_1, … y_n. These x_i and y_i are vectors and can have arbitrary dimensions.

RNNs work by iteratively updating a hidden state h, which is a vector that can also have arbitrary dimension. At any given step t,
1.The next hidden state h_t is calculated using the previous hidden state h_{t-1} and the next input x_t.

2.The next output y_t is calculated using h_t.

<img src="https://miro.medium.com/max/1400/1*xOA99bS7A6utGocZ0l8L4g.png">

Here’s what makes a RNN recurrent: it uses the same weights for each step. More specifically, a typical vanilla RNN uses only 3 sets of weights to perform its calculations:

1. Wxh, used for all x_t → h_t links.

2. Whh, used for all h_{t-1} → h_t links.

3. Why, used for all h_t → y_t links.

We’ll also use two biases for our RNN:

1.b_h, added when calculating h_t.

2.b_y, added when calculating y_t.

We’ll represent the weights as matrices and the biases as vectors. These 3 weights and 2 biases make up the entire RNN!

EQUATION THAT PUTS EVERYTHING TOGETHER:

<img src="https://miro.medium.com/max/1400/1*FieGId293KkBQnTu7jL5_g.png">

