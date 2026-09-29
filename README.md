# CM2015 Programming with Data - University of London

Coursework for **CM2015 Programming with Data** (BSc Computer Science, University of London). The project is an end-to-end data analysis in Python: acquire data from Kaggle and by **web scraping**, clean and merge it, and answer a research question with visualisations.

| Assessment | Project | Key topics |
|---|---|---|
| Mid Term | Local vs global car brands in India | Web scraping, data cleaning, merging datasets, visualisation, data ethics |

**Tech:** Python · pandas · requests · BeautifulSoup · Matplotlib · Seaborn · Jupyter

---

## Local vs Global Car Brands in India's Used Car Market

**Research question:** how does Indian buyers' choice between **local and global car brands** in the used car market relate to **global car production trends**?

### Data sources
1. **Used cars in India** (Kaggle, about 9,500 listings): brand, model, year, age, km driven, transmission, fuel type, and asking price
2. **Global car production by country:** **web scraped** with `requests` + `BeautifulSoup`

### Pipeline
- **Cleaning:** handled missing `kmDriven` values, converted price text to numbers, dropped irrelevant columns, and used lambda functions for transformations
- **Feature engineering:** each brand classified as **Local** or **Global** and mapped to its country of origin
- **Merging:** combined the two datasets on brand country, so every listing carries its home country's production volume
- **Ethics:** covered data provenance and licensing, attribution, bias, and responsible interpretation

### Key findings
- **Global brands lead the listings:** 61.7% of used cars are from global brands and 38.3% from local ones
- **Maruti Suzuki is the single most listed brand** (2,720 cars), so local brands win on affordability
- **Fuel:** diesel (40.1%) and petrol (39.9%) are almost level. Hybrids make up 20%.
- **Transmission:** manual and automatic are about equal overall, but global brands lean automatic while local brands offer more manuals
- **Trend over time:** local brand listings grew strongly after 2014, and both categories dropped in 2020–21 (COVID-19)
- **Production vs price:** correlation of **−0.01**, so a country's global production volume has no meaningful effect on used car prices in India

### Visualisations
Count plots, pie charts, violin plots (car age by category), box plots (price by region), stacked bar charts, line plots over time, and a correlation analysis.

---

## How to run

```bash
pip install -r requirements.txt
jupyter notebook
```
Download the Kaggle used car CSV into the midterm folder. The production data is scraped live when you run the notebook.
