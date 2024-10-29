# Image-Edge-Detection-and-Orientation
This assignment focuses on applying Difference of Gaussians (DoG) and Gabor filters to detect edges in synthetic images, specifically a circle and a square. Additionally, the Winner-Take-All (WTA) strategy is applied to enhance the edge detection results.
<img width="692" alt="image" src="https://github.com/user-attachments/assets/4acda989-72b2-4a8b-9493-2401ec432e7c">
1. **Trying different values of sigma while applying the DOG on Circle and Square**

The DoG filter was applied to both the circle and square images using the sigma pairs mentioned above. The results were visualized to observe the effect of different sigma values on edge detection.

**Observations**:

- Smaller sigma values captured finer details, while larger sigma values highlighted broader edges.
- The edges of the circle and square became more prominent as the difference between the sigma values increased.
<img width="427" alt="image" src="https://github.com/user-attachments/assets/ac2596ba-63b8-46d1-929d-b5e864b1be9d">

2. **Checking different filter sizes and lambda values for Gabor filters**
  Gabor filters are widely used for edge detection, texture analysis, and feature extraction. They are particularly effective in detecting edges with specific orientations. The Gabor filter is a linear filter whose impulse response is defined by a harmonic function multiplied by a Gaussian function.

### **Parameter Selection**

The Gabor filter was applied using the following parameters:

- **Kernel Size (ksize)**: [15, 21, 31]
- **Wavelength (lambda)**: [5.0, 10.0, 15.0]
- **Orientation (theta)**: [0°, 45°, 90°, 135°]

### **Application and Results**

The Gabor filters were applied to the DoG-filtered images for the circle and square. The edge images for different orientations were obtained, and the results were visualized.

**Observations**:

- The Gabor filter effectively detected edges at different orientations.
- The edge strength varied with changes in the kernel size and wavelength, indicating the sensitivity of the filter to these parameters.
- The circle image showed more consistent edges across orientations, while the square image had stronger edges at specific orientations (0° and 90°).
<img width="849" alt="image" src="https://github.com/user-attachments/assets/b9123bfd-37ec-40cb-9c77-ca1765335888">

## Testing in the original Image
<img width="573" alt="image" src="https://github.com/user-attachments/assets/6f84aa1b-d433-4eb9-9c00-d69bc5d0e19e">
<img width="855" alt="image" src="https://github.com/user-attachments/assets/bafa2fe9-bbcf-4212-9198-10f3141b4f55">
<img width="847" alt="image" src="https://github.com/user-attachments/assets/dcca288e-0320-450d-8c0e-60ec37f30b57">


The Winner-Take-All (WTA) strategy was used to select the strongest edge at each pixel location from the Gabor-filtered images. The strongest edge was then normalized by the average edge strength to enhance the edge detection results.

### **Results**

The WTA and normalization were applied to the Gabor-filtered images for both the circle and square. A threshold was used to remove spurious edges.

**Observations**:

- The WTA strategy effectively isolated the strongest edges, reducing noise and improving the clarity of the edge images.
- Normalization further enhanced the contrast between the edges and the background.
- The final edge images highlighted the main contours of the circle and square with reduced background noise.

# Experimentation and Parameter Tuning
### **Sigma Values in DoG**

- **Lower Sigma Pairs**: Captured finer details and noise, useful for detecting small or intricate edges.
- **Higher Sigma Pairs**: Smoothed out noise, focusing on larger, more prominent edges.

### **Kernel Size in Gabor Filters**

- **Smaller Kernel Sizes**: Detected finer edges but were more sensitive to noise.
- **Larger Kernel Sizes**: Provided more robust edge detection but with less sensitivity to small details.

### **Wavelength in Gabor Filters**

- **Shorter Wavelengths**: Detected edges with higher frequency (more detail).
- **Longer Wavelengths**: Detected broader edges, capturing less detail.

### **Threshold in WTA**

- **Lower Threshold**: Preserved more edges but included some spurious edges.
- **Higher Threshold**: Reduced noise but could potentially miss weaker edges.

### **Optimal Parameter Combinations**

- For the circle, a lower sigma pair combined with a medium kernel size and wavelength provided the best results.
- For the square, a higher sigma pair with a larger kernel size and wavelength captured the edges more effectively.

<img width="889" alt="image" src="https://github.com/user-attachments/assets/74ce7853-8daf-43c0-8c6a-7fedd6f85f37">


