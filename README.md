# AI-Assisted Liver Tumour Segmentation and Ablation Planning

## Project Overview

This project explores the application of deep learning to image-guided liver tumour interventions. A 2D U-Net model was developed to segment liver tumours from CT images, followed by a simulation of ablation margins to evaluate tumour coverage and the extent of surrounding tissue involvement.

## Dataset

- **Dataset:** Liver and Liver Tumor Segmentation (LiTS)
- **Source:** [Kaggle](https://www.kaggle.com/datasets/andrewmvd/lits-png)
- **Images:** 58,638 CT slices
- **Resolution:** 256 × 256 pixels
- **Annotations:** Liver and tumour segmentation masks

## Methodology

The project involved:

1. **Data Preprocessing:** Loading and preparing CT images and segmentation masks.
2. **Tumour Segmentation:** Training a 2D U-Net model using PyTorch.
3. **Model Evaluation:** Assessing segmentation performance using Dice Score and Intersection over Union (IoU).
4. **Ablation Simulation:** Generating simulated ablation margins around predicted tumour boundaries.
5. **Coverage Analysis:** Evaluating tumour coverage and surrounding tissue involvement at different simulated margins.
6. **Sensitivity Analysis:** Investigating how variations in segmentation boundaries influence simulated ablation coverage.

## Results

| Evaluation Metric | Result |
|-------------------|--------|
| Mean Dice Score | 0.4341 |
| Mean IoU | 0.4135 |
| Tumour-positive Slice Dice | 0.1886 |
| Tumour Coverage at 0-pixel Margin | 23.4% |
| Tumour Coverage at 10-pixel Margin | 41.0% |

Increasing the simulated ablation margin improved tumour coverage but also increased the proportion of surrounding tissue included in the simulated treatment region.

## Technologies Used

- Python
- PyTorch
- U-Net
- NumPy
- Pandas
- SciPy
- Scikit-learn
- Matplotlib
- Google Colab

## Limitations

This was a computational feasibility study based on 2D CT images. The simulated ablation margins were measured in pixels rather than millimetres, and no actual treatment outcomes were available.

The model also showed limited segmentation accuracy, particularly on tumour-containing slices. 

## Future Work

- Improve tumour segmentation accuracy.
- Extend the framework to 3D CT imaging.
- Incorporate vascular and other critical anatomical structures.
- Develop more realistic ablation planning simulations.
- Evaluate the framework using clinical intervention data.

## Acknowledgements

The dataset used in this project was derived from the Liver Tumor Segmentation Benchmark (LiTS), developed for liver and tumour segmentation research.
