![[Pasted image 20231129232824.png]]

Imagine you're looking at a picture, trying to recognize what's in it. Your brain doesn't just see a bunch of pixels; it recognizes patterns, shapes, edges, and textures. This is similar to how CNNs process images, but first, let's contrast this with how traditional Artificial Neural Networks (ANNs) work.

### Traditional ANNs and the Issue of Flattening

In ANNs, the input data is typically "flattened." Picture a 2D image - a grid of pixels, each with a value. Flattening this image is like unweaving a fabric into a single, long thread. This process, however, loses the spatial structure of the image - the 'where' of each pixel in relation to others.

![[pixels-to-neurons.gif]]

#### Visualization: 
- Imagine a grid representing an image.
- Then, visualize this grid being stretched out into a long, single line of pixels.

### Convolution: Preserving Spatial Relationships

CNNs keep the image in its 2D form. They use a process called convolution, which is like having a small window (a filter) glide over the image, focusing on one small area at a time.

![[CNN-filter-animation-1.gif]]
#### How it Works:
- The filter (a small matrix) moves across the image.
- At each step, it mathematically combines the values of the pixels under it with its own weights, creating a new matrix - the feature map. ( matrix multiplication )
- This process highlights features like edges, textures, etc.

![[Pasted image 20231129234638.png]]
_highlighting different features using different filters_

### Multiple Convolution Layers in CNNs

- **Building Complexity**: In a CNN, using multiple convolution layers is the same as constructing a hierarchy of feature detection. Each layer builds upon the previous one, extracting increasingly complex features from the input image.
- **Visualizing Layer Progression**: Picture an image moving through layers of a CNN. The first layer acts like a set of eyes, each looking for simple patterns, such as edges or basic textures. As the image progresses through subsequent layers, the features detected become more complex. It's like starting from a sketch and gradually filling in the details.
- ![[Pasted image 20231129234317.png]]
#### Example with OCR:
- Think about recognizing handwritten digits.
- Early layers might detect edges and simple shapes.
- Deeper layers combine these into more complex patterns (like parts of numbers).

### ReLU (Rectified Linear Unit): Sharpening the Image

ReLU is an activation function that adds non-linearity. It's like an artist enhancing contrast in a picture - making bright areas brighter and dark areas darker, thus making **features more distinct**.

#### Visualization:
- Imagine a feature map as a grayscale image.
- ReLU then turns all negative values to zero, effectively 'sharpening' the image.

### Pooling: Adding Flexibility

Pooling reduces the size of feature maps but keeps the essential information. Max pooling, for example, takes the largest value in a small region of the feature map.

![[Pasted image 20231129235046.png]]
#### Why It Matters:
- It makes the network less sensitive to small variations and distortions in the image.
- Imagine a slightly tilted digit; max pooling still captures the essential features.

### Flattening: Preparing for Classification

After convolution, ReLU, and pooling, the feature maps are flattened into a long vector. This step prepares the data for the final phase - classification.

#### Visualization:
- Picture taking a multi-layered, 2D feature map.
- Then, unroll it into a long, 1D vector.

### Full Connection: The Final Step

This flattened vector feeds into a traditional ANN. Here, the network combines features in various ways to make a final decision - like recognizing the digit in an image.

#### How it Works:
- The ANN part of a CNN works like any other ANN.
- It uses the features extracted by previous layers to classify the image.

---

In summary, CNNs maintain the spatial relationships within images, detect features at various levels, and are robust to minor variations, making them highly effective for tasks like image recognition. This method of processing is much closer to how our brains interpret visual information, making CNN