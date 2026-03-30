# SAKTHIVEL S
# 212223220090
# Developing a Neural Network Classification Model

## AIM

To develop a neural network classification model for the given dataset.

## Problem Statement

An automobile company has plans to enter new markets with their existing products. After intensive market research, they’ve decided that the behavior of the new market is similar to their existing market.

In their existing market, the sales team has classified all customers into 4 segments (A, B, C, D ). Then, they performed segmented outreach and communication for a different segment of customers. This strategy has work exceptionally well for them. They plan to use the same strategy for the new markets.

You are required to help the manager to predict the right group of the new customers.

## Neural Network Model

<img width="766" height="768" alt="Screenshot 2026-02-13 154243" src="https://github.com/user-attachments/assets/1db8713b-6a9e-48c4-84ba-4e5c6488a74c" />


## DESIGN STEPS

### STEP 1:
Import necessary libraries and load the dataset.

### STEP 2:
Encode categorical variables and normalize numerical features.


### STEP 3:
Split the dataset into training and testing subsets.


### STEP 4:
Design a multi-layer neural network with appropriate activation functions.


### STEP 5:
Train the model using an optimizer and loss function.


### STEP 6:
Evaluate the model and generate a confusion matrix.


### STEP 7:
Use the trained model to classify new data samples.


### STEP 8:
Display the confusion matrix, classification report, and predictions.


## PROGRAM

### Name: SAKTHIVEL S
### Register Number: 212223220090

```
class PeopleClassifier(nn.Module):
    def __init__(self, input_size):
        super(PeopleClassifier, self).__init__()
        self.fc1 = nn.Linear(input_size, 64)
        self.fc2 = nn.Linear(64, 32)
        self.fc3 = nn.Linear(32, 16)
        self.fc4 = nn.Linear(16, 8)
        self.fc5 = nn.Linear(8, 4)
    def forward(self, x):
        x=F.relu(self.fc1(x))
        x=F.relu(self.fc2(x))
        x=F.relu(self.fc3(x))
        x=F.relu(self.fc4(x))
        x=self.fc5(x)
        return x
        


        

```
```python
# Initialize the Model, Loss Function, and Optimizer
model = PeopleClassifier(input_size=X_train.shape[1])
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(),lr=0.01)


```
```python
def train_model(model, train_loader,criterion,optimizer,epochs=100):
  for epoch in range(epochs):
    model.train()
    for X_batch, y_batch in train_loader:
      optimizer.zero_grad()
      output = model(X_batch)
      loss = criterion(output,y_batch)
      loss.backward()
      optimizer.step()

    if (epoch + 1) % 10 == 0:
      print(f"Epoch {epoch+1}/{epochs}, Loss: {loss.item():.4f}")
        

```



## Dataset Information

<img width="778" height="577" alt="Screenshot 2026-02-13 155752" src="https://github.com/user-attachments/assets/661f75ea-8c9f-4fd1-9e69-0d749dfc2092" />

## OUTPUT

### Confusion Matrix

<img width="697" height="536" alt="Screenshot 2026-02-13 155834" src="https://github.com/user-attachments/assets/77028e13-c6fa-47f0-9115-c3583313d2d8" />

### Classification Report

<img width="822" height="356" alt="image" src="https://github.com/user-attachments/assets/5ba33b44-161f-4444-8908-e78f9a6edc9e" />


### New Sample Data Prediction

<img width="1019" height="326" alt="image" src="https://github.com/user-attachments/assets/b6b7823c-4988-42b7-8414-1357afb02f59" />

## RESULT
Thus the neural network classification model was successfully developed.
