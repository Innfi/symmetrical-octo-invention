>[!tip]
>compensating [[Vanishing Gradient]]


```
x = ... // input tensor
residual = x
x = block(x)
x = add([x, residual]) // add original input to the output -> terminal output always preserve whold data of original input
```