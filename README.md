[//]: # (Image References)

[image1]: ./demo/demo.gif

[image2]: ./demo/avoiding.gif

# Deep Reinforcement LEarning for Autonomous Driving


## Scaled Autonomous Vehicles Fall 2020 - Team A

### Team Members:

Lingyi Song (lingyis@g.clemson.edu)

Anshuman Sharma (anshums@g.clemson.edu)

Prateek Sharma (prateek@g.clemson.edu)

## DEMO

![alt text][image1]
![alt text][image2]

---

The repository contains three sub-repositories:
1. f1tenth-RL: It contains code to execute the code with 15 actions.
2. 8 actions: It contains code to execute the code with 8 actions.
3. 9 actions: It contains code to execute the code with 9 actions.

Each sub repository has following files:

1. car/sensors.py: Interface with lidar data from the simulator.
2. car/car_contorl.py: Interface with controller of the simulator.
3. car/safety_control.py: Ensures safety of the car.
4. rl_car_driver.py: It contains the training cycle.
5.  dqn.py: It includs the NN and the DQN algorithm.
6. state.py: creates state by preprocessing data and stacking them.
7. replay.py: manage the samples and the replay buffer.

The code was modified from https://github.com/MichaelBosello/f1tenth-RL.


**

**Installation**
1. For installation of the simulator follow the instructions given on https://f1tenth.org/build.html.
2. Install the dependencies from https://github.com/MichaelBosello/f1tenth-RL.
3. Install tensorflow 2.1.x 
 $ pip3 install tensorflow
 4. Clone this repository:
 $ git clone https://github.com/prateeks97/Deep_Reinforcement_Learning_on_F1_10th/tree/main/f1tenth-RL

**

**Run**
Launch the f1tenth simulator:
-   Go to the working directory of the simulator (_/simulator_)
`$ source devel/setup.bash`
`$ roslaunch f1tenth_simulator simulator.launch`

Run the RL algorithms:
For running algorithm with 15 actions/8 actions/ 9 actions go to the respective repository as indicated on the top.
`$ python3 rl_car_driver.py --simulator`

#### Simulator options:

-   The guide of the simulator is in the readme  _simulator/src/f1tenth_simulator/README/md_
    
-   You may want to change the simulator options, check out  _simulator/src/f1tenth_simulator/params.yaml_
    
-   If you want to change the track, you must edit  _simulator/src/f1tenth_simulator/launch/simulator.launch_
    
    Search for  `<arg name="map" default="$(find f1tenth_simulator)/maps/levine.yaml"/>`  Change  _levine_  (the default map) with one map present in the folder  _simulator/src/f1tenth_simulator/maps_

**Load a model**
You can use the --model argument to load a trained model, e.g.:
`python3 rl_car_driver.py --model=./run-real-car/models --simulator`

Changes in *rl_car_driver.py*: For training uncomment lines 283 and 284. For evaluation keep lines 283 and 284 commented.
