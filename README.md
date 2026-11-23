# Brown Dwarf Temperature-Color Relationship Analysis

## What does it do?
This code analyzes the relationship between age, color, and temperature for a population of brown dwarfs using data from the UltraCoolSheet. The goal is to investigate how the temperature–color relationship varies across different age groups when using two different temperature-estimation methods, atmospheric and evolutionary models.

---

## How does it work?

1. Two CSV datasets containing photometric, age, and temperature measurements are loaded into Pandas DataFrames.
2. The data sets are cleaned. Rows with missing values are removed, and the datasets are matched using object names, resulting in a sample of 1,040 brown dwarfs.
3. The K-band magnitude is subtracted from the J-band magnitude to obtain a color measurement (J-K).
4. Objects are divided into three age groups: young (0–2 Gyr), middle-aged (2–4 Gyr), and old (over 4 Gyr).
5. Quintic polynomial functions are fitted to the temperature-color relationships for each age group using both atmospheric and evolutionary temperature measurements.
6. 1,000 random samples of 300 objects are selected from the middle-aged population. A polynomial fit is generated for each sample to create distributions of possible curve coefficients.
7. Z-scores are calculated to measure differences between the age-group curve coefficients and the Monte Carlo distributions.

---

## Results

The results found that the temperature-color relationship varies between age groups when using the atmospheric model, as compared to using the evolutionary model. 

The Monte Carlo analysis produced the following average Z-scores:

| Temperature Model | Average Z-score |
|---|---:|
| Evolutionary | 1.54 |
| Atmospheric | 2.38 |

These scores represent 

## How to use

1. Clone or download this repository.
2. Open `BrownDwarf_Temp_Color.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
3. Make sure both CSV datasets are available in the notebook's working directory.
4. Run the notebook cells in order.

## Files

- `BrownDwarf_Temp_Color.ipynb` — Main analysis notebook.
- `UltracoolSheetMain.csv` — Source data containing age and photometric measurements.
- `UltracoolSheet_FundamentalProperties.csv` — Source data containing atmospheric and evolutionary temperature measurements.
- `EmmaStoudemire_Project3Paper.pdf` — Written project paper.
