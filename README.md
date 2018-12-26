# CarND_Project12_SementicSegmentation

Solution for Udacity Self driving car Nano degree twelveth project: Sementic Segmentation Project.

---

## Objective

Train a Neural Network to label all pixels in an image belonging to a lane.

---

### Reflection

This project present opportunity to understand how sementic segemnetation of an image by altering the architecture of traditional CNNs, it also provide conepts on optimization of Neural network for inference and deployment purposes.

---

### Background

Up to this project we only worked with bounding box neural networks, finding an object in an image and drawing a box around it. This maybe useful for some applications as object detection, but it doesn't provide a complete understanding about the vehicle surrondings, making our perception incomplete. Sementic segmentation address this problem by preserving spatial information from the orignial image allowing labeling each inidividial pixel in the image to a class, this allows for a much more complete preception and allow for more complex applications as free spcae detection required for complex maneuvers.

---

### Network Architecture

In this project we were following this paper: https://people.eecs.berkeley.edu/~jonlong/long_shelhamer_fcn.pdf

The neural network consists of two parts:
  - Encoder
      A pre-trained VGG16 network is used as the encoder respnosible for the actual classification of the object.
      The final convolution layer is replaced by a 1*1 convlutiuon with a Kenerl count of 2 (Lane or NoLane).
  - Decoder
      The output of 1*1 convolutions is upsampled till the original image size, Layer 3 and 4 of the encoder is scaled and bypassed to the final layers as well allowing integration of the spatial information with the actual classification done by the encoder so that each pixel can be classified to a class.

---

### Output

The output of network is stored under runs/1545705966.127747, below are some examples:

[//]: # (Image References)

[Ex1]: ./runs/1545705966.127747/um_000006.png
[Ex2]: ./runs/1545705966.127747/um_000052.png
[Ex3]: ./runs/1545705966.127747/umm_000082.png
[Ex4]: ./runs/1545705966.127747/uu_000096.png

![Ex1][Ex1]

![Ex2][Ex2]

![Ex3][Ex3]

![Ex4][Ex4]
