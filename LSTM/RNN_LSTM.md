# **Recurrent Neural Networks (RNN) & Long-Short-Term Memory (LSTM)**

Source: [165 -An Introduction to RNN and LSTM](https://youtu.be/Mdp5pAKNNW4?si=lGIekH2AbpLY-uSE)

## **Difference b/w Recurrent Nueral Network & Traditional Deep Learning**
We will have an input image which is passed through a **Convolutional** which extracts features from the input and then pass it to **Max Pool** Layers which is then passed to **Fully Connected** Dense layers from which we get the output. And the output would be a probability of class.

The difference between the *Traditional Deep Learning Model* and *Recurrent Network* is that traditional DL is a feed forward network and in RNN the information is also back propagated, in simpler terms RNN remembers the past.<br>

Summary is that Recurrent Nueral Networks are different from normal Nueral Networks in the fact that they remember the past. RNNs have memory.

## **How do RNNs remember and Why do we need them?**
When we consider rembering the past and time series data, one of the important topic is **Autocorrelation**. <br>

### **Autocorrelation**
Autocorrelation measures the similarity between a time sereies and a lagged version of itself, essentially qualifying how a data point's current value is related to its past values at specific time intervals (lags). It's also known as serial correlation or serial dependence, and it indicates whether there's a predictable pattern within the data series itself. **Positive autocorrelation** means _high values follow high values_, while **negative  autocorrelation** means _high values are followed by low values._

#### **How it Works?**
* **Time Series Data**: Autocorrelation applies to data collected over time, such as daily temperatures or monthly sales figures.
* **Lagging**: A lagged version of the data means shifting the series by a certain number of time periods (e.g., comparing today's temperature with yesterday's which is a lag of 1).
* **Correlation**: You then calculate the standard correlation coefficient between the original series and its lagged version at various lags.
* **Patterns**: A high correlation at a specific lag suggests a pattern; for example, strong autocorrelation at lag 12 for monthly data might signal a yearly seasonal trend.

#### **Why it's important?**
* **Predictive Power**: Autocorrelation helps in predicting future values in a time series based on past behaviour.
* **Model Diagnostics**: The presence of autocorrelation in the residuals (errors) of a time series model can indicate that the model is not capturing the full temporal structure of the data, suggesting the model be "unsound".
* **Applications**: It's used in fields like econometrics, signal processing, demand forecasting, and even in GPS technology to improve accuracy.

#### **Types of Autocorrelation**
* **Positive Autocorrelation**: When high values are likely to be followed by high values, and low values by low values (e.g., a stock rally)
* **Negative Autocorrelation**: When high values tend to be followed  by low values and vice-versa (e.g., mean-reverting processes).

#### **Tools for Analysis**
* **Autocorrelation Function (ACF)**: A common tool used to calculate and visualize the correlation coefficients across different lags, helping to identify repeating patterns or seasonalities.


In time series data, we compare one column to itself and not other features, and that is called autocorrelation, for which we need **RNN** Simple example, I have a table with two columns 'Day' & 'Food'. What food I eat today depends on what food what I had in the past and not on what day it is. This shows that the data point is compaired to the same column and not to the other column, for that is that usual case of Normal Nueral Networks. 

## **Unrolling an RNN**
RNNs are "unrolled" programmatically during training and prediction.
![Alt text](/RNN.png "RNN")