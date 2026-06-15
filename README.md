# New York Solar Resource Data

An R Markdown notebook that retrieves solar resource data for New York from the [National Renewable Energy Laboratory (NRL) API](https://developer.nlr.gov/docs/solar/solar-resource-v1/) and visualises monthly averages.

## Output

Monthly averages for three solar resource metrics:

- **avg_dni** – Direct Normal Irradiance
- **avg_ghi** – Global Horizontal Irradiance
- **avg_lat_tilt** – Average Latitude Tilt

## Requirements

- R 4.0+
- The following R packages:
  - `tidyverse`
  - `httr`
  - `jsonlite`
  - `dotenv`

Install all at once:

```r
install.packages(c("tidyverse", "httr", "jsonlite", "dotenv"))
```

## Setup

1. Clone the repository
2. Create a `.env` file in the project root with your NRL API key:

```
MY_API=your_api_key_here # no quotation marks
```

You can get a free API key at [developer.nlr.gov](https://developer.nlr.gov).

3. Open `notebook.Rmd` in RStudio and knit to HTML or PDF.

## Project Structure

```
├── notebook.Rmd   # Main analysis notebook
├── .env           # API key (not tracked in git)
└── .gitignore     # Excludes .env and other local files
```