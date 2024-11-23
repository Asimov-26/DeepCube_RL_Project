DeepCube
----
One of Rubik's Cube solvers with Deep Reinforcement Learning.
The algorithm is based on the following paper.
* S. McAleer et al. (2018), Solving the Rubik's Cube without Human Knowledge

## About contents in the directory
bin/exec - Contains the saved models.

codes - Contains the code for models.

include - Contains the dependencies for the Neural Network model.

Outputs - Visualize.py for visualization, metrics.csv, and also the evaluation results

## Usage
First, install [OpenBLAS](https://www.openblas.net/)
```
MacOS
$ brew install openblas
Ubuntu
$ sudo apt-get install libopenblas-dev
```
Then, get this repository and make
```
$ git clone https://github.com/Ktakuya332C/deepcube
$ cd deepcube
$ make
```
Solve randomly scrambled Rubik's Cubes by
```
$ bin/exec/search_cube
Scramble the cube. The order of moves is
D' R' U F' L' L D R' L' R'
Solved the cube. The order of moves is
R' L R' D' F U' R D
```
Paste these seqeuences to a [website](https://rubiks-cu.be/#cubesolver) to see how the algorithm solved the cube.

## Training a neural network
Train a neural network employed in the algorithm by
```
$ bin/exec/trainer_cube
```
which will train a network and save its parameters under `/tmp/`. 

Since the executable `search_cube` uses parameters in `data/` directory by default, to use the trained parameters, copy files like `/tmp/dense_layer_*` to `data/`. Then, the next execution of `seach_cube`
```
$ bin/exec/search_cube
```
will use the trained parameters.


## Visualization
I have attached the 'visualize.py' for visualizing loss and target cost trajectory through the epochs.
Results are in 'metrics.csv'.


