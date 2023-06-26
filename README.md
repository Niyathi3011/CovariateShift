# CovariateShift 

### Architecture and Hyper-parameter Choices:
- Model Architecture: The model consists of two linear layers (`self.fc1` and `self.fc2`) with ReLU activation in between.
- Batch Normalization: A batch normalization layer (`self.bn1`) is added after the first linear layer for improved training stability and generalization.
- Learning Rate (lr): 0.001
- Number of Epochs: 50
- Loss Function: CrossEntropyLoss
- Optimization Algorithm: Adam optimizer

### Visualization:
A scatter plot is shown with validation and test data, overlaying all ten classifier boundaries of individual models and the ensemble model.

### Performance Metrics:
| Metric              | Mean across Models | Ensemble Model |
|---------------------|-------------------|----------------|
| Train Accuracy      | 99.4%             | 99.3%          |
| Validation Accuracy | 99.4%             | 99.4%          |
| Test Accuracy       | 79.6%             | 81.6%          |
| Train ECE           | 0.022             | 0.020          |
| Validation ECE      | 0.024             | 0.022          |
| Test ECE            | 0.096             | 0.026          |

### Discussion on Covariate Shift:
Ensembling improves the results under covariate shift in the test domain, as shown by the table and visualization:
1. Improved Test Accuracy: The ensemble model achieves a higher test accuracy compared to the individual models, indicating its ability to handle covariate shift.
2. Reduced Test ECE: The ensemble model exhibits lower ECE, indicating better calibration and confidence estimation in the presence of covariate shift.

### Bayesian Sampling with SGLD
- SGLD (Stochastic Gradient Langevin Dynamics) is used instead of SGD, providing exploration of parameter space and preventing overfitting.
- The Ensemble Model with SGLD outperforms the Ensemble Model with SGD, with increased accuracy and improved calibration.
- Results are included in the attached table.

### Conclusions:
1. Ensembling improves performance and generalization compared to individual models.
2. The Ensemble Model with SGLD achieves higher test accuracy, but there is a tradeoff between accuracy and calibration performance.
3. SGLD optimization improves accuracy and generalization in ensemble modeling, leading to better predictive capabilities.

References:
- Links and resources used for debugging, information gathering, and research purposes are available in the report.
