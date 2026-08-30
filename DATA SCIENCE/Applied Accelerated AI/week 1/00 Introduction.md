This folder will consists notes from applied accelerated ai nptel course. 

Model:- In artificial intelligence, a model is a mathematical program trained on data to recognize patterns and make decisions** without being explicitly programmed for every scenario. Think of it as a digital brain that has learned a specific skill—like translating languages, identifying objects in photos, or predicting stock prices—by studying massive amounts of examples. LLMS are ai models
How an AI Model Works
To understand an AI model, it helps to break it down into three core concepts:
- **The Algorithm (The Blueprint):** This is the underlying mathematical structure or set of rules (like a Neural Network or Decision Tree) used to build the model.
- **The Training (The Education):** The algorithm is fed a massive dataset. For example, to make a model that detects cats, it is shown millions of labeled images of cats and not-cats.
- **The Model (The Graduate):** Once the training is complete, the resulting bundle of saved mathematical weights and parameters is the "model." It can now take _new_, unseen data and output a correct prediction or response.

Weights:- In artificial intelligence, a **weight** is a numerical value that controls the strength of the connection between two neurons in a neural network. It determines how much influence a specific input has on the network's final output.
Think of weights as **knobs that are tuned during the training process** to help the AI learn from its mistakes and make accurate predictions.
How Weights Work
To understand weights, it helps to see how a neural network processes data:
- **Input Data:** The network receives pieces of information (like pixels of an image or words in a sentence).
- **Multiplication:** Each input is multiplied by its assigned **weight**. A high weight means the input is very important, while a weight near zero means the input is mostly ignored.
- **Summation:** The network adds up all the weighted inputs, along with a baseline value called a **bias**.
- **Output:** If the total sum passes a certain threshold, the neuron activates and passes the signal forward.

Gradient kya hai? 
Gradient basically model ko batata hai:
"Mere weights ko kis direction mein change karna chahiye taaki prediction better ho?"
Example:
```
Current weight = 0.5
Gradient = -0.2
        ↓
Optimizer decides how to update it
        ↓
New weight ≈ 0.52
```
So:
**Weight = kya value hai**  
**Gradient = value ko kis direction mein change karna hai**

Optimizer:-
Optimizer is the **algorithm that actually updates the weights** using gradients.
Training roughly:
```
Input
  ↓
Model (weights)
  ↓
Prediction
  ↓
Compare with correct answer
  ↓
Loss
  ↓
Gradients
  ↓
Optimizer
  ↓
Update weights
  ↓
Repeat 🔄
```
**Adam** is one popular optimizer.

Activations 
Activations are the **temporary values produced inside the neural network while processing an input**.
Think:
```
Input
 ↓
Layer 1 → activations
 ↓
Layer 2 → activations
 ↓
Layer 3 → activations
 ↓
Output
```
Training ke time inhe often temporarily store karna padta hai, which is why they also consume VRAM.