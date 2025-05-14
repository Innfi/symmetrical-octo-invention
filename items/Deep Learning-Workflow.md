>[!note]
>technically it's a machine learning workflow but doesn't make a difference for me (so far)

## 1. Workload Definition
---
### Problem definition
- type of input data
- specification for the estimate
- category of the problem
	- binary classification?
	- multiclass classification?
	- scalar regression?
	- vector regression?
### Data Preparation
- data annotation
- (fits [[Deep Learning-Prerequisites]] ?)
- [[Data Augmentation]]
### Comprehending Data
- characteristics?
### Decide Successful Metrics


## 2. Model Development
---
### Data Preprocessing
- vectorization
- normalization 
- handling vacant values
### Decide Validation Method
- [[Holdout Validation]]
- [[K-Fold Cross Validation]]
- Repeated K-Fold Cross Validation
### Exceling
- (todo)
### Scaling Model: for overfitting
- add layer
- increase the size of layer
- training for a longer epochs
- metrics: training accuracy, validation accuracy, training loss, validation loss
### Regularization / Hyperparameter Tuning
- keras tuner?

## 3. Model Deployment
---
(todo)



---
## Terms
- concept drift
- smapling bias
