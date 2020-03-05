## MLP: Layering is Magic

The real magic of deep learning is in the ability
to build models iteratively:
to _compose together_ multiple simple pieces into a single complex model,
just as, in a programming language,
we compose together simple pieces like constants, functions, and control flow
into a single complex program.
This makes our neural network able to do more things and better in the same way
that combining together mutliple objects or functions can make a program better.

The most basic version of this principle is the
_Multi-Layer Perceptron_, or MLP.
In an MLP, we take the output of one collection of perceptron units
and use that as the input to a new collection.
That is, we create a group of perceptrons
whose inputs that get weighted and summed together
are the outputs of other perceptrons,
rather than being data.
We call each piece a _layer_,
because they are built "one on top of the other",
like the layers of a cake or lasagna.
The new layer we added is called a _hidden layer_,
because it is neither an input nor an output.
State-of-the-art neural networks can have hundreds of hidden layers!

Check out
`mlp.py`
in the editor to see how this is done in `Keras`.
We've added a few lines at the top
for tracking our model with Weights & Biases,
but the important changes are in the definition of the model.
There are now _two_ calls to `keras.layers.Dense`.
The second one is from our single-layer perceptron.
The first one is new: it creates a layer of neurons
to feed into the perceptron that actually performs the classification.

If you run this code with
`python mlp.py`{{execute}},
you'll notice that the performance isn't better
than what we had with our single-layer network,
even though our network "should" have gotten stronger.

Look at the code for adding our new layer and ponder
what might be the cause --
are there any pieces that don't seem to make sense?
Test your hypothesis changing the code and running it
before moving on to the next step.
