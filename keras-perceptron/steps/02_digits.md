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

Once you've finished exploring the data,
head to the next step to train your first simple perceptron!
