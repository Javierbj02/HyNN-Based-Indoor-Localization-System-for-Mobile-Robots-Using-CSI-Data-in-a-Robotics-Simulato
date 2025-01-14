## Integration into a Simulation Procedure

In order to do the evaluation of the proposal, through different experiments, it is neccesary to follow the following steps:

1. Reconstruct the real scenario in the simulator, maintaining the cartesian coordinates used in the real environment to create the fingerprint. This step is done in Webots by the creation of the world (.wbt), adding the objects and adjusting their positions in the world to recreate the real scenario.

<div>
<p align = "center">
<img src="test_world_1.png" width="500">
</p>
</div>

2. Launch the simulation in order to obtain the robot positions along the experiments, which follow a predefined path each one.

3. Associate the CSI readings (from full-data dataset) to that route positions.

[Associate CSI Readings](CSI_data_to_route_pos.ipynb)

4. Subsample the route positions to match the model predicition rate (predictions per seconds or frames per seconds). By this way, the robot will not do all the predictions of all the positions of the route (since in the simulator is possible), doing just by some of them, in accordance of frames per seconds.

[Subsampling](subsampling.ipynb)

5. Apply Gaussian noise to the CSI data, obtaining different noise level scenarios.

[Gaussian noise](apply_noise.ipynb)

6. Launch the experiments, for different noise levels and different number of antennas, studying the integration of the Kalman filter or not.

[Run experiments](../src/test_cases_kalman_filter/test_cases_kalman_filter/run_experiments.py)