# A2: Bias in Data

Frank Chen

## Goal

The goal of this project is to perform analysis by cleaning and merging two datasets. 

## Data sources used

To create these tables, we will draw from two data sources: 

* `page_data.csv` (141591 rows, 3 columns: page, country, rev_id)
* `WPDS_2018_data.csv` (414 rows, 2 columns: geography, population mid-2018 (in millions))

## Resources used

This analysis was prepared using Python 3.5 running in a Jupyter Notebook environment.

## Files Created

This notebook creates csv files of data extracted and compiled as part of this analysis.

The first file is `page_data_clean.csv`, which removes entries that begin with 'Template' in `page_data`. The second file is `WPDS_2018_data_clean.csv`, which removes the region names from the original dataset. The third file is `WPDS_2018_region_data.csv`, which is the extracted region file from the original dataset. The fourth file is `page_data_tmp.csv`, which is the `page_data` with correct column names and column order, prepared for merging. The fifth file is `unmerged_data.csv`, which is the leftover rows from `page_data` that were not successfully merged with the other dataset. The sixth file is `wp_wpds_politicians_by_country.csv`, which is the cleaned and merged csv file used for analysis.

## Visualizations Created

I created tables as per the specifications in the assignment wiki.

## Initial Reflection

This has been an interesting assignment that combines many aspects of data analysis, including: data cleaning and data transformation. The initial task of preparing both datasets for merging serves as a constant reminder that the datasets we often work with are not in the ideal format we'd like, so we need to spend time preparing them before we run any analysis. I found it interesting that our definition of 'coverage' is a proportion of articles per country with that country's population. I write more about this in the additional questions section, but I believe this may introduce a bias towards higher coverage for countries with low population. Perhaps the articles/population size could be normalized first, so we have a better representation of coverage.

## Additional Questions

**What biases did you expect to find in the data (before you started working with it), and why?**

Before I started working on the project, I expected to find English-speaking countries with more article entries and higher quality articles, because this is scrapped from the English wikipedia. 

**What (potential) sources of bias did you discover in the course of your data processing and analysis?**

In the course of data processing and analysis, I found that most non-English speaking countries did have less coverage, as the bottom coverage countries included India, China, and Indonesia. Interestingly, since we calculated coverage as a percentage of population, the top countries with most coverage have small populations, such as Tuvalu and Nauru. It seems like we also have a bias in how we defined _coverage_.

**What might your results suggest about (English) Wikipedia as a data source?**

The (English) Wikipedia is expected to contain more higher quality articles and more coverage in English-speaking countries and regions.

**What might your results suggest about the internet and global society in general?**

Wikipedia articles are written by people who have access to the Internet. Naturally, the countries with the highest quality articles are likely from developed areas where broadband Internet is omnipresent.

**Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?**

If we use this dataset to analyze how active the country's citizens are in documenting their political history, we may generate misleading conclusions for countries where the primary language is not English, and the country has entries about their political figures in other languages (China, for example).

**Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?**

This dataset could be useful when visualized as a tool to find political figures with high quality written articles about them.

**How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?**

If we redefine coverage to be adjusted for population size (normalizing the population data), then I would expect the developed, English-speaking countries to show up near the top 10.

## License

This assignment code is released under the MIT license.
