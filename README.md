# CACIITG-Summer-Analytics-Capstone-Project
# Dynamic Pricing for Urban Parking Lots  
*Summer Analytics 2025 - Capstone Project*  

This repository contains a machine learning solution for dynamically pricing urban parking spaces based on occupancy, queue length, local congestion, vehicle type, and competitor prices. Developed for the Summer Analytics Capstone, the project demonstrates data-driven pricing that adjusts in real time to balance parking demand and availability.

## 🚀 Problem Statement

Urban parking is in high demand but pricing is often static, causing overcrowding or under-utilisation. This project designs a real-time pricing engine that sets optimal parking rates dynamically.

## 💻 Tech Stack

- **Python** (core language)  
- **Pandas / Numpy** (data handling)  
- **Pathway** (streaming data ingestion)  
- **Bokeh** (real-time data visualisation)  
- **Google Colab** (execution environment)

## ⚙️ Architecture Flow

1. **Data Ingestion**  
   - Streaming data from `dataset.csv` using Pathway
   - Schema-based parsing of occupancy, vehicle type, congestion etc.

2. **Preprocessing & Feature Engineering**  
   - Normalise and clean fields
   - Encode vehicle types
   - Handle missing data

3. **Pricing Models**  
   - **Model 1**: Baseline Linear, adjusting price as occupancy grows  
   - **Model 2**: Demand-based function considering queue length, congestion, special days  
   - **Model 3**: Competitive pricing, factoring in nearby competitor prices and distance

4. **Real-time Prediction**  
   - Pathway processes the stream in event time  
   - Pricing logic runs on each event  
   - Emits new prices to Bokeh dashboard

5. **Visualisation**  
   - Bokeh provides interactive plots of pricing over time  
   - Helps monitor pricing behaviour

## 🏗️ Architecture Diagram

     +-------------------+
     |   User Vehicle    |
     +---------+---------+
               |
               v
    +----------------------------+
    |  Pathway Streaming Engine  |
    +----------------------------+
               |
               v
    +----------------------------+
    |   Preprocessing & Features |
    +----------------------------+
               |
               v
    +----------------------------+
    |   ML Pricing Logic         |
    |   (Baseline / Demand /     |
    |    Competitive)            |
    +----------------------------+
               |
               v
    +----------------------------+
    |   Bokeh Visualisation      |
    +----------------------------+
               |
               v
        Dynamic Pricing Display

