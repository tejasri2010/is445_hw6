# Bigfoot Sightings Dataset Visualisations
*Submitted By Tejasri Joshi(tajoshi2@illinois.edu)*


## Visualization 1: Bigfoot Sightings Over Time (Filtered by State)

<!-- Embed the JSON chart for  Bigfoot Sightings Over Time -->
<div id="vis1"></div>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  // Load the JSON specification for Visualization 1
  vegaEmbed('#vis1', 'line_chart.json').catch(console.error);
</script>

**Writeup:**


This line chart shows how Bigfoot sightings have changed over time, allowing users to focus on trends for individual states. Each data point represents the total number of sightings recorded in a specific month, grouped by state. By adding a dropdown filter, users can select a specific state and view its trend over time without being overwhelmed by data from other states. This interactive element makes the visualization more personalized and insightful.

For the design, I chose a line chart because it is effective for showing changes over continuous time periods. The x-axis encodes time (year_month) as a temporal variable, while the y-axis encodes the count of sightings as a quantitative variable. I used color to differentiate states, but the dropdown ensures only one state is displayed at a time, reducing clutter and making the chart easier to interpret. Tooltips provide additional details for each data point, such as the state, date, and number of sightings, enhancing user exploration.

In the data preparation stage, I extracted the year and month from the date column and converted them into a year_month format to capture monthly trends. Compared to the earlier homework, where I visualized annual sightings using a bar chart, this visualization provides more granular insights and uses interactivity to let users explore trends for different states. Altair's selection_point feature was used to implement the dropdown interactivity, allowing users to filter by state and focus on relevant data.

## Visualization 2: Bigfoot Sightings by Moon Phase and Precipitation Probability (State Filtered)
<!-- Embed the JSON chart for Bigfoot Sightings by Moon Phase and Precipitation Probability  -->
<div id="vis2"></div>

<script>
  // Load the JSON specification for Visualization 2
  vegaEmbed('#vis2', 'heatmap.json').catch(console.error);
</script>

**Writeup:**

This heatmap explores the relationship between Bigfoot sightings, moon phases, and precipitation probability, filtered by state. The chart uses the x-axis to represent moon phases as a nominal variable and the y-axis to show precipitation probability as a quantitative variable. The color of each cell encodes the number of sightings, with darker shades indicating higher counts. Users can select a state from a dropdown to focus on specific regions, making it easier to identify patterns or anomalies.

I chose a heatmap because it effectively shows relationships between multiple variables and highlights areas with higher or lower counts. For the color scheme, I used Viridis, a perceptually uniform palette that is colorblind-friendly and works well for quantitative data. The tooltip feature provides detailed information for each cell, including the state, moon phase, precipitation probability, and number of sightings, helping users understand the exact values behind the visual patterns.

On the analysis side, I grouped the dataset by state, moon_phase, and precip_probability to calculate the total number of sightings for each combination. This is a departure from the earlier homework, which primarily focused on state-level and yearly aggregates. The addition of moon phase and precipitation probability allows for a richer analysis of environmental factors potentially associated with sightings.

The interactivity, implemented using Altair's selection_point, enables users to filter the heatmap by state. This makes the visualization more insightful, as users can isolate data for specific regions instead of viewing all states at once. This approach introduces both new variables and a new chart type, making the analysis deeper and more versatile.

#### Resources

- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)
- [The Analysis](https://github.com/tejasri2010/is445_hw6/blob/main/Workbook.ipynb)