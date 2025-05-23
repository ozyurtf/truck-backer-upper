# Truck Backer Upper 

## Simulation Before Training 

<img src="videos/simulation-before-training.gif" width="75%" alt="Simulation After Training">

## Simulation After Training

<img src="videos/simulation-after-training.gif" width="75%" alt="Simulation After Training">

## Simulation Beyond Training Boundaries

<img src="videos/simulation-beyond-training.gif" width="75%" alt="Simulation After Training">

## First 10 Trajectories

![Trajectory 1](trajectories/lesson-11/trajectory-1.png)

![Trajectory 2](trajectories/lesson-11/trajectory-2.png)

![Trajectory 2](trajectories/lesson-11/trajectory-3.png)

![Trajectory 4](trajectories/lesson-11/trajectory-4.png)

![Trajectory 5](trajectories/lesson-11/trajectory-5.png)

![Trajectory 6](trajectories/lesson-11/trajectory-6.png)

![Trajectory 7](trajectories/lesson-11/trajectory-7.png)

![Trajectory 8](trajectories/lesson-11/trajectory-8.png)

![Trajectory 9](trajectories/lesson-11/trajectory-9.png)

![Trajectory 10](trajectories/lesson-11/trajectory-10.png)

## Run the Simulation

Create and activate the conda environment with:

```bash
conda env create -f conda_env.yaml
``` 

```bash
conda activate truck_backer_upper
```

To train the models, run:

```bash
python truck-backer-upper.py \
    --train_emulator True \
    --train_controller True \
    --final_cab_angle_range -90 90 \
    --final_cab_trailer_angle_diff_range -45 45 \
    --final_x_cab_range 10 35 \
    --final_y_cab_range -7 7 \
    --env_x_range 0 40 \
    --env_y_range -20 20 \
    --num_lessons 10 \
    --truck_speed -0.1 \
    --wandb_log False \
    --save_computational_graph False 
```

To test the models inside the training region, run:

```bash
python truck-backer-upper.py \
    --final_cab_angle_range -90 90 \
    --final_cab_trailer_angle_diff_range -45 45 \
    --truck_speed -0.1 \
```


To test the models outside the training region, run:

```bash
python truck-backer-upper.py \
    --final_cab_angle_range -90 90 \
    --final_cab_trailer_angle_diff_range -45 45 \
    --final_x_cab_range 70 100 \
    --final_y_cab_range -15 15 \
    --env_x_range 0 100 \
    --env_y_range -25 25 \
    --truck_speed -0.1 \
```