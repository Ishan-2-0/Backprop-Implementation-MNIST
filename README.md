MNIST Digit Classifier: Manual Backprop vs PyTorch

This project implements a simple 2-layer neural network for the MNIST digit classification task, comparing a manual backpropagation implementation with PyTorch’s built in tools. The goal is to learn how backpropagation works from scratch and validate it against PyTorch

Dataset
Source: MNIST dataset via sklearn.datasets.fetch_openml
Features: 784 pixel values (28×28 grayscale images)
Target: Digit class (0–9)
Approach
Manual Implementation
Neural network with 1 hidden layer (128 neurons) and output layer (10 classes)
Activations: ReLU for hidden, Softmax for output
Cross-entropy loss used for training
Manual forward and backward propagation using NumPyGradient descent optimizer implemented from scratch
Metrics: Accuracy on test set

PyTorch Implementation
Same network architecture: 784 → 128 → 10
Uses torch.nn.Linear, torch.relu, torch.nn.CrossEntropyLoss
Optimizer: torch.optim.SGD
Metrics: Accuracy on test set
Key Insights
Manual backpropagation correctly computes gradients and achieves similar accuracy to PyTorch
PyTorch’s .backward() automatically computes gradients using the chain rule
Training loss curves show similar trends for both implementations
Randomness in initialization affects predictions for individual digits, but overall performance is consistent

Results
All plots are stored in the Results/ folder:
loss_comparison.png Training loss comparison between manual and PyTorch models
sample_predictions.png Random MNIST images showing OG label, Manual prediction, and PyTorch prediction

Folder Structure
Backprop-Implementation-MNIST/
├── Notebook.ipynb
├── Results/
│   ├── loss_comparison.png
│   ├── sample_predictions.png
└── README.md
