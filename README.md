# Motion Prediction Algorithms for Autonomous Driving

This repository contains my efforts to explore several motion prediction methods for agents surrounding an ago self-driving car. Lyft's motion prediction database is used here and various functionalities of `l5kit` are used for data fetching and data processing.


## Algorithms

- [x] Approach 1: use a pretrained CNN (resnet) to predict 3 paths (n_timestep * 2) and their confidence (3) and use neg_multi_log_likelihood to get a loss.

- [x] Approach 2: similar to #1 but at the end of CNN encoder instead of fully connect to predict all points, use a GRU later to do so.

- [ ] Approach 3: several enhancements including increase hypothesis, sparse history frame, pallelize rasterization, train on full dataset, remove highly correlated samples (1/8th of samples for each agent), scheduler cosineannealing warmrestarts, gradient clipping, min_frame_history: 0 , Xceoption41, ensembling with set transformer.


## Results
The results after 10 epochs with each epoch 10,000 iterations is as follows:

| Algorithm        | Training Error   | Validation Error|
|:-------------:|:-------------:|:-------------:| 
| 1   | 17.85       | 16.50      | 
| 2   | 18.40       | 17.39      | 
| 3   | -      | -    | 




## Usage
Run the cells in the jupyter notebook motion_prediction.ipynb in the provided order.


## References
    

* https://www.kaggle.com/c7934597/lyft-complete-train-and-prediction-pipeline

* https://github.com/JerryIshihara/lyft-motion-prediction-for-autonomous-vehicle/

* https://github.com/asanakoy/kaggle-lyft-motion-prediction-av






