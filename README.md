# AI-Bandwidth-Prediction

| **Title**      |Bandwidth User Prediction |
| ---------- |-------------------|
| **Team**       |Nguyễn Thiện Phúc - thienphuc0510@gmail.com <br/> Trương Hoàng Ngân - ngantruong@glassegg.com |
| **Predicting** |We will build a model to predict the fuel efficiency (MPG-Miles Per Gallon)|
| **Data**       |Auto MPG Data Set <br/> UCI Machine Learning Repository Data link : https://archive.ics.uci.edu/ml/datasets/auto+mpg |
| **Features**   | <ol> <li>mpg: continuous</li> <li>cylinders: multi-valued discrete</li> <li>displacement: continuous</li> <li>horsepower: continuous</li> <li>weight: continuous</li> <li>acceleration: continuous</li> <li>model year: multi-valued discrete</li> <li>origin: multi-valued discrete</li> </ol>|
| **Models**     |<ol> <li>Multi-layer Perceptron is a class of feedforward artificial neural network. <br/> An MLP consists of at least three layers of nodes: an input layer, a hidden layer and an output layer. <br/> MLP utilizes a supervised learning technique called backpropagation for training.</li>  <li>Regression Tree is a predictive model <br/> to go from observations about an item (represented in the branches) <br/> to conclusions about the item's target value (represented in the leaves).</li> <li>Regression Random Forests are an ensemble learning method <br/> for classification, regression and other tasks that operates <br/> by constructing a multitude of decision trees.</li> </ol>|
| **Discussion** |Which model return the better resuls? <br/> How to improve the other models? <br/> How to tuning the hyper parameters in models? |
| **Future**     |Applying the decision tree method into business problems (Predict Efficiency).<br/> Use other methods like: XGBoost, Reinforcement learning,...<br/> Use tuning methods like: gridsearchcv, pruning... |
|**References**  |[1] https://machinelearningcoban.com/2018/01/14/id3/ <br/> [2]https://towardsdatascience.com/random-forest-and-its-implementation-71824ced454f <br/> [3] https://www.youtube.com/watch?v=g9c66TUylZ4 <br/> [4] https://www.kaggle.com/arunkumarramanan/data-science-python-fuel-efficiency-prediction|
| **Results**    |MLP: Testing set Mean Abs Error:  2.04 MPG <br/> Regression Tree score: 0.8772300290913486 <br/> Regression Random Forest score: 0.9084957992180025 |