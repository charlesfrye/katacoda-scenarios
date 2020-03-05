We added the softmax activation
to our classification layer
because we wanted to make sure
that our outputs looked like the
ones we were asking our network to mimic.

But there's no reason why the internals of our network
should look like the final answers --
in a computer program,
that'd be like requiring everything inside the function
to have the same type as the thing being returned!

Pick one of the other valid values for the activation keyword:
`"elu"`, `"relu"`, `"selu"`, `"softplus"`, `"sigmoid"`, or `"linear"`.
Replace the `"softmax"` in the call to `model.add`
our hidden layer with one of these choices.
If you're working through with a friend,
you should both pick different values.

Then, run the code with
`python mlp.py`{{execute}}.

Which, if any, of these choices improves the network's performance at the end of training?
Do any of them stand out?
Use Weights and Biases to compare the losses and accuracies
during training.
Is there a difference in the speed of training for any of these choices?

We encourage you to explore these activation functions here,
but know that the most common choice is `relu`,
the _REctified Linear Unit_.
It has some small advantages, but its popularity is probably as much historical accident
as it is based in any real superiority.

Once you're done trying out activation functions --
and don't forget that you can check out your model with `predict.ipynb`,
just change the model name to `mlp.h5` --
head to the next step.
