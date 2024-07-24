## How to set up this project?
 First we used ubunto to make a new environment(mario) for this project.In able to run this project you should:

1. Install [conda](https://www.anaconda.com/products/individual)
2. Install dependencies with `environment.yml`
    ```
    conda env create -f environment.yml
    ```
    Check the new environment *mario* is [created successfully](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file).

3. Activate *mario* enviroment
    ```
    conda activate myenv
    ```

## Running
To start the **learning** process for Mario,
```
python main.py
```
This starts the *double Q-learning* and logs key training metrics to `checkpoints`. In addition, a copy of `MarioNet` and current exploration rate will be saved.

GPU will automatically be used if available. Training time is around 80 hours on CPU and 20 hours on GPU.

To **evaluate** a trained Mario,
```
python replay.py
```
This visualizes Mario playing the game in a window. Performance metrics will be logged to a new folder under `checkpoints`. Change the `load_dir`, e.g. `checkpoints/2020-06-06T22-00-00`, in `Mario.load()` to check a specific timestamp.


## Project Structure
**Mario_main.py**
Main loop between Environment and Mario

**Mario_agent.py**
Define how the agent collects experiences, makes actions given observations and updates the action policy.

**Mario_wrappers.py**
Environment pre-processing logics, including observation resizing, rgb to grayscale, etc.

**Mario_neural.py**
Define Q-value estimators backed by a convolution neural network.

**Mario_metrics.py**
Define a `MetricLogger` that helps track training/evaluation performance.

**Mario_replay.py**
To evaluate a trained Mario we use this file.

## Key Metrics

- Episode: current episode
- Step: total number of steps Mario played
- Epsilon: current exploration rate
- MeanReward: moving average of episode reward in past 100 episodes
- MeanLength: moving average of episode length in past 100 episodes
- MeanLoss: moving average of step loss in past 100 episodes
- MeanQValue: moving average of step Q value (predicted) in past 100 episodes


