# PINN MODEL

# Model Architecture
1 Input Layer: The network takes two inputs time (t) and space (x).
2 Hidden Layers: There are 8 hidden layers, each with 20 neurons. The
activation function used is the hyperbolic tangent (Tanh).
3 Output Layer: The output layer has one neuron which provides the
solution u(t, x)

# Initialization and Setup
1 Device Configuration: The script is set to use a GPU if available;
otherwise, it defaults to the CPU.
2 Model Initialization: The PINN model is instantiated and transferred
to the configured device.
3 Optimizer: The Adam optimizer is used for training with a learning
rate of 0.001.

# Training Data and Optimization
# Data Preparation
1 Collocation Points: These are generated using Latin Hypercube
Sampling to ensure uniform coverage of the input domain. The
collocation points are used to enforce the PDE throughout the
domain.

# Loss Function
1 Residual Loss: Ensures that the model’s predictions satisfy the
Burgers’ equation at the collocation points.
2 Initial Condition Loss: Ensures that the model’s predictions match the
initial condition.
3 Boundary Condition Loss: Ensures that the model’s predictions satisfy
the boundary conditions.

# Training Loop
1 The training loop iteratively updates the model’s parameters to
minimize the total loss.
2 The model is trained for 5000 epochs, and the loss is printed every
100 epochs.

 # Visualization
1 To evaluate the model’s performance, the predicted solution is
compared with the actual solution at different time instances.



