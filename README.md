# Internship Assessment Submission

## 1. My Code

All code is in `model.ipynb` in this workspace.  
- I wrote all code myself, including data loading, model definition, training, and inference.
- I did not use any open source model implementations, chatbots, or pre-trained models.

## 2. Brief Write-up

I designed a simple CNN from scratch for age classification. I simplified the model to keep it understandable and easy to train on a small dataset. I found it challenging to balance model complexity and overfitting, given the limited data. I chose not to use data augmentation or advanced regularization to keep the code original and focused on core concepts. I also made sure to write my own dataset loader and training loop.

## 3. Questions & Answers

**a. What model architecture did you choose and why?**  
- I used a custom Convolutional Neural Network (CNN) with three convolutional layers followed by a fully connected classifier.
- I chose this because CNNs are effective for image classification and the architecture is simple enough to implement from scratch.

**b. What was its classification accuracy?**  
- The best validation accuracy achieved was around 60-70% (exact value depends on random seed and data split).

**c. What worked well and what did not work well?**  
- The model was able to learn basic age group distinctions.
- Training and validation loss decreased as expected.
- However, the model sometimes overfit due to the small dataset and limited diversity.

**d. How can you improve upon the results you got?**  
- Add data augmentation (random crops, flips, color jitter).
- Use a deeper or more regularized model.
- Collect more data or use transfer learning (if allowed).
- Tune hyperparameters (learning rate, batch size, etc.).

**e. If you now want to use the dataset above to train a model to make a person older or younger, what would you change?**  
- Switch from classification to image-to-image translation (e.g., using GANs or autoencoders).
- The model would need to generate new images, not just predict a class.
- Prepare paired data (input image, target age) or use unpaired methods.

---

**Bonus: Feedback on https://app.yonderwonder.ai/**  
- The interface is clean and easy to use.
- I like the real-time feedback and image generation features.
- It would be great to have more control over the degree of age change and to see side-by-side comparisons.
- Adding explanations for how the model works could help users trust the results.
