# **DoS Network Attack Detector Using Multi-Channel Neural Network Model and Mutual Information-Based Feature Selection**

## **Introduction**  
In modern cybersecurity, detecting malicious network attacks is critical to preventing service disruptions. This project focuses on detecting **Denial of Service (DoS) Hulk attacks** using **a deep learning model optimized with mutual information-based feature selection**.  

Traditional intrusion detection methods often rely on manually defined rules or shallow machine learning techniques. However, this project takes an advanced approach by leveraging:  
- **Mutual Information (MI) Feature Selection** to extract the most relevant features from network traffic data.
- **A Multi-Channel Neural Network Model** that processes each selected feature separately before learning complex patterns.
- **Binary Classification (Benign vs. DoS Hulk)** to identify potential network threats with high accuracy.

## **Dataset**  
This project uses the **CICIDS 2017 dataset**, specifically the `Wednesday-workingHours.pcap_ISCX.csv` file, which contains labeled network traffic data. The dataset includes various network flow features, such as packet sizes, flow durations, and connection statistics, with a label indicating whether the traffic is **benign** or a **DoS Hulk attack**.

### **Key Characteristics of the Dataset:**  
- **Traffic data features** extracted from real network activities.
- **Binary classification labels**: `BENIGN` (normal traffic) and `DoS Hulk` (attack traffic).
- **High-dimensional feature space**, requiring feature selection techniques to enhance model performance.

## **Mutual Information-Based Feature Selection**  
Feature selection is crucial in machine learning to reduce dimensionality, improve model efficiency, and enhance interpretability. In this project, we use **Mutual Information (MI)** to identify the most relevant features for DoS attack detection.

### **What is Mutual Information?**  
Mutual Information measures the **dependency between a feature and the target label**. It quantifies how much knowing the value of a feature reduces uncertainty about the class label. Mathematically, MI is defined as:

\[
I(X; Y) = \sum_{x \in X} \sum_{y \in Y} p(x, y) \log \frac{p(x, y)}{p(x)p(y)}
\]

where:
- \( p(x, y) \) is the joint probability distribution of the feature \( X \) and the class label \( Y \).
- \( p(x) \) and \( p(y) \) are the marginal probabilities.
- Higher MI values indicate stronger relevance to the target label.

### **Why Use MI for Feature Selection?**  
- Identifies the most **informative features** while discarding irrelevant ones.
- Reduces computational cost by eliminating redundant features.
- Improves the model's generalization by minimizing noise.

From the dataset, we extract the **top 10 most relevant features** using MI, which are then used as inputs for the neural network model.

## **Multi-Channel Neural Network Model**  
To effectively analyze multiple features, we implement a **multi-channel neural network** where each feature is processed through its own input pathway before combining the learned representations.

### **Why Use a Multi-Channel Model?**  
- **Preserves unique feature relationships**: Each selected feature is treated as a separate input channel.
- **Enhances learning capacity**: The network can learn independent and joint patterns between features.
- **Improves classification performance**: Helps distinguish between benign and DoS Hulk attack traffic.

### **Model Architecture**  
1. **Separate Input Layers**: Each feature has its own dedicated input neuron.
2. **Independent Processing Layers**: Each input passes through its own dense layer with activation functions to extract feature-specific patterns.
3. **Concatenation Layer**: The processed features are combined into a unified representation.
4. **Fully Connected Layers**: Additional dense layers refine the learned patterns.
5. **Output Layer**: A single neuron with a **sigmoid activation function** predicts whether the network traffic is benign or an attack.

## **Training and Evaluation**  
### **Training Process:**  
- The dataset is split into **training (80%)** and **testing (20%)** subsets.
- The multi-channel model is trained using the **Adam optimizer** with **binary cross-entropy loss**.
- The model is evaluated on a validation set during training to prevent overfitting.

### **Performance Metrics:**  
The trained model is evaluated using:
- **Confusion Matrix**: Shows true positives, false positives, true negatives, and false negatives.
- **Precision & Recall**: Measure how well the model differentiates between classes.
- **F1-Score**: Provides a balanced measure of precision and recall.
- **Accuracy**: The overall correctness of predictions.

## **Results and Visualization**  
To analyze model performance, we visualize:
- **Training & Validation Loss Curves** to monitor convergence.
- **Training & Validation Accuracy Curves** to assess learning progress.
- **Confusion Matrix** for classification insights.

## **Conclusion**  
This project successfully demonstrates an advanced **deep learning approach for detecting DoS Hulk attacks**. By leveraging **mutual information-based feature selection** and a **multi-channel neural network**, the model achieves high accuracy in distinguishing between benign and malicious network traffic.

### **Key Takeaways:**  
- **Feature selection** enhances efficiency and interpretability.
- **Multi-channel networks** improve learning across multiple input features.
- **Deep learning-based intrusion detection** can significantly enhance cybersecurity defenses.

## **Future Improvements**  
- **Extending to Multi-Class Classification** for other attack types.
- **Integrating Real-Time Detection** into cybersecurity systems.
- **Testing on Other Intrusion Detection Datasets** for generalization.

---
### **Author**  
Ali Ibraheem  

---
