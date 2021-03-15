# **Neural_Network_Charity_Analysis**

## **Overview:**
There is a philanthropic foundation which is dedicated to helping organizations that are protecting environment, improve people's well-being and unify the world, by providing them donations. 
The goal of this company is to analyze the impact of each donation at the end of potential recipients. This helps to ensure that the foundation's money is being used effectively. Unfortunately, not every donation that company makes, is impactful. In some cases, an organization will take the money and disappear. As a result, the company wants to find out which organizations are worth donating to, and which are at high risk. 

They want us to create a mathematical, data driven solutions that can do this accurately. To solve the problem at hand, a deep learning neural network is to be designed and trained using Python's Tensorflow library. This model evaluates all types of input data and will produce a clear decision-making result. Also, we need to optimize the deep learning model to obtain the best possible accuracy, so that it can be effectively determined which organizations will receive donations from this philanthropic foundation.
## **Results:**
- ### **Data Preprocessing:**
    - Variable 'IS_SUCCESSFUL' is considered the target for our model
    - Variables EIN , NAME and ASK_AMT are neither targets nor features, and are removed from the input data
    - All the remaining variables except above four variables, are kept as features

- ### **Compiling, Training, and Evaluating the Model:**

    ![](https://github.com/kirtibhandari/Neural_Network_Charity_Analysis/blob/main/Resources/initial_model.png)
    
    ![](https://github.com/kirtibhandari/Neural_Network_Charity_Analysis/blob/main/Resources/first_attempt.png)

    ![](https://github.com/kirtibhandari/Neural_Network_Charity_Analysis/blob/main/Resources/second_attempt.png)

    ![](https://github.com/kirtibhandari/Neural_Network_Charity_Analysis/blob/main/Resources/third_attempt.png)

    - How many neurons, layers, and activation functions did you select for your neural network model, and why?

        **Layers:** 
           
        Out of the three attempts made to optimize the model, the number of layers in the model, which gave most optimum results for our attempt, has only 1 hidden_layers. Here first layer acts a superficial layer which when present on its own, without any other hidden layer will act as simple logistic regression model, along with one output layer. As we tried in next attempt to add a layer but the accuracy reduced instead of increasing. On the basis of this trial and error method, we got best results with only two hidden layers.

        **Neurons:**
            
        In the aspect of number of neurons for the input layer, the best model in our attempts have twice the number of features , fed into input layer, and thrice the number of input features to hidden layer and 1 neuron to output layer as per the general recommendations of neuron range. This combination proved optimal for our attempts as is clear from the second and third attempt results that when we put in any other values for neurons for the input and hidden layer, the accuracy got a bit reduced.
        **Activation functions:**

        1. ReLU: to enable our model to enable non linear relationships among the variables in the input data (to identify non-linear characteristics from the input values) has performed better than the usage of tanh function in second hidden layer of third model attempt which did not perform better when we only used ReLU function for our input and hidden layer. Hence, ReLU worked best for input layer and hidden layer.
        
        2. Sigmoid function: to produce a probability output, as this is a classification model and we only want a yes or no binary decision.

    - **Were you able to achieve the target model performance?**
        
        The desired accuracy here is 75% or higher and that was not achieved by the model initially. We were able to achieve only approximately 73% accuracy in our 3 attempts.

        ![](https://github.com/kirtibhandari/Neural_Network_Charity_Analysis/blob/main/Resources/initial_results.png)

        ![](https://github.com/kirtibhandari/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization_results.png)

    - **Steps that were taken to try and increase model performance:**
    
        We made three attempts to increase our initial model's performance:
        1. Removing the outlier variable ASK_AMT in the dataset used in initial deep learning model
        2. Changing the bin size of APPLICATION_TYPE and CLASSIFICATION variables
        3. Changing the number of neurons in hidden layers
        4. Adding a another hidden_layer 
        5. Changing the optimization function
       
       
## **Summary:**

The overall results of the deep learning model built in this analysis provides the accuracy of approximately 73 %, in our case. The initial model results and results obtained by making three attempts to optimize the performance of the model are almost comparable.

### **Recommendation:**

We may use Random forest classifiers to solve this classification where this model combines multiple smaller models into a robust and accurate model. These models use a number of weak learner algorithms which are then in combination, use their output to provide final classification. in this model, input data is in tabular form as we have our dataset,the output and selection of features are easily interpretable and are capable to handle outliers and non-linear data.

The random forest model improves upon classification on the consensus of weak learners whereas the deep learning models evaluate input data within a single neuron as well as multiple layers.
Their predictive performance may be comparable, but the implementation and training times, which is in seconds, for random forest classifier, as compared to couple of minutes to train on tens of thousands of data using deep learning model. Hence, random forest classifier, for a tabular data, provides comparable predictive accuracy on big datasets with less code and faster performance than a neural network , deep learning model.


