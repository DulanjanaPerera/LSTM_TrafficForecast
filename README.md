# Time Series Forecasting with LSTM

This repository contains a Long Short-Term Memory (LSTM) model implemented in Python for traffic volume forecasting. The project utilizes historical traffic data with multiple features, including temperature, rain volume, snow volume, and cloud coverage, to predict future traffic volume at a 3-hour interval.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Hyperparameter Tuning](#hyperparameter-tuning)
- [Training and Evaluation](#training-and-evaluation)
- [Usage](#usage)
- [Results](#results)
- [Project Structure](#project-structure)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

Traffic volume prediction is a crucial task in urban planning and transportation management. This project explores the use of LSTM networks, a type of recurrent neural network (RNN), to model and predict traffic volume based on past data and external conditions.

## Dataset

The dataset consists of time-series data recorded at 1-hour intervals from October 2012 to October 2018. The target variable is **traffic volume**, and the predictor variables include:

- Temperature
- Rainfall (1-hour volume)
- Snowfall (1-hour volume)
- Cloud coverage
- Datetime information (converted into sinusoidal features for periodic representation)

## Preprocessing

The preprocessing steps include:

1. **Handling Missing Values**: Missing numerical values are replaced with the mean.
2. **Normalization**: All numerical variables are normalized to zero mean.
3. **Feature Engineering**: The datetime variable is transformed into sinusoidal features to maintain periodic behavior.
4. **Data Splitting**: The dataset is split into training, validation, and test sets.

## Model Architecture

The LSTM model consists of:

- Input layer
- Multiple LSTM layers (2-4 layers evaluated)
- Dropout layers for regularization
- Dense output layer with a single neuron for traffic volume prediction

## Hyperparameter Tuning

Several experiments were conducted to tune hyperparameters such as:

- **Batch Size**: Smaller batch sizes resulted in better performance.
- **Number of LSTM Layers**: A 4-layer LSTM model provided the best results.
- **Dropout Rate**: A dropout of 0.2 improved generalization.
- **Statefulness**: Enabled stateful LSTMs to capture long-term dependencies.

## Training and Evaluation

- The model was trained for **20 epochs**, after which performance plateaued.
- The best model was selected based on the lowest validation loss.
- Evaluation metrics:
  - **Mean Absolute Error (MAE)**: Achieved **0.1242** (normalized scale)
  - **Leaderboard Score**: The best model obtained **245.16** on the public leaderboard.

## Usage

1. **Run the Jupyter Notebook**
   ```bash
   jupyter notebook time_series_notebook_DulanjanaPerera.ipynb
   ```
2. **Modify hyperparameters and retrain**
   - Open `time_series_notebook_DulanjanaPerera.ipynb` and update model configurations.

## Results

- The trained LSTM model successfully predicts traffic volume with low error.
- The best-performing model used **4 LSTM layers with 64 nodes each, dropout of 0.2, and batch size of 9**.
- The introduction of statefulness slightly improved performance.

## Project Structure

- `time_series_notebook_DulanjanaPerera.ipynb`: Main notebook for data processing, model training, and evaluation.
- `CSC578-FinalProject-DulanjanaPerera.pdf`: Final project report detailing methodology and results.
- `README.md`: Project documentation.

## License

This project is released under the MIT License.

## Acknowledgments

This project was developed as part of the CSC 578 Final Project at Texas A&M University. Special thanks to the instructors and peers for their valuable insights.

---

For further details, refer to the [Final Project Report](CSC578-FinalProject-DulanjanaPerera.pdf).

