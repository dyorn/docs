description: Adjust the contrast of an image or images by a random factor.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.layers.experimental.preprocessing.RandomContrast" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="adapt"/>
</div>

# tf.keras.layers.experimental.preprocessing.RandomContrast

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.4/tensorflow/python/keras/layers/preprocessing/image_preprocessing.py#L1086-L1154">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Adjust the contrast of an image or images by a random factor.

Inherits From: [`PreprocessingLayer`](../../../../../tf/keras/layers/experimental/preprocessing/PreprocessingLayer.md)

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.keras.layers.experimental.preprocessing.RandomContrast`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.keras.layers.experimental.preprocessing.RandomContrast(
    factor, seed=None, name=None, **kwargs
)
</code></pre>



<!-- Placeholder for "Used in" -->

Contrast is adjusted independently for each channel of each image during
training.

For each channel, this layer computes the mean of the image pixels in the
channel and then adjusts each component `x` of each pixel to
`(x - mean) * contrast_factor + mean`.

#### Input shape:

4D tensor with shape:
`(samples, height, width, channels)`, data_format='channels_last'.



#### Output shape:

4D tensor with shape:
`(samples, height, width, channels)`, data_format='channels_last'.



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Raise</h2></th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
if lower bound is not between [0, 1], or upper bound is
negative.
</td>
</tr>
</table>





<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`factor`
</td>
<td>
a positive float represented as fraction of value, or a tuple of
size 2 representing lower and upper bound. When represented as a single
float, lower = upper. The contrast factor will be randomly picked between
[1.0 - lower, 1.0 + upper].
</td>
</tr><tr>
<td>
`seed`
</td>
<td>
Integer. Used to create a random seed.
</td>
</tr><tr>
<td>
`name`
</td>
<td>
A string, the name of the layer.
</td>
</tr>
</table>



## Methods

<h3 id="adapt"><code>adapt</code></h3>

<a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.4/tensorflow/python/keras/engine/base_preprocessing_layer.py#L53-L66">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>adapt(
    data, reset_state=(True)
)
</code></pre>

Fits the state of the preprocessing layer to the data being passed.


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Arguments</th></tr>

<tr>
<td>
`data`
</td>
<td>
The data to train on. It can be passed either as a tf.data
Dataset, or as a numpy array.
</td>
</tr><tr>
<td>
`reset_state`
</td>
<td>
Optional argument specifying whether to clear the state of
the layer at the start of the call to `adapt`, or whether to start
from the existing state. This argument may not be relevant to all
preprocessing layers: a subclass of PreprocessingLayer may choose to
throw if 'reset_state' is set to False.
</td>
</tr>
</table>




