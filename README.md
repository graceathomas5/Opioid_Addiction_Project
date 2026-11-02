# Analysis of Medicare Part D buprenorphine prescribers, 01/2013 to 12/2024

## Data
This analysis uses spreadsheets, one per year, from 2013-2024 scraped from the Centers for Medicare & Medicaid Services' [Medicare Part D Prescribers by Provider and Drug](https://data.cms.gov/provider-summary-by-type-of-service/medicare-part-d-prescribers/medicare-part-d-prescribers-by-provider-and-drug) dataset.

Relevant columns:
- `Prscrbr_NPI`: unique ID for each prescriber
- `Prscrbr_Type`: prescriber's specialty
- `Prscrbr_State_Abrvtn`: prescriber's state
- `Brnd_Name`: brand name of the drug
- `Gnrc_Name`: generic name of the drug
- `Tot_Clms`: total Medicare Part D claims, including refills
- `year`: year of the data (added by me)

## Methodology
[`notebooks/Assignment1.ipynb`](notebooks/Assignment1.ipynb) is the analysis.

### Part 1: Scraping
Used the CMS API to download every row where the generic drug name contains "Buprenorphine," saving one CSV per year (394,269 rows in total).

### Part 2: Cleaning
Combined the years, removed products usually for pain (Butrans, Belbuca, Buprenex and generic buprenorphine patches) based on brand name, leaving 289,146 rows, and labeled prescribers as NP or PA.

### Part 3: Analysis
Calculated prescriptions and share by prescriber group and year, compared NP share for addiction products, and calculated each group's share of growth from 2016 to 2024.

### Limitations
The data covers Medicare Part D only. It excludes prescribers with fewer than 11 claims for a product in a year.

## Outputs
The notebook produces a spreadsheet of prescriptions and shares by prescriber group and year: (output/np_pa_prescriptions_by_year.csv).


## Running the analysis yourself
You can run the analysis yourself. To do so, you'll need the following installed on your computer:

Python 3
The Python libraries specified in requirements.txt

## Licensing
Code is under the MIT License. The output data file is under CC BY 4.0. Files in `data/` are in the public domain.

## Feedback / Questions?
Grace Thomas, grace.thomas02@journalism.cuny.edu
