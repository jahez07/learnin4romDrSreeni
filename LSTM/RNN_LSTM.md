# **Recurrent Neural Networks (RNN) & Long-Short-Term Memory (LSTM)**

**Traditional Deep Learning**
We will have an input image which is passed through a **Convolutional** which extracts features from the input and then pass it to **Max Pool** Layers which is then passed to **Fully Connected** Dense layers from which we get the output. And the output would be a probability of class.

The difference between the *Traditional Deep Learning Model* and *Recurrent Network* is that traditional DL is a feed forward network and in RNN the information is also back propagated, in simpler terms RNN remembers the past.<br>
Summary is that Recurrent Nueral Networks are different from normal Nueral Networks in the fact that they remember the past. RNNs have memory.

**How do RNNs remember and Why do we need them?**<br>
When we consider rembering the past and time series data, one of the important topic is **Autocorrelation**. <br>

Autocorrelation measures the similarity between a time sereies and a lagged version of itself, essentially qualifying how a data point's current value is related to its past values at specific time intervals (lags). It's also known as serial correlation or serial dependence, and it indicates whether there's a predictable pattern within the data series itself. **Positive autocorrelation** means _high values follow high values_, while **negative  autocorrelation** means _high values are followed by low values._
