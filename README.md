# Time Series Forecasting using Deep Learning

## Overview

This project focuses on predicting future values for a 7-variable time series using Deep Neural Networks. We experimented with various techniques, including LSTM, GRU, and Transformer-inspired models, to achieve high accuracy in time series forecasting.

## Dataset

- 68,528 samples of a multivariate time series
- 7 features: sponginess, wonder level, crunchiness, loudness on impact, meme creativity, soap slipperiness, and hype root
- Features are not normalized and range across different scales
- Periodic components observed through Fast Fourier Transform

## Key Features

- Data analysis and preparation
- Data augmentation with Gaussian noise
- LSTM and GRU models
- Transformer-inspired models (encoder-only, decoder-only, encoder-decoder)
- Hyperparameter search using keras_tuner

## Methods

### Data Preparation
- Dataset splitting (training, validation)
- Normalization of variables between 0 and 1
- Data augmentation with low variance Gaussian noise

### Models
- LSTM (simple and bidirectional)
- GRU
- Transformer-inspired models (encoder-only, decoder-only, encoder-decoder)

### Training
- Cross-validation via hold-out
- Sliding window approach
- Experimentation with window size, stride, and telescope values
- Teacher forcing (for transformer models with decoders)

## Results

Best performing models on remote test data:

| Model                         | RMSE   |
|-------------------------------|--------|
| Transformer (encoder only)    | 3.6866 |
| LSTM model                    | 3.8241 |
| GRU model                     | 3.9163 |

## Conclusions

Simpler models generally led to better results for this dataset. Bidirectional models didn't show benefits for LSTM and GRU. For transformer-inspired models, fewer encoder stacks were more successful due to quicker training time.

## Tools Used

- TensorFlow
- Keras
- keras_tuner

## Authors

- Marco Domenico Buttiglione
- Luca De Martini
- Giulia Forasassi

Politecnico di Milano

## Date

January 21, 2022

---

For more detailed information about the methodology, experiments, and findings, please refer to the full project report.
