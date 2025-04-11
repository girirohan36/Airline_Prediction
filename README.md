# Airline Prediction

## Overview

This project tackles the challenge of **airline ticket pricing and overbooking** through a dynamic programming approach combined with **forward simulation**. The aim is to develop pricing strategies and overbooking policies that **maximize expected revenue** while balancing the cost of passenger disruptions.

By modeling ticket sales over a full year (365 days), this solution provides actionable insights on overbooking thresholds, customer no-shows, pricing strategies, and risk mitigation.

## Objective

Maximize total profit across a 365-day booking window by:
- Strategically overbooking coach seats while managing bump costs.
- Pricing coach and first-class tickets optimally each day.
- Incorporating seasonality and behavioral probabilities into decisions.
- Evaluating policies through simulation to understand trade-offs.


## Model Breakdown

- **State Variables**: Days remaining, coach seats sold, first-class seats sold.
- **Actions**: Daily pricing choices for coach ($300/$350) and first-class ($425/$500).
- **Probabilistic Components**:
  - Sale likelihood varies with price and availability.
  - Passenger show-up rates: 95% for coach, 97% for FC.
- **Objective**: Maximize discounted revenue, accounting for overbooking costs.

---

## Key Features

### 1. Value Function with Dynamic Programming
- Optimizes over a 3D space: time, coach sold, FC sold.
- Uses **backward recursion** and memoization.
- Evaluates every price combination and stochastic outcome.

### 2. Overbooking Analysis
- Tests multiple overbooking caps (0–20 seats).
- Considers coach-to-FC upgrades and bump penalties.
- Recommends optimal level based on revenue risk-reward tradeoff.

### 3. Simulation Engine
- Forward simulates ticket sales under given policies.
- Tracks profit, bump count, terminal penalties, ticket sales, and show-ups.
- Validates DP results with real-world randomized scenarios.

### 4. Seasonality Effect
- Adds realism to model by adjusting sale probabilities over time.
- Reflects booking spikes near departure.
- Captures its impact on overbooking decisions.


