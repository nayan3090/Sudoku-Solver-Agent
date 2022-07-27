# AI agent built using constraint propagation and search to solve any Sudoku puzzle

This repository is a course project from [Udacity's Artifical Intelligence Nanodegree](https://www.udacity.com/course/ai-artificial-intelligence-nanodegree--nd898).

In this project, an intelligent agent is built for solving any Sudoku puzzle using the following AI techniques:

### Constraint Propagation
When trying to solve the puzzle, local constraints for each square are identified. These constraints help narrow the possibilities for the answer and thus is very helpful for solving the puzzle. Three strategies are used for constraint propagation in this puzzle and to get closer to the solution:
1. **Elimination**: The elimination strategy says that if a box has a value assigned, then none of the peers of that box can have the same value.
2. **Only choice**: The only choice strategy says that if only one box in a unit allows a certain digit, then that box must be assigned that digit.
3. **Naked twins**: The naked twins strategy says that if you have two or more unallocated boxes in a unit and there are only two digits that can go in those two boxes, then those two digits can be eliminated from the possible assignments of all other boxes in the same unit.
These three strategies are utilized to repeatedly apply simple constraints to iteratively narrow down the search space of possible solutions.

### Search
In the process of solving the Sudoku puzzle, there are many instances at which there can be two or more possibilities for the value that needs to go in the square. In order to find the correct value that will go in any square, the agent takes into account all the possibilities after all the local constraints are applied. This creates a whole tree of possibilities and the agent is tasked to find a way to traverse the tree until the solution to the puzzle is obtained. The search algorithm used in this project is `Depth-first search`.


## Setup Instructions

1. Clone the project files from github

    `$ git clone https://github.com/nayan3090/Sudoku-Solver-Agent.git`


2. Use `environment.yaml` file in the project repository to setup the environment which includes several important packages that are used for the project. Open a terminal and run the following:
    `$ conda env create -f environment.yaml`


3. Activate the environment by running the following:
    
    *// For  conda 4.6 and later versions on Linux/macOS/Windows, use*
    `$ conda activate aind`
    *// For conda versions prior to 4.6 on Linux/macOS, use* 
    `$ source activate aind`
    *// For conda versions prior to 4.6 on Windows, use* 
    `$ activate aind`


4. You can run a small set of test cases using the local test suite. 

    `(aind)$ python -m unittest -v`


5. You can run the code with visualization (see the last section of the readme for more information)

    `(aind)$ python solution.py`


## Visualization

**Note:** The `pygame` library is required to visualize your solution -- however, the `pygame` module can be troublesome to install and configure. It should be installed by default with the AIND conda environment, but it is not reliable across all operating systems or versions. Please refer to the pygame documentation [here](http://www.pygame.org/download.shtml), or discuss among your peers in the slack group if you need help.

Running `python solution.py` will automatically attempt to visualize your solution, but you mustuse the provided `assign_value` function (defined in `utils.py`) to track the puzzle solution progress for reconstruction during visuzalization.
