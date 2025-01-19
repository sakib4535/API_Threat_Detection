# Advanced Persistent Threat (APT) Detection Framework
[!as](https://github.com/sakib4535/API_Threat_Detection/blob/main/as.webp)

## **Project Overview**

This project addresses the critical challenge of detecting Advanced Persistent Threats (APTs), a sophisticated and stealthy form of cyberattack. APTs aim to infiltrate and remain undetected within systems over extended periods, leveraging advanced techniques to evade conventional security measures. By employing machine learning methodologies, this framework uncovers anomalies and suspicious behaviors indicative of APT activities. The project synthesizes feature engineering, robust preprocessing, algorithmic design, and detailed evaluation metrics to create a resilient detection system.

![corr](https://github.com/sakib4535/API_Threat_Detection/blob/main/corr.png)

## **Research Context and Significance**

**Literature Review**
The rise of APTs has been extensively documented in cybersecurity literature. Traditional detection mechanisms, such as signature-based methods, often fail to identify novel and evolving APT tactics due to their reliance on pre-existing threat patterns. Recent research emphasizes the importance of behavioral analysis and anomaly detection in overcoming these limitations. Machine learning models have shown promise in this regard, providing:

- **Adaptability:** Models can generalize to detect unseen attack patterns.
- **Efficiency:** Automated analysis of large-scale network traffic data.
- **Precision:** Reduction in false positives, a critical requirement in cybersecurity.
Key studies highlight the role of features such as session durations, packet inter-arrival times, and TCP handshake anomalies in detecting sophisticated attacks. This project builds on these findings, offering a comprehensive and practical implementation.

## **Hypothesis**
**Feature Relevance Hypothesis:** Temporal, packet-level, transaction-level, and behavioral features significantly improve the detection accuracy of APTs.
**Algorithm Synergy Hypothesis:** Combining linear models (Logistic Regression) with non-linear models (Decision Trees) enhances the robustness and reliability of APT detection systems.
**Performance Benchmark Hypothesis:** The proposed model achieves superior detection metrics compared to traditional heuristic-based approaches.

![dur](https://github.com/user-attachments/assets/f66e3559-ce43-4d86-afac-bb40b047d874)

## **Key Components**

**1. Feature Engineering and Preprocessing**
Feature engineering is pivotal in capturing nuanced network behaviors that differentiate malicious activities from normal traffic. Key features include:
###**Temporal Features:**
- **stime** (Session Time): Identifies anomalies in session durations, which may signal unauthorized activities.
- **sintpkt** & **dintpkt** (Inter-packet Times): Detects stealthy communication patterns typical of APTs.
- **Packet-Level Features:**
- **sttl & dttl**(Source/Destination TTL): Highlights mismatches in TTL values indicative of routing irregularities or reconnaissance attempts.
synack & ackdat: Exposes anomalies in the TCP handshake process, revealing potential session hijacking or scanning activities.

### **Transaction-Level Features:**
- **trans_depth:** Flags probing or deep scanning behaviors.
- **res_bdy_len:** Identifies unusual response payloads that could indicate data exfiltration attempts.

### **Behavioral Features:**
**tcprtt** (TCP Round Trip Time): High RTT values may suggest intermediary attack stages.
Encoded Categorical Features (proto, state, service): Encapsulates protocol-specific behavior to uncover suspicious patterns.

![plot](https://github.com/user-attachments/assets/f5cd2c32-5f13-4bfb-abf0-ca956b710d25)

## **2. Algorithms Used**
### Logistic Regression:
Purpose: Exploits linear separability in feature spaces.
Advantages:
High interpretability, aiding cybersecurity analysts.
Computational efficiency, suitable for real-time detection.
Performance:
Accuracy: 97.2%
Precision: High, minimizing false positives.
Use Case: Effective for isolated anomalies.

### Decision Tree Regressor:
**Purpose:** Models non-linear dependencies and interactions between features.
**Advantages:**
Captures intricate patterns in data.
Provides a visual hierarchy of feature importance.
**Performance:**
**R² Score:** 0.924
**RMSE:** 0.091

## **4. Model Deployment**
The final model integrates both Logistic Regression and Decision Tree approaches to:
Enhance detection accuracy across diverse APT scenarios.
Balance interpretability with modeling complexity.
**Evaluation Metrics:**
**Precision:** 97%
**Recall:** 96%
**F1-Score:** 0.97
**ROC-AUC Score:** 0.98

## **5. Results Visualization**
ROC Curve: Demonstrates the model's ability to distinguish between benign and malicious activities.
Confusion Matrix: Illustrates classification performance, providing actionable insights for cybersecurity teams.

<p float="left">
  <img src="https://github.com/user-attachments/assets/531d5e77-e996-433a-9861-534b8d172bea" alt="result2" width="45%" />
  <img src="https://github.com/user-attachments/assets/e455ae90-1e16-46d5-b16f-b2ca5f676ee9" alt="result1" width="45%" />
</p>



Relevance to Advanced Threat Detection
Implications for Industry
APTs pose significant risks to industries such as finance, healthcare, and defense. This framework provides:
**Proactive Detection:** Identifies threats early to minimize damage.
**Comprehensive Coverage:** Addresses both known and emerging attack patterns.
**Scalability:** Adapts to varying network environments and attack vectors.

## Broader Research Impact
This work contributes to the growing body of knowledge on machine learning for cybersecurity. By demonstrating the efficacy of combined algorithms and targeted features, it sets the stage for future advancements in APT detection systems.
Usage Instructions
Data Preparation:


Ensure datasets are formatted and stored as per the provided folder structure.
Install all dependencies listed in the requirements file.
###Model Training:


Use the Feature_Engineering_and_Processing.ipynb notebook for data preprocessing and feature extraction.
Train models via models_deploy_APTDetection.ipynb.
## **Evaluation:**

Evaluate performance using the provided evaluation scripts.
Visualize results through the ROC Curve and Confusion Matrix.
Future Directions
Real-Time Integration: Deploy the model in live network monitoring setups.
Transfer Learning: Adapt the model to detect novel attack patterns.
Explainability Enhancements: Integrate feature attribution techniques to aid interpretability.
Hybrid Approaches: Combine this framework with anomaly detection models for improved generalization.

## Contributors
Team Members: Hasnain Imtiaz & Shakhauat Hossain Sumon

## Acknowledgments
This project leverages the UNSW-NB15 dataset for APT detection. Special thanks to the dataset creators and the broader research community for their invaluable contributions to cybersecurity.

## License
This project is licensed under the MIT License. See LICENSE for more details.
