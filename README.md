# US Solar Resource Data

An R Markdown notebook that retrieves solar resource data for three US cities (New York, Los Angeles, and Austin) from the [National Renewable Energy Laboratory (NRL) API](https://developer.nlr.gov/docs/solar/solar-resource-v1/), and analyses solar viability and estimated rooftop solar savings by location.

## Research Question

If I install a 5kW rooftop solar panel in each city, how much energy would it generate per year, and which city offers the best financial return?

## Output

Monthly and annual analysis across three solar resource metrics:

- **avg_dni** – Direct Normal Irradiance
- **avg_ghi** – Global Horizontal Irradiance
- **avg_lat_tilt** – Average Latitude Tilt

Derived metrics include annual energy generation (kWh), estimated annual savings (USD), seasonality ratio, and number of viable solar months per city.

## Key Finding

Los Angeles generates the most solar energy (~1,737 kWh/year) but New York produces the second-highest annual savings (~$362) despite weaker irradiance, due to its high electricity price of 28.55¢/kWh. Electricity price is as important as solar resource when evaluating rooftop solar investment.

## Requirements

- R 4.0+
- The following R packages:
  - `tidyverse`
  - `httr`
  - `jsonlite`
  - `dotenv`
  - `kableExtra`

Install all at once:

```r
install.packages(c("tidyverse", "httr", "jsonlite", "dotenv", "kableExtra"))
```

## Setup

1. Clone the repository
2. Create a `.env` file in the project root with your NRL API key:

```
MY_API=your_api_key_here
```

You can get a free API key at [developer.nlr.gov](https://developer.nlr.gov).

3. Open `notebook.Rmd` in RStudio and knit to PDF.

## Adding More Locations

Locations are defined as a list in the setup chunk. To add a city, add an entry:

```r
list(name = "Chicago", lat = 41.88, lon = -87.63)
```

No other code changes are needed.

## Project Structure

```
├── notebook.Rmd   # Main analysis notebook
├── .env           # API key (not tracked in git)
└── .gitignore     # Excludes .env and other local files
```