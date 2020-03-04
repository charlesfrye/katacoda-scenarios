Once we've trained a model,
it's time to deploy it to production.

Open up `predict.ipynb` in Jupyter.

Running this notebook will select a digit
from a collection the perceptron model has never seen:
the _test dataset_.
It then passes that digit to the model
and determines what our neural network thinks the class is.

Our perceptron is very good,
so it usually gets the answer right,
but it still makes some mistakes,
about 10% of the time.
If you search, you should be able to find one.
Does the mistake make sense? Why or why not?
