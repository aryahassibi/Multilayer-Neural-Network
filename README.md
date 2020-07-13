# Multilayer Neural Network
This [Neural Network](#neural-network) is written in Python (3.7.6) <br>
All of the matrix calculations of this neural network are done by [NumPy](https://numpy.org/)(1.9.6)

Multilayer networks solve the classification problem for non linear sets by employing hidden layers, whose neurons are not directly connected to the output.
> *note:* The Activation function of this neural network is the ***sigmoid*** function 
### *HOW TO WORK WITH neuralNetwork.py:*
1. Import Class
      
        from neuralNetwork import *
        
2. Create an Object

        nn = NeuralNetwork(number_of_first_layer_nodes, number_of_second_layer_nodes, ..., number_of_n-th_layer_nodes)

    > *note:* this is a multilayer neural network so it can have as many layers as it wants. 
    for example:
    
        nn = NeuralNetwork(5, 8, 2, 6, 1)
        nn = NeuralNetwork(6, 3, 4)
      
    
3. Generate the inputs and the targets that you want to train your network with
    <br>For training the neural netwrok you should use the **train()** method: 
          
        nn.train(inputs_list, targets_list)

    > *note:* the length of **inputs_list** should be equal to **first argument** of the neural network <br>
    >    and the lenght of **targets_list** should be equal to **last argument** of the neural network

    for example this time we are going to train the neural netwrok to solve [XOR](https://github.com/aryahassibi/XOR-Problem) problem:
    
        inputs = [[0, 0], [1, 0], [1, 1], [0, 1]]
        targets = [[0], [1], [0], [1]]

        # Training the neural network 10000 times
        for _ in range(10000):
            index = randint(0, 3)
            nn.train(inputs[index], targets[index])

4. Getting neural network prediction
    <br>For Getting predictions you should use **predict()** method:

        nn.predict(inputs_list)

    > *note:* the length of **inputs_list** should be equal to **first argument** of the neural network

    Again we continue with [XOR](https://github.com/aryahassibi/XOR-Problem) problem.<br>
    For getting the result after trianing the neural network you can do this:
    
        inputs = [[0, 0], [1, 0], [1, 1], [0, 1]]

        for i in range(4):
            output = nn.predict(inputs[i])[0]
            print("XOR", inputs[i], " ≈ ", output)

    *output:*
    
          XOR [0, 0]  ≈  0.040257468759495006
          XOR [1, 0]  ≈  0.9490906272946118
          XOR [1, 1]  ≈  0.05838670461374751
          XOR [0, 1]  ≈  0.944367949333263
      
            
           


