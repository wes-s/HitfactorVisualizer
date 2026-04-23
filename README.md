# Hitfactor USPSA Visualizer

A browser-based tool for analyzing USPSA shooter performance using
classifier scores and ELO history. This app focuses on accurate,
transparent calculation of classification percentages using raw hit
factor data instead of relying on rounded API values.

## Key Features

### 📊 Classifier Analysis

-   Visualizes classifier HHF % over time
-   Computes **true USPSA classification percentage** using:
    -   Latest 8 valid classifiers
    -   Best 6 of those 8
-   Automatically handles:
    -   Duplicate classifiers (keeps most recent)
    -   Thrown-out lowest scores
    -   Manual exclusions

### 🎯 Accurate Calculations

-   Uses **raw hit factor / HHF × 100** when available
-   Avoids API rounding issues (2-decimal truncation)
-   Maintains precision through all calculations

### 📈 ELO History

-   Displays shooter ELO rating trends over time
-   Includes prediction and peak tracking

### 🔮 What-If Analysis

-   Calculates required average classifier % to reach next
    classification
-   Simulates future classifier performance impact

### ✍️ Manual Score Entry

-   Add provisional classifier scores
-   Immediately updates rankings and projections

### 📥 CSV Export

Download a shooter's classifier history with: - `classifier_date` -
`classifier_inclusion_code` - `classifier_pct_of_hhf` -
`current_calculated_classification_pct` - `classifier_code`

#### Inclusion Codes

-   `v` → valid
-   `f` → lowest two thrown out
-   `m` → duplicate/superseded
-   `mi` → manually excluded

### 🔗 Shareable Views

URL state includes: - Selected shooters/divisions - Date filters -
Manual exclusions - Manual scores

## How Classification Is Calculated

1.  Group classifiers by code\
2.  Keep the most recent per classifier\
3.  Take the most recent 8 unique classifiers\
4.  Select the best 6\
5.  Average those 6

Minimum requirement: **4 valid classifiers**

## Technical Notes

### Precision

HHF % is calculated as:

    (hitfactor / hhf) * 100

-   Full precision internally
-   4 decimal display/export

### Built With

-   Vanilla JS
-   D3.js

## Usage

1.  Enter shooter\
2.  Select division\
3.  Add\
4.  Analyze

## Known Limitations

-   Depends on availability of raw hitfactor + HHF
-   Falls back to API % if missing
-   No persistence beyond URL
