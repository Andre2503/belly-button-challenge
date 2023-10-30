# belly-button-challenge

The Belly Button Biodiversity Dashboard is an interactive web application that visualizes the microbial species (also called operational taxonomic units, or OTUs) found in the navel of different individuals.

## Repository Structure

```plaintext
belly-button-challenge/
│
├── Read Me (This file)
├── samples.json (dataset sampple)
│
└── static/
    └── js/
        └── app.js (logic for data extraction and visualization)
```

## Features

### 1. **Dropdown Menu for Sample Selection**

Users can select a sample from the dropdown menu, which will dynamically update all the visualizations on the page.

### 2. **Horizontal Bar Chart**

- Represents the top 10 OTUs found in the selected individual.
- Uses `sample_values` for bar values.
- Uses `otu_ids` for bar labels.
- Provides `otu_labels` as the hovertext.

### 3. **Bubble Chart**

- Visualizes OTU data for the selected sample.
- `sample_values` define the y-axis and marker sizes.
- `otu_ids` determine the x-axis and marker colors.
- `otu_labels` are used for hovertext.

### 4. **Demographic Information Panel**

Displays the metadata corresponding to the selected sample, including details such as ethnicity, gender, age, location, bbtype, and washing frequency (`wfreq`).

### 5. **Interactive Updates**

All visualizations on the page update in real-time when a different sample is selected from the dropdown.

## Methodology

- **Fetching Data:** The dataset is fetched from [this URL](https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.1/14-Interactive-Web-Visualizations/02-Homework/samples.json) using D3.js.

- **Data Extraction:** Within `app.js`, functions extract data arrays for `sample_values`, `otu_ids`, and `otu_labels` using the `.map` method on the dataset. This data powers the visualizations.

- **Populating Dropdown:** The dropdown menu is populated with the sample IDs from the dataset, allowing users to select different samples.

- **Bar Chart:** The `plotBarChart` function creates a horizontal bar chart for the top 10 OTUs in the selected sample.

- **Bubble Chart:** The `plotBubbleChart` function crafts a bubble chart where each marker represents an OTU.

- **Metadata Display:** The `displayMetadata` function appends the selected sample's metadata to a designated panel on the web page.

- **Real-time Updates:** The `optionChanged` function ensures that when a new sample is selected from the dropdown, all visualizations and metadata displays update accordingly.

## Deployment

The Belly Button Biodiversity Dashboard is deployed on GitHub Pages. Check it out [here](https://andre2503.github.io/belly-button-challenge/).

## Links

- [GitHub Repository](https://github.com/andre2503/belly-button-challenge)
- [Live Demo on GitHub Pages](https://andre2503.github.io/belly-button-challenge/)

## Disclosure 
GPT4 assisted with the formating of this Readme File. 
The js was not working until GPT4 provided the line `window.optionChanged = optionChanged` to ensure the optionChanged was globally accesible. 
