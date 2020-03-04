## The Importance of Being Normal

Even though the model accuracy was quite high,
it can still be made higher.

If you go back to `digits.ipynb`,
you'll see that the values in our inputs are between 0 and 255 --
they are one byte integers.

There's nothing inherently wrong with this.
It's possible to train machine learning algorithms
no matter what the scale of the inputs.
But machine learning algorithms like the perceptron have lots
of parameters to fiddle with:
how do I pick initial values of the weights and biases?
how quickly do I update them?

A framework like `Keras` tries to make sensible choices for all of these parameters,
but those choices come with assumptions.
One of the most important assumptions is that the input data's average value is close to zero
and the values vary on a scale of about 1:
that the data is _normalized_.

There are many strategies for normalizing data,
like _z_-scoring and PCA-whitening.
One of the simplest just sets the range of the data to be between 0 and 1.

Run
`python perceptron-normalize.py`{{execute}}
to see what the impact of this change is on performance.

How do we quantify the improvement?

We might see a gain of a few percentage points in accuracy:
from ~89% to about 93%.
While that may seem modest, it means that for every 3 mistakes
the un-normalized model makes, the normalized model makes only 2.
In serious applications, this can mean
saved lives or substantial cost savings.

You may have noticed an extra line at the end:
`model.save`.
This line makes your model portable
by saving all the parameters,
the weights and biases,
into a file.
Head to the next step to load this file
and take a look at the model predictions.
