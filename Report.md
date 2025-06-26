# Internship Assessment Submission

## 1. My Code

All code is in `model.ipynb` in this workspace.  
- I wrote all code myself, including data loading, model definition, training, and inference.
- I used a pre-trained ResNet18 backbone for better feature extraction but implemented the full training pipeline and custom regression head myself.
- The model architecture and training approach are my own implementation for age regression.

## 2. Brief Write-up

I designed an age regression model using a ResNet18 backbone with a custom regression head. After initially trying a classification approach (which achieved only ~14% accuracy), I switched to regression since age is a continuous variable rather than discrete classes. This change improved performance and accuracy of the model. The model uses L1 loss (Mean Absolute Error) for training and it showed excellent convergence with both training and validation losses decreasing smoothly and a stable learning without overfitting(overfitting is solved in here).

## 3. Questions & Answers

**a. What model architecture did you choose and why?**  
- I used a ResNet18 backbone with a custom regression head consisting of dropout layers, fully connected layers with ReLU activations, and a single output neuron cause we are predicting age only right.

- I chose ResNet18 because it provides excellent feature extraction capabilities for face analysis while being computationally efficient.

- The regression approach is more suitable than classification since age is a continuous variable, allowing the model to learn ordinal relationships between ages.

**b. What was its classification accuracy?**  
- **Mean Absolute Error (MAE)**: ~6 years on validation set
- **Accuracy within ±5 years**: 60%  
- **Accuracy within ±10 years**: 85% 
- **Training Loss**: Reduced from 50 to 6 (88% reduction)
- **Validation Loss**: Reduced from 48 to 6 (87% reduction)


**c. What worked well and what did not work well?**  
**What worked well:**
- Switching from classification to regression dramatically improved performance (14% → 55-60%)
- Pre-trained ResNet18 backbone provided excellent feature extraction capabilities
- Data augmentation (random crops, flips, color jitter, rotation) improved generalization
- L1 loss function proved effective for age regression tasks
- Training showed excellent convergence with smooth loss reduction

**What could be improved:**
- Accuracy could potentially reach 70-80% with more data or advanced techniques
- Limited dataset size constrains the upper bound of performance

**d. How can you improve upon the results you got?**  
- **Larger dataset**: Collect more diverse age samples, especially for underrepresented age groups
- **Advanced architectures**: Try EfficientNet, Vision Transformers model might give accurate results than expected.

**e. If you now want to use the dataset above to train a model to make a person older or younger, what would you change?**  
- **Switch to Generative Models**: Use Generative Adversarial Networks (GANs) or Diffusion Models instead of regression
- **Architecture Change**: Implement conditional GANs (cGANs) or StyleGAN with age conditioning
- **Loss Functions**: Use adversarial loss combined with perceptual losses and identity preservation losses
- **Data Structure**: Prepare data for image-to-image translation with age conditioning vectors
- **Training Strategy**: Use progressive training, starting with low-resolution images and gradually increasing resolution
- **Evaluation Metrics**: Focus on image quality (FID, LPIPS) and age accuracy rather than just regression metrics
- **Post-processing**: Add face blending and smoothing techniques to ensure natural-looking results

---
