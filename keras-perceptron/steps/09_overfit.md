## In Too Deep

You might wonder why we stopped with a single layer.
Why not go dozens or hundreds of layers deep,
as in state-of-the-art models?

While this can make our loss go down even further,
it turns out that that doesn't mean our model is getting better.
Our model can start to find patterns in the specific examples
we are showing it that aren't real --
that don't _generalize_ to other data.

Think of the loss as our code testing suite,
checking to see whether our machine-learned program,
the model, has any bugs.
If we're allowed to look at the details of the test implementations,
then we might be able to find ways to cheat:
we might special-case the inputs that are actually being tested,
or even learn to take advantage of a bug in the tests!
Neural networks are very lazy programmers
and are always looking for ways to cheat.

The only way to protect against this is to run some tests
that the programmers never get to see and evaluate them on that basis.
This is usually done by _hold-out validation_:
we literally hold out, or hide from the model,
some of our data, then check how it does.
We call this data the _validation set_.
The `val_loss` and `val_acc` values you may have seen
in the terminal outputs are tracking the loss
and the accuracy on a validation set.

Run
`python overfit.py`{{execute}}.
While it's going, open the model code in the editor.
This model has a larger hidden layer than our old `mlp`,
and now it has two of them!
Over time the accuracy of this model will get close to 100%
on the training data,
the data the model is using to adjust the weights and biases.
But the accuracy on the validation set will not behave the same way.
Click the link to the visualization at Weights and Biases
to compare the training and validation loss and accuracy over time.

Try editing the code for this multi-layer perceptron
in a way that you think would make over-fitting worse.
Did it work?
Notice that as the model gets bigger,
training takes longer and longer to finish.
The size of the network is the major determinant
of computational expense in deep learning.

Once you've tried making over-fitting worse,
either check out the extra credit below,
which shows you how to reduce over-fitting,
or head to the next step to complete this scenario.

### Extra Credit:

One of the top techniques for reducing over-fitting
in MLPs is _DropOut_.
Adding it is like adding
an activation that randomly sets some fraction
of the activations to be exactly 0.
This prevents the network from easily learning patterns
that are too intricate and biases it to learning simpler things.

Here's the code to add a DropOut layer:
`model.add(tf.keras.layers.Dropout(0.5))`{{copy}}.

Where do you think it should be added?
Which layer is causing over-fitting?
Where do you think adding it would have the worst effect?
