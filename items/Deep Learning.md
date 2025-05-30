
>[!note]
>Artificial Intelligence > Machine Learning > Deep Learning
>Machine Learning: finding viable representation of input data, helped by feedback signal, within the predefined space of possibility
>-> infer pattern based on data and solution

>[!tip] 
>Layered Representations Learning
>Hierarchical Representations Learning

## Prerequisites
- [[Deep Learning-Prerequisites]]
### Model: Neural Network
- [[Neural Network]]
## Training Loop
* extract a batch for a training sample X with a corresponing target y_true 
* execute a model using x (forward pass), then calculate a estimation of y_pred
* calculate the loss of the model for this batch by measuing the difference between y_pred and y_true 
* update every weights of the model to diminish the load of the batch to some degree 
	* the most difficult part
	* connects to [[Gradient Descent]]
## Tools
- [[Tensorflow]]
## Workflow
- [[Deep Learning-Workflow]]


---
## Terms
- [[Computation Graph]]
- [[Text Processing]]
## Questions
- from optimization to generalization
	- dataset curation
	- feature engineering
	- early stopping
	- [[Regularization]]
- thin line between underfitting and overfitting
## Evaluation
- [[Holdout Validation]]
- [[K-Fold Cross Validation]]
