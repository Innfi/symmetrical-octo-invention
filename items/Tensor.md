#AI 

---
>[!note]
>Scalar
>Vector
>Matrix


## Attributes
---
dtype
ndim
shaper

## Operations
---
[[ReLU]]
[[Tensor-Broadcasting]]
[[Tensor-Product]]
[[Tensor-Reshaping]]

translation
rotation
linear transform
affine transform
transposition

---

training loop:
* extract a batch for a training sample X with a corresponing target y_true 
* execute a model using x (forward pass), then calculate a estimation of y_pred
* calculate the loss of the model for this batch by measuing the difference between y_pred and y_true 
* update every weights of the model to diminish the load of the batch to some degree 
	* the most difficult part
	* connects to [[Gradient Descent]]


