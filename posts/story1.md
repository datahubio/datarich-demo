---
title: Global Temperature Trends Analysis
authors: [Jane Doe, John Smith]
date: "2023-11-30"
layout: blog
---

![[climate-change.jpeg]]

[Here is the source file on GitHub](https://github.com/datopian/datarich-demo/blob/main/posts/story1.md) used to render this page.

## Table of Contents

## Introduction

In this analysis, we explore the global temperature trends over the past century. Utilising historical temperature data, we aim to understand how the Earth's surface temperature has changed and identify patterns that might indicate future trends.

## Data Overview

Our dataset comprises Land-Ocean Temperature Index from 1880 to present sourced from [NASA GISS Surface Temperature Analysis](https://data.giss.nasa.gov/gistemp/).

<Table
	url="https://raw.githubusercontent.com/datopian/datarich-demo/main/data/land-ocean-global-means.csv"
/>

## Temperature Trends Over Time

The chart below visualises global yearly temperature means changes over the past century, highlighting the gradual increase.

<LineChart 
  data="https://raw.githubusercontent.com/datopian/datarich-demo/main/data/land-ocean-global-means.csv"
  title="Global Land-Ocean Annual Means"
  xAxis="Year"
  yAxis="J-D"
/>

## Conclusion

The data clearly indicates a significant rise in global temperatures over the past century. These trends, consistent with scientific research on climate change, underscore the urgency of addressing global warming.