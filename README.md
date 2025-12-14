This repository documents a systematic exploration of classical machine learning, quantum machine learning, and hybrid modeling strategies for credit card fraud detection under extreme class imbalance and nonlinear data characteristics. The project begins with strong classical baselines and progressively investigates the feasibility and limitations of quantum-enhanced approaches in a real-world anomaly detection context. Initial experiments employ Logistic Regression with SMOTE-balanced data, achieving consistently high recall but extremely low precision, highlighting the practical limitations of recall-driven models in fraud detection. A Random Forest classifier is subsequently introduced, demonstrating robust generalization, high precision, and stable recall across training and testing splits, establishing it as the most reliable standalone model in this study.
Motivated by recent advances in Quantum Machine Learning (QML), a Variational Quantum Classifier (VQC) is implemented using PCA-compressed and angle-encoded features. Despite careful subset selection and threshold tuning, the VQC exhibits limited expressive capacity and inferior F1-scores relative to classical models, particularly on unseen data. This phase exposes practical challenges in current QML workflows, including evolving Qiskit APIs, deprecated backends, optimizer migration, and computational constraints that restrict circuit depth and dataset scale. To bridge classical robustness with quantum experimentation, a hybrid Random Forest + VQC framework is developed, where the classical model handles high-confidence predictions and the quantum classifier refines decisions in uncertain regions. While this hybrid strategy preserves Random Forest performance and yields modest improvements in selected cases, the overall gains remain incremental, reinforcing the dominance of classical models under current hardware and software constraints.
📌 Project Overview
Detect highly imbalanced credit card fraud transactions
Compare classical ML, quantum ML, and hybrid ensembles
Evaluate real-world feasibility of Variational Quantum Classifiers (VQC)

🧠 Modeling Approaches

1️⃣ Classical Models
Logistic Regression (SMOTE-balanced)
Random Forest (baseline benchmark)
2️⃣ Unsupervised Models
Autoencoder (AE)
Isolation Forest (IF)
3️⃣ Quantum Models
Variational Quantum Classifier (Qiskit-based)
PCA + angle encoding
Subset-based quantum training
4️⃣ Hybrid Architectures
AE + IF fusion
RF + VQC gated refinement
Soft-gated uncertainty routing

📊 Dataset & Preprocessing
Credit Card Transactions Dataset
Feature scaling & normalization
Dataset splits:
Initial: 3-part (train/val/test)
Final: merged train + independent test
Extreme class imbalance handling

⚙️ Pipeline Flow
Data preprocessing & scaling
Feature compression (PCA / AE bottleneck)
Classical anomaly scoring
Quantum refinement on uncertain samples
Ensemble threshold tuning
Evaluation on held-out test data

📈 Evaluation Metrics
Precision
Recall
F1-score
ROC–AUC
Confusion Matrix

🧪 Key Experiments
Classical vs Quantum comparison
Removal of underperforming QML components
Supervised teacher integration (later removed)
Gated and soft-gated ensembles
Real-world unsupervised deployment focus

🧩 Key Findings
Random Forest remains the strongest standalone model
Autoencoder excels at recall
VQC performance is currently limited by hardware and expressivity
Hybrid models enable controlled quantum integration
Quantum adds insight, not dominance (yet)

🛠️ Tech Stack
Python, NumPy, Pandas
Scikit-learn
PyTorch
Qiskit Machine Learning
PennyLane (early experiments)
