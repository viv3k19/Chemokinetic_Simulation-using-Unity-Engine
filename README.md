# Chemokinetic Simulation
This project focuses on simulating chemotaxis in agents within a dynamic environment. The objective is to explore the development of chemotaxis in artificial agents using a basic "forward or rotate" movement strategy, similar to the bacteria C. elegans. By employing a single probabilistic spiking perceptron, this project aims to investigate whether simpler artificial agents can achieve chemotaxis in a dynamic environment. The findings from this simulation can contribute to research in artificial biology, evolutionary computing, and artificial intelligence.

## Chemotaxis
Chemotaxis is the ability of organisms to move in response to a chemical stimulus. It plays a critical role in various biological processes, such as bacteria seeking nutrition or avoiding toxins, sperm navigating towards eggs, or leukocytes migrating during infection or injury.

## Dynamic Environment
In this simulation, the dynamic environment is a 2-dimensional finite space (R2) with x and y axes. Each point in the environment is represented by an ordered pair of real numbers, indicating its distance from the origin along the respective axes. The environment includes a nutrition source that moves randomly within the space, simulating a dynamic scenario.

## Artificial Agents
Artificial agents in this simulation are equipped with artificial neural networks (ANNs), computational systems inspired by biological neural networks. Specifically, the simulation utilizes a probabilistic version of spiking neural networks (SNNs). Unlike other neural networks, SNNs only fire when the membrane potential, representing the neuron's electrical charge, reaches a certain value. The firing process is probabilistic, meaning a neuron with a charge of 0.7 has a 70% chance of firing.

The artificial agents possess the following main properties:

* Motor: Similar to the flagella of the bacteria Escherichia coli (E. coli), the motor enables agents to move forward in a straight line or rotate randomly.

* Perceptor: Agents receive input values from their environment, specifically the distance between the agent and the nutrition source (environmental chemical gradient).

* Neuron: The neuron takes the input value from the perceptor, subtracts it from the previous perceptor value, and adds a unique neural bias value for the agent. The resulting output determines the probability of an agent moving forward instead of rotating. The subtraction of the new input from the previous input allows agents to perceive changes in nutrition concentration over time, enabling them to sense whether they are moving toward a higher concentration. The probabilistic firing of neurons simplifies the simulation compared to conventional spiking neural networks.

* Energy Level: Agents are assigned an initial energy value at birth, which increases or decreases based on the nutrition concentration in their environment. Agents successfully navigating to higher nutrition concentrations are rewarded with increased energy levels.

* Evolution: After a predefined number of steps, agents update their neural biases, which determine the frequency of neural firing. The new bias is calculated based on the difference between the agent's current energy value and its highest achieved energy value, as well as the corresponding difference between the current bias and the bias that resulted in the smallest energy loss.

## Algorithm
The evolutionary algorithm in this simulation follows these steps:

1. Spawn a number of agents randomly throughout the environment, each assigned initial random neural bias values. Place the nutrition source in the environment.

2. Agents receive input from the environment (proximity to the nutrition source) and calculate their neural output based on the previous input and neural bias. The neural output determines the probability of agents moving or rotating randomly.

3. Repeat step 2 for a specified number of times until evolution occurs. Evaluate energy levels and update neural biases.

4. Repeat steps 2 and 3 until the simulation is stopped.

## Technologies used
* Unity Game Engine
* C#

## Run
To run the application:

1. Click "+10 agents" any number of times to spawn agents.
2. Press the play button to start the simulation.
3. Ensure that the "MainScene" is the active scene in Unity.
4. Adjust the speed and zoom sliders to modify the simulation.
5. Click reset to restart the application.
6. Note that different screen resolutions may result in slight variations in the GUI design.

The text display provides the following information:

* Cycle: Current movement-perception cycle of the agent.
* Generation: Current generation (100 cycles).
* Population: Number of current agents.
* Bias average: Average bias value of all agents.
* Energy average: Average highest energy (or smallest energy loss) among all agents.

## Screenshots

![Chemotaxis](https://github.com/viv3k19/Chemokinetic_Simulation-using-Unity-Engine/assets/82309435/a44dd566-2362-4501-92b3-176d2d7d8084)

# Project Creator
* Vivek Malam - Feel free to contact me at viv3k.19@gmail.com for any questions or feedback.
