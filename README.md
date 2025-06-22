# SmolNeRF
Small implementation of NeRF



The main component of our NeRF implementation are:
    - Volume of space that is voxelized
    - Camera position and orientation
    - Calculating the ray for each pixel
    - Calculating the color and opacity at a point on each ray
    - Neural network to predict the color and opacity
    - Rendering the image from a camera position
    - Loss function for rendered image and ground truth images
    - Dataset loader for training and testing 
    - Dataset of images and camera positions
    - Training/Testing loop
    - Evaluation code


Neural Network
- Inputs: 
    - Ray direction: theta, phi
    - Ray origin: x, y, z
- Outputs
    - Color: R, G, B
    - Opacity: simga

- Architecture
    - 8 fully connected layers with 256 hidden units each
    - ReLU activations
    - After 4 layers, the model concatenates the original 3D input (x,y,z) again (a skip connection), which helps preserve spatial info
    - Viewing Direction Branch: After computing 𝜎 from the spatial MLP, the MLP appends the viewing direction and continues with 1-2 more layers to predict RGB color


