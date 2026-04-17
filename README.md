# Analysis of annual HIV Surveillance datasets from NYC Health Department — 01/2010 to 12/2024

This repository contains data, analytic code, and findings that support portions of the article, “[HIV Surveillance Annual Report, 2024](https://www.nyc.gov/assets/doh/downloads/pdf/dires/hiv-surveillance-annualreport-2024.pdf),” published December 2025. Please read that article, which contains important context and details, before proceeding.

## Data

This analysis uses fifteen spreadsheets.

The spreadsheets come from the following sources:

- Annual HIV Surveillance Reports from the NYC Health Department
  https://www.nyc.gov/site/doh/data/data-sets/hiv-aids-surveillance-and-epidemiology-reports.page

  The Tabula application was used to extract data from the surveillance reports and convert the data into csv files.

Each of the spreadsheets contain, among others, the following columns relevant to the analysis:

- `UHF NEIGHBORHOOD` — There are 42 United Heath Fund or UHF neighborhoods in NYC.  UHF neighborhoods were created by aggregating adjacent zip codes. UHF neighborhoods are used by the NYC Health Department for analysis of health outcomes citywide and local communities.
- `YEAR` — January 1/year to December 31/year
- 'HIV DIAGNOSES PER 100,000 POPULATION' - New HIV diagnoses during one year per 100,000 people in the specified borough or UHF neighborhood. Intercensal population were calculated by the NYC Health Department.
- 'AGE-ADJUSTED DEATH RATE OER 1,000 PEOPLE LIVING WITH HIV' - Number of deaths during one year among 1,000 people with HIV in the specified borough or UHF neighborhood. Age adjustment was based on the 2010 United States population.

## Methodology

The notebook [`HIV_project.ipynb`]()performs the following analyses:

##### Part 1: IMPORT AND CLEAN

- Each annual HIV surveillance data from 2010 to 2024 was imported as csv files
- Columns were standardized to upper case; string elements were removed from the datapoints to allow for analyses; evaluation that all null cells were absent from the two columns of interest, namely that of HIV incidence and HIV death rate


##### Part 2: MERGING DATASETS

- Each annual HIV surveillance dataset from 2010 to 2024 was merged into a single dataset called all_HIV

##### Part 3: SETTING UP, PERFORMING LINEAR REGRESSION ANALYSES AND CREATING SCATTER PLOTS
- Linear regression analyses were performed for each annual HIV surveillance dataset from 2010 to 2024 to visualize the relationship between HIV incidence and HIV death rate. The main objective was to identify outlier UHF neighborhoods, which may indicate disparities in HIV prevention, testing and treatment.

##### Part 4: SETTING UP, PERFORMING GROUPED ANALYSES AND CREATING GRAPHS
- The merged dataset, all_HIV, was analyzed to create a time trend of both HIV incidence by UHF neighborhood over time AND HIV death rate by UHF neighborhood over time. The 2024 HIV Surveillance Report from the NYC Health Department highlighted the increasing incidence of HIV citywide since 2020. This trend is in contrast to a steady decline in HIV incidence prior to 2020. This analysis identified the three UHF neighborhoods with the highest HIV incidence and highest HIV death rate during the latest year, 2024.

## Outputs

The notebook outputs scatterplots that depict the relationship between HIV incidence and HIV death rate by neighborhood per year.

The notebook also outputs graphs that depict HIV incidence by neighborhood over time and HIV death rates by neighborhood ober time.

## Running the analysis yourself

You can run the analysis yourself. To do so, you'll need the following installed on your computer:

- Python 3
- The Python libraries specified in [`requirements.txt`](requirements.txt)

## Licensing

All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). The data file in the output/ directory is available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license. All files in the data/ directory are released into the public domain.

## Feedback / Questions?

Contact Josephine Tsai at jtsaihelmond@gmail.com.
