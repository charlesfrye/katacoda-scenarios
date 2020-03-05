## `softmax` for Fun and Profit

You probably found that your perceptron didn't work very well:
that it was performing only a little better than chance (10%).

We can fix this by making two changes:
first, we need to make sure our network outputs look
like the desired outputs.
Right now, they are just weighted sums of the inputs,
and there is nothing stopping them from being negative or from being very large.

But if we look at the desired outputs,
for example using `digits.ipynb`,
we'll see that the correct answer is always a 1 in one place
and zeroes everywhere else.
We'd like our outputs to look more like that:
never negative, never bigger than one.

We can fix this by applying a non-linear function after our weighted sum.
In the neural network world, these are called `activation` functions.

If you open up `perceptron.py`,
you'll notice a change to our most important line:
when we create our ten neurons and add them to the model,
we pass the keyword argument `activation='softmax'`.
The softmax activation is designed to make our outputs
non-negative and less than or equal to 1.
Even better, it makes them add up to 1,
which means we can interpret them as probabilities:
for a well-trained model,
the output of neuron 3 is the probability that the input is a 3.

With this new type of output, we need a new type of `loss`.
If you check out `model.compile`, you'll see that now `loss='categorical_crossentropy'`.
This loss is more complicated than just the mean squared error,
but in short it's big whenever we have a small output for the correct answer:
in fact, if the neuron corresponding to the right answer puts out a 0,
this loss is infinite!

Run
`python perceptron.py`{{execute}}
and observe the performance of this new style of perceptron.

Is the accuracy better? (and do we want accuracy to be high or low?)
What about the loss? (again, should that be big or small?)
Does it make sense to directly compare the values of the losses?

Are you satisfied with the accuracy of your model?
Think of some potential applications for this model,
and try to guess what level of accuracy they'd require --
automatically detecting street numbers in a robotic delivery truck,
reading vehicle license plates at a highway toll,
partially digitizing documents before humans edit them.
Is this model sufficient for any of these?

Once you've trained this model and answered the questions,
proceed to the next step.
