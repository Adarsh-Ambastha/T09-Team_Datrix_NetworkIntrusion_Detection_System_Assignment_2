# Network Intrusion Detection System (NIDS)

This project aims to develop a **Network Intrusion Detection System (NIDS)** using machine learning models to classify network traffic as either benign, malicious, or outliers. The focus is on detecting various types of intrusions by analyzing network flow data and classifying it as either normal, suspicious, or anomalous (outliers). 
## Download the DataSet From here
##### *NIDS(DataSet) : https://drive.google.com/file/d/1NOqaLxFRfp-YmfwLD0yFU2UzV75sgmGC/view?usp=sharing*
## Project Overview

The project processes network traffic data by extracting relevant features from network flows (sequences of packets) and uses machine learning models to classify each flow into one of three categories:
1. **Malicious (0)**: Traffic that is considered harmful, such as Denial of Service (DoS) attacks, data exfiltration, etc.
2. **Benign (1)**: Normal traffic that poses no security threat.
3. **Outlier (2)**: Traffic that cannot be definitively categorized as either benign or malicious. These outliers represent ambiguous behavior that requires further inspection.

### Dataset

The dataset contains several features related to network traffic flows. Each record represents a network flow, and the key features include:

- **avg_ipt**: Average inter-packet time (indicating the time between consecutive packets)
- **bytes_in**: Number of bytes received in the flow
- **bytes_out**: Number of bytes sent in the flow
- **dest_port**: Destination port number (useful in identifying the type of service being accessed)
- **entropy**: Entropy, a measure of randomness in the packet data
- **num_pkts_out**: Number of outgoing packets
- **num_pkts_in**: Number of incoming packets
- **proto**: Protocol used (e.g., TCP, UDP)
- **src_port**: Source port number
- **total_entropy**: Total entropy across different layers in the protocol
- **duration**: Duration of the session (time taken for the network flow)

The **target variable** indicates whether the traffic is:
- **0**: Malicious traffic (attack).
- **1**: Benign traffic (normal).
- **2**: Outliers, where the traffic behavior is neither clearly benign nor malicious.

### Goal

The main goal of the project is to classify network traffic into three classes:
1. **Malicious (0)**: Harmful or attack traffic.
2. **Benign (1)**: Normal network behavior.
3. **Outlier (2)**: Traffic that doesn't clearly fall into the benign or malicious categories, thus requiring further inspection.

By correctly classifying traffic, the system can alert network administrators to potential intrusions or ambiguous traffic that may need further attention, helping in early detection of cyber threats.

## Machine Learning Models

In this project, several machine learning models were used to classify the network traffic:

1. **RandomForest Classifier**: 
   - The RandomForest model was trained to classify the network traffic based on the features described.
   - It provides built-in feature importance and handles high-dimensional data effectively.

2. **XGBoost Classifier**:
   - XGBoost was used to further enhance the model's performance and handle any class imbalance.
   - Known for its speed and accuracy, XGBoost is widely used for structured data classification tasks.

3. **Decision Tree Classifier**:
   - A Decision Tree model was employed to classify the traffic, providing an interpretable structure for decision-making.
   - Decision trees help identify the decision paths based on specific features like port numbers, protocols, and packet counts.

### GridSearchCV for Hyperparameter Tuning

To fine-tune the performance of the models, **GridSearchCV** was used to search for the best hyperparameters for RandomForest, XGBoost, and Decision Tree models. GridSearchCV allows the model to be trained and validated across various combinations of parameters, ensuring the best results for classification accuracy and generalization.

### Feature Importance

The following features were found to be most important for distinguishing between malicious, benign, and outlier traffic:

- **dest_port**: The destination port is highly indicative of certain types of services that might be vulnerable to attacks.
- **proto**: Protocol type is key in identifying the nature of traffic (e.g., TCP, UDP).
- **num_pkts_in** and **num_pkts_out**: The number of packets being transmitted helps in distinguishing normal traffic from high-volume attacks.
- **entropy** and **total_entropy**: These features measure the randomness in the data, which is often elevated in malicious or suspicious traffic.

## Prediction Results

The following are the classification accuracy scores on the test dataset for the models used:

1. **RandomForest**: Achieved an accuracy of **X%** on the test data.
2. **XGBoost**: Achieved an accuracy of **92%** on the test data.
3. **Decision Tree**: Achieved an accuracy of **83%** on the test data.

These models were evaluated using standard classification metrics such as accuracy, precision, recall, F1-score, and confusion matrices. The results indicate that all models effectively classify benign and malicious traffic, while handling outliers as a third class.

## How to Use the Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/nids-classification.git

# Authors


#### Adarsh (202418004)
#### Aman (202418004)
#### Yash (202418064)
#### Pragnya (202418065)

