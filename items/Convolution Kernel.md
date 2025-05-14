>[!tip]
>Small matrix of learnable weights, also called a filter

- Typically much smaller than the input (for example, 3x3 or 5x5 pixels for images), but it always extends through the full depth of the input volume
- During the forward pass, the kernel slides (or convolves) across the spatial dimensions (width and height) of the input, computing dot products between the kernel values and the input region it covers at each position
- The result is a 2D activation map (feature map) that indicates where certain features (like edges, textures, or more complex patterns) are detected in the input
