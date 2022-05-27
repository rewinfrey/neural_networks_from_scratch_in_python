### What is a neural network?

"Artificial" neural networks are modeled after the human brain.

The basic unit of a neural network is the neuron.  A neural network is the combination of hundred or thousands (or more) of nuerons.  The interconnectivity produces relationships and results that often perform better compared with other machine learning methods.

The most common type of layer is a dense layer.  These are layers of interconnected neurons.  In a dense layer,  each neuron in one layer is connected to every other neuron in the next layer.  An edge between neurons indicates the input / output relationship between neurons.  Each edge can also have a label or property called a weight.  This weight indicates how much of the output / input to use,  and is a constant multiplied to the input value.

       weight: 10
[ A ] -----------> [ B ]  => yields:  B input value = A output value * weight.  The resulting input value for neuron B is 10 (weight) * 2 (output value from neuron A) = 20
        value: 2

Neuron A is connected to neuron B.  This means the output from neuron A is the input of neuron B.  If the weight of the connection between neuron A and neuron B is 10,  and if the input value for neuron B is 2,  then the resulting input value for neuron B is 20.

       weight: 10
[ A ] -----------> [ B ]
        value: 2
                     ^
       weight: 5     |
[ C ] ---------------|
        value: 1

Neuron A and neuron C are connected to neuron B.  To calculate the total input for neuron B,  each connected neuron's output is multiplied by their respective weight,  and each of these values is summed to yield the final input value for neuron B.

(2 * 10) + (5 * 1) = 26 is the final input value for neuron B.

In addition to these input values,  a bias can also be used as an additional trianable parameter.  The bias provides a positive or negative offset to the total input value.

Weights and biases are knobs that are useful for tuning models to data.

Although I'm describing the relationship between connected neurons in terms of first neuron's output becomes 2nd neuron's input,  we can view the relationship between weights and biases as an expression of a single input neuron and its output in terms of weights and biases.

A single input neuron's output = weight * input + bias

output = weight * input + bias
y      = m      * x     + b

Adjusting the weight affects the resulting slope of the line if we were to graph this single input neuron's output signal for various input values.

Adjusting the bias affects the resulting offset,  or point at which the resulting line intersects the y axis.  Increasing the bias impacts the output values by increasing the output values (or moving the line up).  Decreasing the bias impacts the output values by decreasing the output values (or moving the line down).

output = sum(inputs[i] * weights[i]) + bias

Activation functions are then applied to this value.  An activation function can be thought of in simple terms like a step function.

     1   x >  0
y =
     0   x <= 0

This step function is "activated" when x > 0,  but is not activated if x <= 0.

output = activation(output)

Although step functions can be used,  today's neural networks use Rectified Linear (ReLU) activation functions.
