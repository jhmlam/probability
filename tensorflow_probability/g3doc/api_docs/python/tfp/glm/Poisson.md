Project: /probability/_project.yaml
Book: /probability/_book.yaml
page_type: reference
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfp.glm.Poisson" />
<meta itemprop="property" content="is_canonical"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="log_prob"/>
</div>

# tfp.glm.Poisson

## Class `Poisson`

Inherits From: [`ExponentialFamily`](../../tfp/glm/ExponentialFamily.md)

`Poisson(rate=mean)` where `mean = exp(matmul(X, weights))`.

## Properties

<h3 id="is_canonical"><code>is_canonical</code></h3>

Returns `True` when `variance(r) == grad_mean(r)` for all `r`.

<h3 id="name"><code>name</code></h3>

Returns TF namescope prefixed to ops created by member functions.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(name=None)
```

Creates the ExponentialFamily.

#### Args:

* <b>`name`</b>: Python `str` used as TF namescope for ops created by member
    functions. Default value: `None` (i.e., the subclass name).

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    predicted_linear_response,
    name=None
)
```

Computes `mean(r), var(mean), d/dr mean(r)` for linear response, `r`.

#### Args:

* <b>`predicted_linear_response`</b>: `float`-like `Tensor` corresponding to
    `tf.matmul(model_matrix, weights)`.
* <b>`name`</b>: Python `str` used as TF namescope for ops created by member
    functions. Default value: `None` (i.e., 'call').


#### Returns:

* <b>`mean`</b>: `Tensor` with shape and dtype of `predicted_linear_response`
    representing the distribution prescribed mean, given the prescribed
    linear-response to mean mapping.
* <b>`variance`</b>: `Tensor` with shape and dtype of `predicted_linear_response`
    representing the distribution prescribed variance, given the prescribed
    linear-response to mean mapping.
* <b>`grad_mean`</b>: `Tensor` with shape and dtype of `predicted_linear_response`
    representing the gradient of the mean with respect to the
    linear-response and given the prescribed linear-response to mean
    mapping.

<h3 id="log_prob"><code>log_prob</code></h3>

``` python
log_prob(
    response,
    predicted_linear_response,
    name=None
)
```

Computes `D(param=mean(r)).log_prob(response)` for linear response, `r`.

#### Args:

* <b>`response`</b>: `float`-like `Tensor` representing observed ("actual")
    responses.
* <b>`predicted_linear_response`</b>: `float`-like `Tensor` corresponding to
    `tf.matmul(model_matrix, weights)`.
* <b>`name`</b>: Python `str` used as TF namescope for ops created by member
    functions. Default value: `None` (i.e., 'log_prob').


#### Returns:

* <b>`log_prob`</b>: `Tensor` with shape and dtype of `predicted_linear_response`
    representing the distribution prescribed log-probability of the observed
    `response`s.



