# Computer Vision

## What is Computer Vision?

Computer Vision is a field of Artificial Intelligence that enables computers to interpret, analyze, and understand visual information from images and videos.

Rather than relying on manually written rules, modern computer vision systems use machine learning and deep learning models to recognize patterns within visual data.

Computer vision powers many real-world applications, including:

- Facial recognition
- Medical imaging
- Autonomous vehicles
- Security systems
- Manufacturing quality inspection
- Retail product recognition
- OCR (Optical Character Recognition)
- Satellite imagery

Deep learning, particularly Convolutional Neural Networks (CNNs), has significantly improved the accuracy of computer vision systems.

---

# Computer Vision vs Traditional Image Processing

Traditional image processing relies on manually designed rules.

Examples include:

- Edge detection
- Thresholding
- Image filtering

Computer vision uses machine learning to automatically learn useful image features.

Instead of programming exactly what a cat looks like, the model learns the characteristics of cats from thousands of training examples.

---

# Digital Images

A digital image is composed of thousands or millions of tiny picture elements called pixels.

Each pixel stores numerical information describing color or brightness.

Image size is typically described as:

```
Width × Height
```

Example:

```
224 × 224 pixels
```

means

- 224 pixels wide
- 224 pixels tall

---

# RGB Images

Color images are represented using three color channels.

- Red (R)
- Green (G)
- Blue (B)

Each channel typically ranges from:

```
0 – 255
```

Example:

```
RGB(255,0,0)
```

Produces pure red.

```
RGB(0,255,0)
```

Produces pure green.

```
RGB(0,0,255)
```

Produces pure blue.

Images used in deep learning are commonly normalized to values between 0 and 1 by dividing every pixel value by 255.

---

# Grayscale Images

Grayscale images contain only one intensity value per pixel.

Instead of three RGB channels, grayscale images use a single channel representing brightness.

Advantages include:

- Smaller memory usage
- Faster computation
- Simpler models

Examples include:

- X-rays
- Handwritten digit recognition
- Historical photographs

---

# Image Classification

Image classification predicts a single label for an entire image.

Examples:

- Cat
- Dog
- Car
- Airplane

The model determines which category best describes the entire image.

---

# Object Detection

Object detection identifies both:

- What objects appear
- Where they appear

Example:

A street image may contain:

- Cars
- Pedestrians
- Traffic lights

Each object receives both a class label and a bounding box.

---

# Image Segmentation

Image segmentation assigns a class label to every individual pixel.

Applications include:

- Medical imaging
- Autonomous driving
- Satellite imagery

Segmentation provides more detailed information than image classification.

---

# Convolutional Neural Networks (CNNs)

Convolutional Neural Networks are specialized neural networks designed for image data.

Unlike fully connected networks, CNNs preserve spatial relationships between pixels.

CNNs automatically learn increasingly complex image features such as:

- Edges
- Corners
- Textures
- Shapes
- Objects

CNNs are the foundation of most modern computer vision systems.

---

# Convolution Layers

A convolution layer applies small filters (kernels) across an image.

Rather than examining the entire image at once, each filter scans local regions.

Different filters learn different visual patterns.

Examples include:

- Vertical edges
- Horizontal edges
- Curves
- Texture

As more convolution layers are added, the network learns increasingly abstract features.

---

# Feature Maps

After a convolution operation, the resulting output is called a feature map.

Feature maps highlight areas where important visual patterns were detected.

Each convolution filter produces its own feature map.

---

# Activation Functions

CNNs commonly use the ReLU activation function.

Advantages include:

- Fast computation
- Efficient learning
- Reduced vanishing gradients

ReLU is applied after most convolution layers.

---

# Pooling Layers

Pooling reduces the size of feature maps while preserving important information.

Benefits include:

- Faster training
- Lower memory usage
- Reduced overfitting

---

## Max Pooling

Max Pooling selects the largest value within each pooling window.

It is the most commonly used pooling operation.

Advantages:

- Preserves the strongest visual features
- Reduces computational cost

---

## Average Pooling

Average Pooling computes the average value within each pooling window.

It produces smoother feature maps but is used less frequently than Max Pooling.

---

# Flatten Layer

The Flatten layer converts two-dimensional feature maps into a one-dimensional vector.

This allows the information to be passed into fully connected (Dense) layers for final prediction.

---

# Dense Layers

Dense layers combine learned image features to produce the final prediction.

The final Dense layer depends on the prediction task.

Examples:

Regression:

```
Dense(1)
```

Binary Classification:

```
Dense(1, activation="sigmoid")
```

Multi-class Classification:

```
Dense(number_of_classes, activation="softmax")
```

---

# Data Augmentation

Deep learning models often require thousands of images.

Data augmentation artificially increases dataset size by creating modified copies of existing images.

Common augmentation techniques include:

- Horizontal flip
- Vertical flip
- Rotation
- Zoom
- Brightness adjustment
- Width shift
- Height shift

Benefits include:

- Reduced overfitting
- Improved generalization
- Better robustness

---

# Transfer Learning

Training deep neural networks from scratch requires enormous datasets and computational resources.

Transfer learning reuses models already trained on millions of images.

Popular pretrained models include:

- ResNet50
- VGG16
- EfficientNet
- MobileNet

Advantages:

- Less labeled data required
- Faster training
- Higher accuracy
- Lower computational cost

Transfer learning is commonly used in real-world computer vision projects.

---

# ResNet

Residual Networks (ResNet) introduced residual connections that allow very deep neural networks to train effectively.

Benefits include:

- Improved accuracy
- Reduced vanishing gradients
- Ability to train deeper networks

ResNet50 is one of the most widely used pretrained computer vision models.

---

# Common Computer Vision Workflow

A typical computer vision project follows these steps:

1. Collect image data.
2. Label the images.
3. Split into training, validation, and test sets.
4. Normalize image pixel values.
5. Apply data augmentation.
6. Load images using data generators.
7. Train a CNN or pretrained model.
8. Evaluate model performance.
9. Deploy the trained model.

---

# Common Deep Learning Libraries

Popular computer vision libraries include:

- TensorFlow
- Keras
- PyTorch
- OpenCV
- Pillow (PIL)

Common Keras layers include:

- Conv2D
- MaxPooling2D
- AveragePooling2D
- Flatten
- Dense
- GlobalAveragePooling2D
- Dropout

---

# Computer Vision Project Example

A common real-world project is age estimation from facial images.

Typical workflow:

- Load facial images.
- Resize images to a consistent size.
- Normalize pixel values.
- Apply data augmentation.
- Use Transfer Learning with ResNet50.
- Fine-tune the model.
- Predict a person's age.

Age estimation demonstrates how pretrained computer vision models can solve practical regression problems.

---

# Common Interview Questions

Interviewers frequently ask:

- What is Computer Vision?
- Why are CNNs better than fully connected neural networks for images?
- What does a convolution layer do?
- Why use Max Pooling?
- What is Transfer Learning?
- Why is ResNet popular?
- What is data augmentation?
- What is the difference between image classification and object detection?
- Why normalize pixel values?
- Why use pretrained models?

Strong interview answers explain the intuition behind these concepts instead of memorizing definitions.

---

# Key Takeaways

- Computer Vision enables computers to interpret images and videos.
- CNNs automatically learn visual features such as edges, textures, and shapes.
- Pooling reduces computational complexity while preserving important information.
- Data augmentation improves generalization by creating additional training examples.
- Transfer Learning reuses pretrained models to improve performance and reduce training time.
- ResNet50 is one of the most widely used pretrained computer vision architectures.
- Modern computer vision systems power applications ranging from medical imaging to autonomous vehicles.