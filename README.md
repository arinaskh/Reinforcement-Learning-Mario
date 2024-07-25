## Project Overview
### Topic: Training a Reinforcement Learning agent to Play Mario game

### Team Members:
- Arina Sadeghi Khiabanian
- Maxence Murat

### Instructor: Andrea Asperti

### Course: Deep Learning, 3-Credit Project

## Project Files
- **main.py**: The main loop managing interactions between the environment and Mario.
- **Mariometrics.py**: Includes a `MetricLogger` to track training and evaluation performance.
- **replay.py**: Used to evaluate a trained Mario model.
- **Marioagent.py**: Defines how the agent collects experiences, selects actions based on observations, and updates its action policy.
- **Mariowrappers.py**: Contains logic for environment preprocessing, such as resizing observations and converting RGB to grayscale.
- **neural.py**: Defines Q-value estimators using a convolutional neural network.



## project overview
we uploaded two different videos of mario in our repository that see it's performance before and after training


## Setup Instructions
To set up this project, we utilized Ubuntu to create a new environment named *mario*. Follow these steps to run the project:

1. Install [conda](https://www.anaconda.com/products/individual).
2. Install the necessary dependencies using `environment.yml`:
    ```sh
    conda env create -f environment.yml
    ```
    Ensure that the *mario* environment is [successfully created](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file).

3. Activate the *mario* environment:
    ```sh
    conda activate mario
    ```

## File Descriptions
### Learning Process
To initiate the training process for Mario, execute:
```sh
python main.py
```
This command starts the double Q-learning algorithm and logs key training metrics to the `checkpoints` directory. Additionally, a copy of `MarioNet` and the current exploration rate will be saved. If a GPU is available, it will be used automatically. Training takes approximately 80 hours on a CPU and 20 hours on a GPU.

### Evaluation
To evaluate a trained Mario model, run:
```sh
python replay.py
```
This will display Mario playing the game in a window and log performance metrics to a new folder within `checkpoints`. To load a specific checkpoint, update the `load_dir` parameter in `Mario.load()` with the desired timestamp, such as `checkpoints/2020-06-06T22-00-00`.


