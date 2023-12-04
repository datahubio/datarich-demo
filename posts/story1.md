---
title: Global Temperature Trends Analysis
authors: [Jane Doe, John Smith]
date: "2023-11-30"
layout: blog
---

![[climate-change.jpeg]]

[Here is the source GitHub](https://github.com/datopian/datarich-demo) repository with the markdown files and assets used to render this site.

## Table of Contents

## Introduction

In this analysis, we explore the global temperature trends over the past century. Utilising historical temperature data, we aim to understand how the Earth's climate has changed and identify patterns that might indicate future trends.

## Data Overview

Our dataset comprises yearly average temperatures from 1920 to 2020, sourced from global meteorological organizations. The data reflects the mean surface temperature changes relative to the 20th-century average.

## Temperature Trends Over Time

The chart below visualises global average temperature changes over the past century, highlighting the gradual increase.

<LineChart 
  data="https://raw.githubusercontent.com/datopian/datarich-demo/main/land-ocean-global-means.csv"
  title="Global Land-Ocean Annual Means"
  xAxis="Year"
  yAxis="Mean"
  fullWidth="true"
/>

## Geographical Temperature Anomalies Distribution

This map illustrates temperature anomalies by region for the year 2020.

<OpenLayers data={temperatureByRegion2020} />

## Detailed Analysis

This interactive element allows for a deeper dive into specific years or regions, providing a comprehensive view of global temperature changes.

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

The data clearly indicates a significant rise in global temperatures over the past century. These trends, consistent with scientific research on climate change, underscore the urgency of addressing global warming.