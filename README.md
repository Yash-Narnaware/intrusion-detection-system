# Multi-Class Intrusion Detection System Based on System Call Sequences

## Project Overview
This project aims to build a **multi-class intrusion detection system** (IDS) that classifies sequences of system calls based on machine learning techniques. The system distinguishes between normal behavior and different types of attack sequences, using **deep learning** models such as **LSTM** (Long Short-Term Memory) networks. The dataset used includes system call sequences from both normal and attack instances, and this project includes preprocessing, feature extraction, and data augmentation techniques.

## Features

- **System Call Sequences**: The model classifies system call sequences of different applications and attacks.
- **Multi-Class Classification**: Supports multiple attack types (labels 1 to 6) and normal sequences (label 0).
- **Data Augmentation**: Implements techniques like oversampling and undersampling to handle class imbalances.
- **Modeling with LSTM**: Uses a deep learning approach (LSTM) to classify the sequences effectively.
- **Data Preprocessing**: Includes tokenization and padding of sequences for input into the LSTM model.

## Dataset
The dataset used in this project is the **ADFA-LD** dataset, which is part of the ADFA (Australian Defence Force Academy) intrusion detection dataset. The ADFA-LD dataset contains labeled system call sequences collected from real-world applications, including both normal activities and various types of attacks.

### Dataset Details:

- **Source**: The dataset can be found at [ADFA-LD Dataset]([https://www.unsw.adfa.edu.au/](https://research.unsw.edu.au/projects/adfa-ids-datasets)]).
- **Labels**: The dataset contains system call sequences labeled as follows:
  - **Label 0**: Normal system calls (non-attack)
  - **Labels 1-6**: Different types of attacks, such as:
    - **Adduser**: 
    - **Hydra FTP**: 
    - **Hydra SSH**: 
    - **Java Meterpreter**: 
    - **Meterpreter**: 
    - **Web Shell**: 
- **Format**: The sequences are recorded as system call events, where each event corresponds to a system call identifier.

The dataset is preprocessed to extract meaningful features from raw system call sequences, followed by splitting into training, validation, and test sets.

### Structure of the Data:
```plaintext
system_calls_with_labels.csv
├── System_Calls  # Sequence of system calls (e.g., [240, 311, 78, 240, ...])
├── Label         # Attack type (0 = normal, 1-6 = different types of attacks)
└── Attack Type   # Name of the attack
```

## Data Preprocessing
The preprocessing steps include:
- Converting system calls from a string format to lists.
- Tokenizing the system call sequences.
- Padding the sequences to ensure uniform input size for the model.
- Handling class imbalances using oversampling and undersampling.
- Separating attack instances for inclusion in the validation dataset.

## Project Workflow
The project follows this general flow:

1. **Data Loading**: Load the dataset and examine the distribution of attack types.
2. **Data Preprocessing**:
   - Separate attack and normal instances.
   - Tokenize and pad the system call sequences.
   - Split the data into training, validation, and test sets.
   - Handle class imbalance using oversampling and undersampling.
   - Add a subset of attack instances to the validation dataset.
3. **Model Training & Evaluation**: The model training and evaluation are handled in a Jupyter Notebook (`PGSL_project_LSTM_based_IDS.ipynb`), where the LSTM model is trained on the preprocessed sequences.


