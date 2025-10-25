
# RGA-TrafficNet: A Traffic Prediction System

This project is a novel traffic prediction model, **RGA-TrafficNet (RNN-GNN Attention Traffic Network)**. Its goal is to provide highly accurate, real-time traffic predictions by effectively combining Recurrent Neural Networks (RNNs) and Graph Neural Networks (GNNs).  

This model is designed to overcome the challenges faced by existing methods, which often struggle to capture complex temporal dynamics (patterns over time) and spatial relationships (how roads connect).  

## Key Features

* **Hybrid Model:** Combines RNNs to understand temporal traffic patterns and GNNs to handle spatial dependencies between roads.
* **Attention Mechanism:** Uses an attention mechanism to focus on the most relevant road segments or time steps, improving accuracy.
* **Multimodal Data Fusion:** Integrates various real-time data sources to improve predictions:
    * Live traffic feeds
    * Weather data from the OpenWeather API
    * Point of Interest (POI) data (e.g., malls, schools) to account for local traffic generators
* **Uncertainty Quantification:** Implements Monte Carlo Dropout to measure the model's confidence in its predictions. This provides an uncertainty score along with the forecast.

## How It Works: The Workflow

The model follows these steps to generate predictions:

1. **Data Collection:** The system gathers real-time data, including weather conditions and POI information.
2. **Preprocessing:** All data is cleaned, normalized, and structured to fit the model's input format. POI data is encoded into the graph structure.
3. **Temporal Modeling (RNN):** The preprocessed time-series data is fed into the RNN component to model sequential traffic patterns.
4. **Spatial Modeling (GNN):** The GNN component processes the road network as a graph, capturing spatial dependencies between different locations.
5. **Attention Layer:** The attention mechanism is applied to weigh the most critical time steps and locations more heavily.
6. **Monte Carlo Dropout:** Dropout is applied during the prediction phase to estimate uncertainty.
7. **Prediction Output:** The model combines the outputs to deliver a final real-time traffic prediction, complete with an uncertainty measure.

## Models Compared

This project develops the RGA-TrafficNet model and compares it against two existing models:

* **Recurrent Neural Network (RNN):** A class of networks designed for processing sequential data, like time-series. They use a hidden state to store information from previous steps, capturing temporal dependencies.
* **Graph Neural Network (GNN):** A class of networks that process data represented as graphs. They are used for tasks like node classification and link prediction.
* **RGA-TrafficNet (Proposed Model):** The novel model that integrates RNNs, GNNs, Attention, and Monte Carlo Dropout for a more accurate and reliable traffic forecast.
