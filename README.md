# GAN Image Classification Using DCT Maps

This project classifies images as either GAN-generated or real by leveraging Discrete Cosine Transform (DCT) maps. Based on findings from research, GAN-generated images do not exhibit distinct changes in the DCT maps at the bottom-right corner, while real images do. This repository implements two binary classification models: one inspired by a paper and another custom-built model, with the latter demonstrating superior performance.

## Project Structure

- **DCT Conversion**: The images are converted into DCT maps. The bottom-right corner of these maps provides crucial information for distinguishing between GAN-generated and real images.
- **Model Training**: Two models are used for classification:
  1. **Paper Model**: A model architecture mentioned in a research paper.
  2. **Custom Model**: A custom architecture designed and implemented in this project, which outperforms the paper's model.
- **Saliency Maps**: Saliency maps are generated to verify that the models focus on the bottom-right corner of the DCT maps during classification, in line with the hypothesis.

## Files

- `Classifier.ipynb`: The main notebook containing the code for loading images, generating DCT maps, training the models, and visualizing results through saliency maps.
- `dct_heatmap(image_path)`: A function that converts the input image into its corresponding DCT heatmap for analysis and visualization.
- `models/`: Directory containing the models used for classification.

## Dataset

I used this dataset from kaggle https://www.kaggle.com/datasets/muzzwalvanshikreddy/deepfake

## Usage

1. Prepare your dataset of GAN-generated and real images, and place them in the appropriate folders (e.g., `real_train/` and `fake_train/`).
2. Run the Jupyter notebook `Classifier.ipynb` to:
   - Generate DCT heatmaps of the images.
   - Train both models for binary classification.
   - Visualize saliency maps to verify model focus.

## Results

The custom model significantly outperforms the model mentioned in the paper and achieves an accuracy of 99.9% on the dataset. The saliency maps confirm that both models focus on the bottom-right corner of the DCT maps, where real images exhibit distinct changes, while GAN-generated images do not.

## References

- **Paper Model**: [Leveraging Frequency Analysis for Deep Fake Image Recognition](https://arxiv.org/abs/2003.08685)

## Saved model
You can directly download the trained model to use for your work
