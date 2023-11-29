---
title: "Climate Change: An Interactive Data Analysis"
authors: [Jane Doe, John Smith]
date: "2023-11-30"
layout: blog
---

![[climate-change.jpeg]]

In this document, we explore the concept of 'Data Rich Documents' by blending text analysis with data visualisations[^1].

[^1]: All the data was mocked.

[Here is the source GitHub](https://github.com/datopian/datarich-demo) repository with the markdown files and assets used to render this site.
## Table of Contents

## Global Temperature Trends

The `LineChart` component below visualises global temperature changes over the past decade, highlighting the gradual increase.

Here is how you can add the component in your markdown:

```jsx
<LineChart 
  data={[
    ['2010', 14.5],
    ['2011', 14.6],
    ['2012', 14.7],
    ['2013', 14.8],
    ['2014', 14.9],
    ['2015', 15.0],
    ['2016', 15.1],
    ['2017', 15.2],
    ['2018', 15.3],
    ['2019', 15.4]
  ]}
  title="Global Temperature Trends"
/>
```

And this is how it renders:

<LineChart 
  data={[
    ['2010', 14.5],
    ['2011', 14.6],
    ['2012', 14.7],
    ['2013', 14.8],
    ['2014', 14.9],
    ['2015', 15.0],
    ['2016', 15.1],
    ['2017', 15.2],
    ['2018', 15.3],
    ['2019', 15.4]
  ]}
  title="Global Temperature Trends"
/>

## CO2 Emissions by Country

Next, we analyse CO2 emissions using the `VegaLite` component. This visualisation shows emissions from different countries.

Here is how you can add the component in your markdown:

```jsx
<VegaLite
  data={{
    table: [
      { country: "USA", emissions: 5000 },
      { country: "China", emissions: 4800 },
      { country: "India", emissions: 2700 },
      { country: "Russia", emissions: 1700 },
      { country: "Japan", emissions: 1200 }
    ]
  }}
  spec={{
    $schema: "https://vega.github.io/schema/vega-lite/v4.json",
    mark: "bar",
    data: {
      name: "table"
    },
    width: 500,
    height: 200,
    encoding: {
      x: {
        field: "country", 
        type: "ordinal"
      },
      y: {
        field: "emissions",
        type: "quantitative"
      }
    }
  }}
/>
```

And this is how it renders:

<VegaLite
  data={{
    table: [
      { country: "USA", emissions: 5000 },
      { country: "China", emissions: 4800 },
      { country: "India", emissions: 2700 },
      { country: "Russia", emissions: 1700 },
      { country: "Japan", emissions: 1200 }
    ]
  }}
  spec={{
    $schema: "https://vega.github.io/schema/vega-lite/v4.json",
    mark: "bar",
    data: {
      name: "table"
    },
    width: 500,
    height: 200,
    encoding: {
      x: {
        field: "country", 
        type: "ordinal"
      },
      y: {
        field: "emissions",
        type: "quantitative"
      }
    }
  }}
/>

## Summary Statistics

The `Table` component presents a summary of average temperatures and CO2 emissions, showing how these metrics have evolved.

Here is how you can add the component in your markdown:

```jsx
<Table 
  cols={[
    { key: 'year', name: 'Year' },
    { key: 'avgTemperature', name: 'Avg Temperature' },
    { key: 'avgEmissions', name: 'Avg Emissions' }
  ]} 
  data={[
    { year: 2010, avgTemperature: 14.5, avgEmissions: 4000 },
    
    { year: 2015, avgTemperature: 15.0, avgEmissions: 4500 },
    { year: 2019, avgTemperature: 15.4, avgEmissions: 4700 }
  ]}
/>
```

And this is how it renders:

<Table 
  cols={[
    { key: 'year', name: 'Year' },
    { key: 'avgTemperature', name: 'Avg Temperature' },
    { key: 'avgEmissions', name: 'Avg Emissions' }
  ]} 
  data={[
    { year: 2010, avgTemperature: 14.5, avgEmissions: 4000 },
    { year: 2015, avgTemperature: 15.0, avgEmissions: 4500 },
    { year: 2019, avgTemperature: 15.4, avgEmissions: 4700 }
  ]}
/>

## Temperature anomalies

Finally, we incorporate external data through a `VegaLite` component, analysing temperature anomalies from a CSV file.

Here is how you can add the component in your markdown:

```jsx
<VegaLite
  spec={{
    $schema: "https://vega.github.io/schema/vega-lite/v5.json",
    data: {
      url: "https://raw.githubusercontent.com/datopian/datarich-demo/main/demo.csv",
    },
    width: 600,
    height: 250,
    mark: "line",
    encoding: {
      x: { field: "Time", type: "temporal" },
      y: { field: "Anomaly (deg C)", type: "quantitative" },
      tooltip: { field: "Anomaly (deg C)", type: "quantitative" },
    },
  }}
/>
```

And this is how it renders:

<VegaLite
  spec={{
    $schema: "https://vega.github.io/schema/vega-lite/v5.json",
    data: {
      url: "https://raw.githubusercontent.com/datopian/datarich-demo/main/demo.csv",
    },
    width: 600,
    height: 250,
    mark: "line",
    encoding: {
      x: { field: "Time", type: "temporal" },
      y: { field: "Anomaly (deg C)", type: "quantitative" },
      tooltip: { field: "Anomaly (deg C)", type: "quantitative" },
    },
  }}
/>

## Conclusion

Through this exploration, we see how 'Data Rich Documents' enable a seamless integration of narrative and data, offering interactive insights into complex topics like climate change.
