#  MIT-BIH Normal vs Abnormal Beat Classification
aim
Classify heartbeats from the MIT-BIH dataset as:
Normal (0)
Abnormal (1) – includes types like L, R, V, A, F

# PROCESS

 1)Loads ECG Data
Reads .csv files and their corresponding annotations.txt files.

Extracts ECG signals from records.

Gets positions of heartbeats and their labels.

2) Creates Input Data
Cuts out 90-sample segments around each heartbeat.

Labels each beat:

0 if it's normal ('N')

1 if it's abnormal (L, R, V, A, F)

Stores the beats in X and the labels in y.

3) Preprocessing
Standardizes (normalizes) the beats using StandardScaler.

4) Visualization
Plots:

A sample ECG signal
<img width="1247" height="393" alt="2e57e370-7474-4ad8-be8a-7e1d9f7e4f23" src="https://github.com/user-attachments/assets/bc6daebe-d974-46da-86ce-a4e0b8af006e" />

One beat (normal or abnormal)
<img width="859" height="393" alt="3019b4b0-abc5-4f37-87d4-b85d322a7513" src="https://github.com/user-attachments/assets/6f95f546-e399-494c-a6a0-8d5e6ef59d04" />

Histogram of average beat amplitudes

5) Model Building
Builds a 1D CNN model using PyTorch:

2 convolution layers + pooling

Fully connected layers to classify into 2 classes

6) Training
Trains the CNN on the data for 10 epochs.

Uses CrossEntropyLoss and Adam optimizer

7) Evaluation
Prints a classification report (precision, recall, F1-score)

Shows a confusion matrix with seaborn heatmap
<img width="556" height="455" alt="0037373b-ea04-4d2d-8d68-0abbbda32dbd" src="https://github.com/user-attachments/assets/987e0b2d-f628-46c3-a2f7-cfcd8216cc58" />
