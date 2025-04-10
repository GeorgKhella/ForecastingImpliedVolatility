# Forecasting Implied Volatility using Nelson-Siegel

**Author:** Georg Khella  
**Date:** March 2025

## 📈 Overview

This project adapts the **Nelson-Siegel model**, commonly used for interest rates, to forecast the **term structure of implied volatility** derived from American option prices.  
Using these forecasts, the strategy generates trading signals for **VIX futures** or enables **delta hedging** in derivative portfolios.

## 🧠 Methodology

- Estimate implied volatility curves using **market option prices**
- Fit the **Nelson-Siegel model**:  
  σ(τ) = β₀ + β₁ * ((1 - e^(−τ/λ)) / (τ/λ)) + β₂ * (((1 - e^(−τ/λ)) / (τ/λ)) − e^(−τ/λ))
- Forecast β₀, β₁, β₂ using **AR(1) time-series models**
- Predict future implied volatility σ̂(τ)

## 📊 Trading Strategy

- **VIX Futures Rule**:
  - Buy if forecast σ̂ > 1.05 × current σ
  - Short if forecast σ̂ < 0.95 × current σ
- **Delta Hedging Alternative**:
  - Adjust ∆ exposure based on volatility predictions to maintain delta-neutrality

## 🔬 Tools & Models

- Implied volatility from **Black-Scholes inversion**
- **OLS** for parameter estimation
- Grid search for optimal λ in Nelson-Siegel
- **AR models** for coefficient forecasting

## 📁 Files

- `Forecasting_Implied_Volatility.pdf`: Full report with mathematical modeling, trading strategy, and references

## 📚 References

- Black & Scholes (1973) – Option pricing theory  
- Nelson & Siegel (1987) – Yield curve modeling  
- Diebold & Li (2006) – Term structure forecasting  
- Hull (2000), Bakshi et al. (2000) – Option pricing frameworks
