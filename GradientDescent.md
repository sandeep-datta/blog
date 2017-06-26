
---
title: "Understanding Gradient Descent"
use_math: true
---


## The cost function - Mean Squared Error (MSE)

### MSE for a single output neuron and $m$ input records


\begin{align}
  MSE_y = \frac{1}{2m} \sum_{\mu=1}^{m} (y_\mu - \hat{y_\mu})^{2}
\end{align}


Where...

$\mu =$ index into the training data set with $\mu^{th}$ record : $\langle \vec{X_\mu}, y_\mu \rangle$.
$\vec{X_\mu} = \mu^{th}$input record.
$y_\mu = \mu^{th}$output record.
$m = $ number of records in the training data.

### MSE for $n$ output neurons and $m$ input records

\begin{equation}
  MSE = \frac{1}{2mn} \sum_{\mu=1}^{m} \sum_{j=1}^{n}(y_{j\mu} - \hat{y_{j\mu}})^{2}
\end{equation}

Where...
$j = j^{th}$ output neuron 
$n = $ total number of output neurons.

### To do: Minimize MSE

* Since inputs and their corresponding outputs are fixed in the training phase the only thing that can change are the weights.
