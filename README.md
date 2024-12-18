# Multi-Class Texture Analysis in Colorectal Cancer Histology

## Objective
The goal of this project is to develop a robust machine learning model for the classification of colorectal tissue samples based on histological images. Using various dimensionality reduction techniques and classifiers, the objective is to accurately classify tissue types for potential diagnostic and research applications.

---

## Dataset

- **Source**: [Nature Scientific Reports](https://www.nature.com/articles/srep27988) and [Zenodo Repository](https://zenodo.org/record/53169#.Yo3WLS8RqUn)
- **Description**:
  - A dataset of 5,000 histological images (150x150 RGB pixels).
  - Eight labeled classes:
    - Tumor epithelium
    - Simple stroma
    - Complex stroma
    - Immune cells
    - Debris
    - Normal mucosal glands
    - Adipose tissue
    - Background (no tissue).
  - **Split:**
    - Training Set: 80% (4,000 images)
    - Test Set: 20% (1,000 images).

---

## Preprocessing Steps

1. Loaded dataset using the `tensorflow_datasets` library.
2. Verified and reshaped data dimensions.
3. Normalized pixel values to a range of [0.0, 1.0].
4. Defined and encoded class labels.

---

## Experiments

Nine experiments were conducted using combinations of dimensionality reduction techniques and classifiers:

### Experiment Combinations

1. **Downsampling to 32x32 pixels + SVM**
   - **Training Accuracy**: 82.88%
   - **Testing Accuracy**: 68.80%

2. **Downsampling to 32x32 pixels + Softmax**
   - **Training Accuracy**: 79.98%
   - **Testing Accuracy**: 48.30% (Overfitting observed)

3. **Downsampling to 32x32 pixels + Neural Network**
   - **Training Accuracy**: 83.38%
   - **Testing Accuracy**: 56.30% (Overfitting observed)

4. **PCA to 256 dimensions + SVM**
   - **Training Accuracy**: 85.00%
   - **Testing Accuracy**: 63.50%

5. **PCA to 256 dimensions + Softmax**
   - **Training Accuracy**: 76.17%
   - **Testing Accuracy**: 55.81%

6. **PCA to 256 dimensions + Neural Network**
   - **Training Accuracy**: 99.83%
   - **Testing Accuracy**: 61.90% (Overfitting observed)

7. **VGG16 backbone + SVM**
   - **Training Accuracy**: 98.35%
   - **Testing Accuracy**: 87.40%

8. **VGG16 backbone + Softmax**
   - **Training Accuracy**: 99.85%
   - **Testing Accuracy**: 86.50%

9. **VGG16 backbone + Neural Network**
   - **Training Accuracy**: 99.90%
   - **Testing Accuracy**: 87.10% (Best overall performance).
---

## Results Summary

![image](https://github.com/user-attachments/assets/6d1b1a3d-b13c-4977-b35a-9705405771d5)

- The best-performing model utilized VGG16 for dimensionality reduction and a Neural Network classifier, achieving a **training accuracy of 99.90%** and a **testing accuracy of 87.10%**.
  ![image](https://github.com/user-attachments/assets/1a8c15ed-c87b-44de-9951-806665d46dea)

- Overfitting was a recurring challenge in some combinations, particularly with PCA and Neural Networks.

---

## Recommendations for Future Work

1. **Data Augmentation**: Enhance training data diversity with techniques like rotation, scaling, and flipping.
2. **Hyperparameter Optimization**: Fine-tune learning rates, batch sizes, and regularization terms.
3. **Experimentation**: Explore additional combinations of dimensionality reduction methods and classifiers.
4. **Ensemble Learning**: Combine models to leverage collective strengths for improved robustness and accuracy.

---

## Visualizations and Analysis

- Confusion matrices and accuracy plots were used to evaluate model performance.
- t-SNE visualizations provided insights into feature separability post-reduction.

