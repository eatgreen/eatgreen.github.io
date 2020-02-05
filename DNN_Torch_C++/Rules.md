# Rules
## Never use tensor from at:: as they are tensors only, use tensor from torch::, as they are variables.
## element-wise access. Use *accessor*.
## Factory function: create a new tensor.
torch::Tensor tensor=torch::ones({3,4,5})
tensor.sizes()
tensor.size(i)(equivalent tensor.sizes()[I])
## TensorOptions

