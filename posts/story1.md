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

Our dataset comprises yearly average temperatures from 1920 to 2020, sourced from global meteorological organisations. The data reflects the mean surface temperature changes relative to the 20th-century average.

<Table url="https://raw.githubusercontent.com/datopian/datarich-demo/main/land-ocean-global-means.csv" />

## Temperature Trends Over Time

The chart below visualises global average temperature changes over the past century, highlighting the gradual increase.

<LineChart 
  data="https://raw.githubusercontent.com/datopian/datarich-demo/main/land-ocean-global-means.csv"
  title="Global Land-Ocean Annual Means"
  xAxis="Year"
  yAxis="J-D"
/>

## Geographical Temperature Anomalies Distribution

This map illustrates temperature anomalies by region for the year 2020.

## Conclusion

The data clearly indicates a significant rise in global temperatures over the past century. These trends, consistent with scientific research on climate change, underscore the urgency of addressing global warming.