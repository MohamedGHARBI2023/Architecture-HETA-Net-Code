# Architecture-HETA-Net-Code
This repository contains the pseudocode and the needed data to reproduce the experiments.

1. Event Table Construction
Goal: Convert heterogeneous clinical tables into a unified chronological event table with aligned dependency scores.
Input
Patients table (P)
Diagnoses table (D)
CCAM procedures table (C)
Clinical notes table (N)
Dependency scores table (S)
Output
Event table (E) with dependency score y aligned to each event.

2. Sequence Preparation
Goal: Convert the event table into temporal patient sequences ready for model training.
Input
Event table (E) with features and aligned dependency score y.
Output
Patient sequences {Xp, Yp} suitable for batching and padding.


3. Temporal Model Architecture
Goal: Predict the next dependency score and detect score change events from patient event sequences.
Input
Batch of padded sequences with pad_mask
Current score y_curr at each timestep
Output
y_hat (predicted next score)
delta (predicted score change)
change_logit (probability of score change)
