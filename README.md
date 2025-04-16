# Multi-Class SVM Optimization using Metaheuristics

This project applies Support Vector Machines (SVM) to a multi-class classification problem using a UCI dataset. The focus is on tuning the nu parameter and kernel type of NuSVC using metaheuristic optimization strategies over multiple random samples.

--

## Methodology

1. **Dataset:** Multi-class dataset from the UCI Machine Learning Repository.
2. **Model:** NuSVC from Scikit-learn, a variant of SVM using the nu parameter instead of C.
3. **Optimization Strategy:**
   - 10 random samples of the dataset were generated.
   - Each sample underwent 100 iterations of metaheuristic optimization.
   - Parameters optimized:  
     - Kernel: 'linear', 'poly', 'rbf', 'sigmoid'  
     - Nu: A float between (0,1)  
     - Epsilon: Tuned (though not directly relevant to NuSVC, assumed part of extended tuning)
4. **Evaluation Metric:** Accuracy on the test set for each sample.

---

## Result Table (Best of 10 Samples)

| Sample | Best Accuracy (%) | Best Kernel | Nu   | Epsilon |
|--------|-------------------|-------------|------|---------|
| S1     | 98.65             | rbf         | 0.06 | 0.242   |
| S2     | 99.42             | rbf         | 0.03 | 0.455   |
| S3     | 99.61             | rbf         | 0.07 | 0.228   |
| S4     | 99.23             | rbf         | 0.07 | 0.963   |
| S5     | 99.04             | rbf         | 0.09 | 0.942   |
| S6     | 98.65             | rbf         | 0.02 | 0.291   |
| S7     | 99.04             | rbf         | 0.06 | 0.026   |
| S8     | 99.42             | rbf         | 0.02 | 0.039   |
| S9     | 99.42             | rbf         | 0.01 | 0.651   |
| S10    | 99.81             | rbf         | 0.02 | 0.959   |

> All samples converged to the `rbf` kernel as the optimal choice.

---

## Result Graph

- The model rapidly improved its accuracy in the first 25 iterations.
- Accuracy stabilized at 100%, indicating early convergence of the optimizer.

---

## Requirements

- Python 3.7+
- scikit-learn
- matplotlib
- numpy
- pandas

---

## Conclusion

- Metaheuristic optimization is effective in quickly finding high-accuracy SVM configurations.
- The rbf kernel consistently performed best across all samples.
- NuSVC achieved up to **99.81%** accuracy using optimal hyperparameter settings.
