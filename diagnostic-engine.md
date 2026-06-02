# Diagnostic Engine: Organizational Sync-Stability™ Quantification Core

> **File Positioning**
>
> This file is the technical core of `governance-operating-system.md`.
>
> The board sees signals.
> Inside the engine runs the logic that generates those signals.
>
> This document defines **how to move from raw data to an Organizational Sync-Stability™ score**.
> It does not address response protocols. Response protocols are defined by the Governance Operating System.

---

## 1. Engine Architecture Overview

```txt

Raw Data Stream → Variable Normalization Module → Formula Computation Module → Signal Conversion Module → Threshold Trigger Module
↑ ↑ ↑ ↑ ↑
Multi-source Unified Core Algorithm Score Output Governance Signal
Ingestion Dimension

```
---


| Module | Function | Output |
| :--- | :--- | :--- |
| Variable Normalization Module | Unifies heterogeneous data into computable variables | ER, PR, RI, Acceleration Pressure (normalized values) |
| Formula Computation Module | Executes core formula operations | Raw Organizational Sync-Stability™ value |
| Signal Conversion Module | Maps raw value to a standardized interval | 0–100 standardized score |
| Threshold Trigger Module | Applies trend and threshold logic to standardized score | Governance signal (Green/Yellow/Orange/Red, trend alert) |

---

## 2. Variable Normalization Module

### 2.1 Variable Definitions and Data Sources

#### Execution Rhythm (ER)

| Dimension | Description |
| :--- | :--- |
| **Definition** | The structural rhythmic capacity of the organization to convert input into value output |
| **Positive Indicators** | Delivery cycle stability, cross-departmental collaboration completion rate, decision-to-execution loop speed |
| **Negative Indicators** | Project delay rate, priority-switching frequency index, backlog of unfulfilled commitments |
| **Recommended Data Sources** | Project management systems, OKR/KPI tracking systems, operational rhythm metadata |
| **Normalization Direction** | 0–1; higher values indicate healthier execution rhythm |

#### Pressure Regulation (PR)

| Dimension | Description |
| :--- | :--- |
| **Definition** | The capacity to perceive, absorb, and dissipate internal and external pressure without undergoing structural deformation |
| **Positive Indicators** | Pressure early-warning response speed, resource elastic reallocation capacity, pre-escalation conflict resolution rate |
| **Negative Indicators** | Critical node overload frequency, shortening of pressure-to-performance transmission time, number of cycles where pressure signals are ignored |
| **Recommended Data Sources** | HR systems, operational monitoring, employee pulse surveys, incident report timelines |
| **Normalization Direction** | 0–1; higher values indicate stronger pressure regulation capacity |

#### Recovery Integrity (RI)

| Dimension | Description |
| :--- | :--- |
| **Definition** | The existence, sufficiency, and protected status of organizational recovery windows |
| **Positive Indicators** | Regularity of recovery windows, proportion of uninterrupted recovery periods, magnitude of post-recovery performance rebound |
| **Negative Indicators** | Frequency of recovery window compression, length of continuous work cycles, actual leave utilization rate |
| **Recommended Data Sources** | Work intensity data, overtime records, meeting density trends, recovery compliance logs |
| **Normalization Direction** | 0–1; higher values indicate more complete recovery capacity |

#### Acceleration Pressure

| Dimension | Description |
| :--- | :--- |
| **Definition** | The resultant force of internal and external acceleration acting on the organization |
| **Positive Indicators** | Market rhythm acceleration, competitive intensity, internal change frequency and magnitude, target growth rate |
| **Negative Indicators** | (This variable itself is a pressure indicator; negative indicators represent pressure overload signals) |
| **Recommended Data Sources** | Strategic objective data, market intelligence, change logs, resource saturation monitoring |
| **Normalization Direction** | 0–1; higher values indicate greater acceleration pressure (positioned in the denominator of the formula) |

---

### 2.2 Normalization Method (Recommended)

Each variable is composed of multiple sub-indicators with weighted synthesis. Raw values are mapped to the 0–1 interval through normalization.

**General Normalization Formula** (applicable to indicators with historical baselines):

---

Normalized Value = (Current Value - Historical Minimum) / (Historical Maximum - Historical Minimum)

---

For inverse indicators (where higher values are worse), take the complement:

---

Normalized Value = 1 - [(Current Value - Historical Minimum) / (Historical Maximum - Historical Minimum)]

---


**Weighting Principles**:
- Use equal weighting or expert-assigned weights at initial deployment
- After four quarters of operation, perform statistical calibration based on the correlation between each sub-indicator and organizational stability events

---

## 3. Formula Computation Module

### 3.1 Core Formula (Computation Layer)

**Organizational Sync-Stability™ (Raw Value) = (ER × PR × RI) / Acceleration Pressure**

Where:

| Variable | Value Range | Description |
| :--- | :--- | :--- |
| Execution Rhythm | 0–1 | Execution Rhythm normalized value |
| Pressure Regulation | 0–1 | Pressure Regulation normalized value |
| Recovery Integrity | 0–1 | Recovery Integrity normalized value |
| Acceleration Pressure | 0.01–1 | Acceleration Pressure normalized value (minimum boundary set at 0.01 to prevent division by zero) |

### 3.2 Mathematical Intuition of the Formula

- **The numerator is the product of three variables**: If any single variable collapses, overall stability tends toward zero. This reflects the serial fragility of the system — execution, regulation, and recovery are all indispensable.
- **The denominator is Acceleration Pressure**: When acceleration pressure approaches zero (the organization is at rest), stability scores remain high even if the numerator is small. This aligns with physical intuition — a system at rest cannot become unstable.
- **Nonlinear characteristics**: When any of ER, PR, or RI approaches zero, the product effect amplifies the collapse. This is consistent with how real organizations fail suddenly.

---

## 4. Signal Conversion Module

### 4.1 Mapping Raw Values to 0–100 Standardized Scores

Raw values can theoretically float between 0 and extremely large values (when Acceleration Pressure is very small). A smoothing function is required to map them to a standardized interval.

**Recommended Mapping Function: Logarithmic Compression**

Standardized Score = 100 × [ln(1 + Raw Value) / ln(1 + Raw Value Benchmark Upper Limit)]


**Benchmark Upper Limit Setting**: Take the maximum raw value across the four historical quarters after deployment, or preset to 3.0 at initial deployment (corresponding to ER=1, PR=1, RI=1, Acceleration Pressure≈0.33).

### 4.2 Mapping Effect

| Raw Value | Approximate Standardized Score (Benchmark Upper Limit=3.0) |
| :--- | :--- |
| 0.00 | 0 |
| 0.50 | ~29 |
| 1.00 | ~50 |
| 2.00 | ~79 |
| 3.00 | 100 |

**This mapping ensures scores fall within 0–100 and possess intuitive readability.**

---

## 5. Threshold Trigger Module

### 5.1 Threshold Zone Definitions

| Standardized Score | Zone | Signal |
| :--- | :--- | :--- |
| 70–100 | Green Zone | Controlled Synchronization |
| 50–69 | Yellow Zone | Volatility Expansion |
| 30–49 | Orange Zone | Structural Risk |
| <30 | Red Zone | Collapse Acceleration |

---

### 5.2 Trend Trigger Logic

Trend detection is based on the percentage change between two consecutive data points (quarters):

Δ% = (Current Score - Previous Score) / Previous Score × 100%


| Condition | Signal |
| :--- | :--- |
| Δ% < -8% and > -15% | Yellow Alert |
| Δ% < -15% | Red Alert |

---

### 5.3 Trigger Output Format

When threshold or trend conditions are met, the engine outputs the following structure for consumption by the Governance Operating System:

```json
{
  "timestamp": "2026-Q2",
  "sync_stability_score": 47,
  "zone": "orange",
  "trend_delta_pct": -12.3,
  "alerts": [
    "red_alert: single-quarter decline exceeds 15%",
    "zone_trigger: entering orange zone"
  ],
  "variable_breakdown": {
    "er": 0.62,
    "pr": 0.58,
    "ri": 0.41,
    "acceleration_pressure": 0.71
  },
  "recommended_action": "freeze_non_core_growth_initiate_governance_intervention"
}

```
---

## 6. Calibration and Validation

### 6.1 Initial Deployment Calibration

Step	Content
1	Set sub-indicators and initial weights for each variable
2	Collect at least four quarters of historical data as baseline
3	Run the engine to generate retrospective scores
4	Compare against known organizational stability events (major failures, collective burnout, key personnel losses, etc.)
5	Adjust weights and mapping parameters so that engine output aligns closely with known events

---

### 6.2 Ongoing Calibration

Review weights every four quarters

Recalibrate after every major organizational restructuring

Update benchmark upper limit annually based on the latest data

---

## 7. Engine Boundary Statement

This engine explicitly does not include the following:

Does not include raw data collection systems (data ingestion is the responsibility of the deployment layer)

Does not include governance response protocols (response rules are defined in the Governance Operating System)

Does not include cross-organizational benchmarking (benchmarking is an independent module)

Does not include predictive functionality (this engine is descriptive/diagnostic, not predictive)

---

## 8. Version Information

Item	Content
File Version	v1.0
Release Date	2026-06-03
Parent System	Dual-Rhythm Architecture™
Companion File	governance-operating-system.md
License	CC BY-NC-ND 4.0

---

Domain: dualrhythmsystems.com

Domain: organizationalsyncstability.com

---

© 2026 Organizational Sync-Stability™ All rights reserved.
Founded by: Li Kuanxu (李宽续) | ORCID: 0009-0006-7346-3999

