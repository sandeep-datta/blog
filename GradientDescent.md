---
title: "Understanding Gradient Descent"
use_math: true
---


## The cost function - Mean Squared Error (MSE)

### MSE for a single output neuron and $m$ input records

$$
  MSE_y = \frac{1}{2m} \sum_{\mu=1}^{m} (y_\mu - \hat{y_\mu})^{2}
$$

Where...

$\mu =$ index into the training data set with $\mu^{th}$ record : $\langle \vec{X_\mu}, y_\mu \rangle$.  
$\vec{X_\mu} = \mu^{th}$input record.  
$y_\mu = \mu^{th}$output record.  
$m = $ number of records in the training data.  

### MSE for $n$ output neurons and $m$ input records

$$
  MSE = \frac{1}{2mn} \sum_{\mu=1}^{m} \sum_{j=1}^{n}(y_{j,\mu} - \hat{y}_{j,\mu})^{2}
$$

$$
\hat{y_{j,\mu}} = f(h_{j,\mu})
$$

$$
h_{j,\mu} = \sum_{i=1}^{q} w_{j,i} \cdot x_{i, \mu}
$$

Where...

$j = j^{th}$ output neuron  
$n=$ total number of output neurons.  
$q=$ total number of inputs for each output neuron  
$y_{j,\mu}=$ expected value of the $j^{th}$ neuron for the $\mu^{th}$ input record  
$\hat{y_{j,\mu}}=$ current (calculated) value of the $j^{th}$ neuron for the $\mu^{th}$ input record  
$h_{j,\mu}=$ value of the $h$ for the $j^{th}$ neuron for the $\mu^{th}$ input record  
$w_{j,i} =$ the weight between the $j^{th}$ output neuron and the $i^{th}$ input (to that neuron).  
$x_{i, \mu}=$ the $i^{th}$ input in the $\mu^{th}$ input record  

### Minimizing MSE

#### Restating the MSE() formula in terms of the weights

* Since inputs and their corresponding outputs are fixed in the training phase the only thing that can change are the weights.
	* Hence MSE can now be viewed as a function of all the weights.

$$
C(\vec{W}) = MSE(w_{1,1}, w_{1,2}, ..., w_{1,m}, w_{2,1}, w_{2,2}, ..., w_{2,m},  ..., w_{n,m})=\\\frac{1}{2mn} \sum_{\mu=1}^{m} \sum_{j=1}^{n}(y_{j,\mu} - f(\sum_{i=1}^{q} w_{j,i} \cdot x_{i, \mu}))^{2}
$$

So in the above equation everything is a constant except for the weights which are free variables.

Now in order to minimize the multivariable function $C(\vec{W})$ we need to have ...

$$\nabla C(\vec{W}) = \vec{0}$$

i.e. ...

$$
\frac{\partial C(\vec{W})}{\partial w_{1,1}}=0, 
\frac{\partial C(\vec{W})}{\partial w_{1,2}}=0,
..., 
\frac{\partial C(\vec{W})}{\partial w_{1,m}}=0,
\frac{\partial C(\vec{W})}{\partial w_{2,1}}=0,
\frac{\partial C(\vec{W})}{\partial w_{2,2}}=0,
...,\\
\frac{\partial C(\vec{W})}{\partial w_{2,m}}=0,
...,
\frac{\partial C(\vec{W})}{\partial w_{n,m}}=0,
$$

#### Gradient w.r.t. arbitrary weight $w_{x,y}$
$$
\frac{\partial C(\vec{W})}{\partial w_{x,y}} =
\frac{\partial \left (\frac{1}{2mn}  
\sum_{\mu=1}^{m} 
\sum_{j=1}^{n}
(y_{j,\mu} - f(\sum_{i=1}^{q} w_{j,i} \cdot x_{i, \mu}))^{2}
\right )}{\partial w_{x,y}}
$$

$$
=
\frac{1}{2mn}  
\sum_{\mu=1}^{m} 
\sum_{j=1}^{n}
\frac{\partial \left (
(y_{j,\mu} - f(\sum_{i=1}^{q} w_{j,i} \cdot x_{i, \mu}))^{2}
\right )}{\partial w_{x,y}}
$$

#### Chain rule (of differentiation)

