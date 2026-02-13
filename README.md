## AIM

To develop a neural network regression model for the given dataset.

## THEORY

Explain the problem statement

## Neural Network Model

<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/a4e003c3-00a0-4168-bd4e-cfae7ae556bf" />


## DESIGN STEPS

### STEP 1:

Loading the dataset

### STEP 2:

Split the dataset into training and testing

### STEP 3:

Create MinMaxScalar objects ,fit the model and transform the data.

### STEP 4:

Build the Neural Network Model and compile the model.

### STEP 5:

Train the model with the training data.

### STEP 6:

Plot the performance plot

### STEP 7:

Evaluate the model with the testing data.

## PROGRAM

### Name: Gowshik S
### Register Number: 212223220026
```python

import torch.nn as nn
import torch.optim as optim
class Neuralnet(nn.Module):
   def __init__(self):
        super().__init__()
        self.n1=nn.Linear(1,10)
        self.n2=nn.Linear(10,20)
        self.n3=nn.Linear(20,1)
        self.relu=nn.ReLU()
        self.history={'loss': []}
   def forward(self,x):
        x=self.relu(self.n1(x))
        x=self.relu(self.n2(x))
        x=self.n3(x)
        return x
     
Gows_brain=Neuralnet()
criteria=nn.MSELoss()
optimizer=optim.RMSprop(Gows_brain.parameters(),lr=0.001)
     
def train_model(Gows_brain,x_train,y_train,criteria,optmizer,epochs=4000):
    for i in range(epochs):
        optimizer.zero_grad()
        loss=criteria(Gows_brain(x_train),y_train)
        loss.backward()
        optimizer.step()

        Gows_brain.history['loss'].append(loss.item())
        if i%200==0:
            print(f"Epoch [{i}/epochs], loss: {loss.item():.6f}")
     

train_model(Gows_brain,x_train_tensor,y_train_tensor,criteria,optimizer)
```
## Dataset Information
<img width="237" height="716" alt="image" src="https://github.com/user-attachments/assets/da2c9215-c6d8-4d33-9f30-f15f96fc59db" />

## OUTPUT
<img width="622" height="515" alt="image" src="https://github.com/user-attachments/assets/a5279f9f-087e-4320-899f-2598c7e359f1" />

<img width="677" height="130" alt="image" src="https://github.com/user-attachments/assets/69f53cbf-fc98-4c1f-80ca-88cf45693602" />

### Training Loss Vs Iteration Plot

<img width="785" height="653" alt="image" src="https://github.com/user-attachments/assets/76869dbe-430c-493a-903f-659d96e457c2" />


### New Sample Data Prediction

<img width="521" height="103" alt="image" src="https://github.com/user-attachments/assets/2370e168-2f73-4f30-9899-e0ce9f12189a" />

## RESULT

Thus,the code was successfully executed to develop a neural network regression model...


