#Layer 

>[!tip]
>combine the output of the previous calculation as a part of the input

```
# pseudocode of simpleRNN

state_t = 0
for input_t in input_sequence:
  output_t = activation(dot(W, input_t) + dot(U, state_t) + b)
  state_t = output_t
```
