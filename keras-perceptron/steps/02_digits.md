## Hello, World of Deep Learning!

First, we need to familiarize ourselves with what goes into our network.

In Jupyter, open up `digits.ipynb`.

This notebook shows you what the data looks like for the machine learning problem
we'd like our perceptron to solve:
as inputs, hand-written digits and, as desired outputs, their identities.

Check out the data:
how are the hand-written digits represented?
what about their labels?
what are their types?
what is the largest possible input value?

In machine learning, the most important data type is the
multi-dimensional array, or _tensor_ --
hence the name `tensorflow` for one of the most popular
deep learning libraries.
Multi-dimensional arrays are like nested lists of numbers --
for each layer of lists, we say the array has one dimension.
A one-dimensional array is often called a vector,
and it is a homogeneous list of numbers.
A two-dimensional array is often called a matrix,
and it is just a list of vectors.

Notice that the labels come in as numbers,
in `y_train`,
but then get transformed into something different,
called a "one-hot vector",
by `to_categorical`.
How might we read off the class of a digit
from its one-hot vector?
Try a few different indexes and see if you can
find the pattern.
Why might we encode digit class this way?
Hint: a `2*2==4`. but something that looks
twice as much like a two doesn't look more like a four.

Once you've finished exploring the data,
head to the next step to train your first simple perceptron!
