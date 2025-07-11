# Housing Optimisation Project

This repository presents a mathematical optimisation model designed to assist real estate developers in the Netherlands in configuring profitable, regulation-compliant residential towers. The model was developed for the Advanced Analytics for a Better World (AABW) course and is capable of evaluating various floor configurations, owner assignments, and sector allocations to maximise profit under a strict set of constraints.

## Repository Structure
```
Housing_Optimisation/
├── Housing optimisation.ipynb # Main Jupyter notebook with model implementation
├── Housing_Optimisation_overview.pdf # Initial case brief and introduction
├── Housing_Optimisation_detailed_description.pdf # Full list of constraints and requirements
├── Housing_Optimisation_parameter_values.xlsx # Input data: floor designs, sectors, owners, profits
├── Housing Optimisation Report.pdf # Final report summarising results and recommendations
├── README.md # This file
```


## Model Objective

To determine the most profitable building configuration in terms of:
- Number of floors
- Floor layout (from a predefined set of 2-sector designs)
- Sector classification (social, middle, free)
- Owner allocation (corporation, investor, private)

The model selects a feasible floor configuration for each level in the building while adhering to all national and municipal housing constraints.

## Key Constraints

The model adheres to a range of real-world restrictions, including:
- Minimum % of affordable apartments (≥40% social, ≥40% middle)
- Minimum average apartment area per sector
- Owner-sector eligibility constraints (e.g., corporations can’t own “free” sector units)
- All units on a single floor must be assigned to the same owner
- Apartment sizes on higher floors must not be smaller than those on lower ones

For the full constraint list, see the [Housing_Optimisation_detailed_description.pdf](Housing_Optimisation_detailed_description.pdf) file.

## Approach

- Model implemented in Python using Gurobi to solve a mixed-integer programming problem.
- Predefined floor designs serve as atomic building blocks, avoiding the complexity of dynamically generating apartment layouts.
- Sector and owner assignments are determined through variable indexing and constraint-based filtering.
- Results can be adapted by relaxing specific constraints to evaluate different profitability scenarios.

## Results Summary

Optimal profit outcomes (with all constraints enforced):

| Tower Size | Profit        |
|------------|---------------|
| 23 floors  | €17.5 million |
| 40 floors  | €29.6 million |
| 56 floors  | €39.2 million |

By selectively relaxing constraints (e.g., raising the share of free-sector units), profits can increase by over 30%. For example:
- 23 floors → €23.2 million (32.5% increase)
- 56 floors → €52.2 million (33.2% increase)

Detailed allocation summaries and visual breakdowns are available in the [Housing Optimisation Report.pdf](Housing%20Optimisation%20Report.pdf).

## Files of Interest

- `Housing optimisation.ipynb`: Main optimisation script and result analysis.
- `Housing_Optimisation_parameter_values.xlsx`: Dataset used to populate model parameters (floor designs, profits, constraints).
- `Housing Optimisation Report.pdf`: Final stakeholder-ready write-up, including visual outputs and recommendations.

## Authors

Developed by:
- Neil Basson
- Domenica Valle


For the course *Advanced Analytics for a Better World* at the University of Amsterdam.

