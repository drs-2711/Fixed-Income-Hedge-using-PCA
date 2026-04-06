# Fixed Income Portfolio Hedging Using PCA

## Overview
This project develops a quantitative framework to hedge a fixed income portfolio against yield curve risk using Principal Component Analysis (PCA). Instead of modeling interest rate risk as a single factor, the approach captures movements across the entire yield curve and decomposes them into a small number of systematic components.

## Objective
The goal is to identify the primary drivers of yield curve movements, measure a portfolio’s exposure to these drivers, and construct a hedge that neutralizes these risks.

## Data
Daily U.S. Treasury yield data was obtained from the Federal Reserve Economic Data (FRED) database for the following maturities:
- 2-year
- 5-year
- 10-year
- 20-year
- 30-year

The dataset spans from 2010 to 2024. Daily changes in yields were computed and standardized prior to analysis.

## Methodology

### PCA Decomposition
Principal Component Analysis was applied to daily yield changes to extract the main factors driving yield curve movements. These factors represent:
- Level (parallel shifts)
- Slope (steepening/flattening)
- Curvature (shape changes)

### Portfolio Construction
A fixed income portfolio was constructed as a long position in a 20-year Treasury bond.

### Factor Exposure
The portfolio’s exposure to each PCA factor was calculated by projecting its maturity profile onto the factor loadings.

### Hedging Framework
A hedge was constructed using a set of Treasury securities with different maturities. A system of linear equations was formulated to offset the portfolio’s exposure to each factor. The system was solved to determine the required hedge ratios.

## Tools and Libraries
- Python
- pandas
- numpy
- scikit-learn
- matplotlib
- pandas-datareader