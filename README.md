# Digital Watermarking

## Overview
This project performs a series of image processing steps using OpenCV to embed a watermark into a carrier image. The process involves accessing images, resizing them, splitting image channels, applying the Catalan transform, training an MLP regressor, and using Non-negative Matrix Factorization (NMF) for feature extraction and watermark embedding.

## Dataset
- **Carrier Image**: The base image in which the watermark is embedded.
- **Watermarked Image**: The image to be embedded as a watermark.

## Preprocessing and Feature Extraction
1. **Mount Google Drive**: Access carrier and watermarked images stored in Google Drive.
2. **Load and Display Images**: Load and display the carrier and watermarked images.
3. **Resize Images**: Resize images to 256x256 pixels.
4. **Split Image Channels**: Split the carrier image into its red, green, and blue channels.
5. **Process Green Channel**: Extract 16x16 blocks from the green channel and apply the Catalan transform to calculate coefficients.
6. **Train MLP Regressor**: Train a Multi-Layer Perceptron (MLP) regressor model using the Catalan coefficients.
   - **Model Structure**:
     - Hidden Layer Sizes: 100 neurons
     - Activation Function: ReLU
     - Solver: Adam
     - Maximum Iterations: 1000
7. **Extract Features**: Extract features from the trained MLP regressor.
8. **Apply NMF**: Use Non-negative Matrix Factorization (NMF) to find the best feature with the lowest reconstruction error.
9. **Embed Watermark**: Embed the watermarked image into the green channel of the carrier image using the best feature.
10. **Combine Channels**: Combine the processed green channel with the original red and blue channels to create a merged image.
11. **Display Merged Image**: Display the final watermarked image.

## Results
The final output is a watermarked image where the watermark is embedded into the green channel of the carrier image.

### Visualizations
- **Carrier Image**
  - ![Carrier Image](https://i.ibb.co/M6ywhNW/vi.png)

- **Watermarked Image**
 - ![Watermarked Image](https://i.ibb.co/jwn3PhN/vj.png)

- **Final Merged Image**
 - ![Final Merged Image](https://i.ibb.co/23YxHpp/vk.png)
