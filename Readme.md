## Conclusion

This project demonstrates an end-to-end deep learning pipeline for land use and land cover classification using the EuroSAT RGB dataset derived from Sentinel-2 satellite imagery. The task was formulated as a multi-class image classification problem involving ten distinct land-cover categories spanning natural and urban environments.

A structured workflow was followed, beginning with exploratory data analysis to understand class balance and image characteristics. Data preprocessing and augmentation techniques were applied to improve model robustness and reduce overfitting. These included geometric transformations, color perturbations, and normalization using ImageNet statistics.

A ResNet18 architecture pretrained on ImageNet was adopted as the backbone model. Instead of training from scratch, a transfer learning strategy with partial fine-tuning was used: early convolutional layers were frozen to preserve generic visual features, while the final residual block and classification head were fine-tuned to adapt to satellite imagery. This approach provided an effective balance between computational efficiency and task-specific learning.

The model was trained using cross-entropy loss with label smoothing, differential learning rates for different network components, and a validation-based learning rate scheduler. Early stopping and model checkpointing ensured stable convergence and optimal generalization.

The final model achieved a **test accuracy of 95.37%**, indicating strong performance on unseen data. The confusion matrix analysis showed that most land-cover classes were reliably distinguished, with minor confusion occurring primarily between visually similar categories. These results highlight the effectiveness of transfer learning for remote sensing applications and demonstrate that high-quality land-cover classification can be achieved even with compact RGB imagery.

Overall, this project showcases a practical and scalable approach to satellite image classification and provides a solid foundation for future work, such as incorporating multispectral bands, experimenting with deeper architectures, or extending the model to real-world geospatial analysis tasks.
