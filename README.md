# DataRich Documents Demo

Welcome to DataRich Documents Demo!

👉 [[tutorial|Check our tutorial to learn how to create and publish DataRich documents]]

👉 [[story1|See example data analysis of climate change]]

👉 [[reference|Features reference page]]

## But wait, what is a DataRich document?

A DataRich document is one in which the writer can easily mix formatted text content with data visualisations. This means that you don't have to code or embed your charts and tables; they can be added to the document with a very simple syntax, either by passing inline data or simply referencing your data files. What you end up with is a plain text, human-readable document enriched with data visualisations, that is simple to edit and looks awesome when rendered in DataHub (or Flowershow Cloud ❓❓❓)!

## What does this syntax look like?

The structure and text formatting of the documents are created with markdown (take a look at [this guide](https://www.datopian.com/playbook/markdown) to learn more about markdown). But it's not just markdown; it's markdown on steroids: writers are capable of easily adding tables of contents, mathematical formulas, data visualisations, and more!

And guess what? What you are reading right now is a DataRich document powered by DataHub (or Flowershow Cloud ❓❓❓). That's why we can do this:

<LineChart data={
    [
      ["1850",-0.41765878],
      ["1851",-0.2333498],
      ["1852",-0.22939907],
      ["1853",-0.27035445],
      ["1854",-0.29163003]
    ]
} />

Awesome, right? Even more awesome is that this chart is created by simply having the following snippet in this document:

```
<LineChart data={
    [
      ["1850",-0.41765878],
      ["1851",-0.2333498],
      ["1852",-0.22939907],
      ["1853",-0.27035445],
      ["1854",-0.29163003]
    ]
} />
```

You can check out the full source of the data-rich document you are reading [here](https://github.com/datopian/datarich-demo).

More on available features and components in this [[reference|reference page]].

## What is a DataRich site?

A DataRich site is simply a GitHub repository with some DataRich and/or plain markdown documents, published with DataHub (or Flowershow Cloud ❓❓❓). That's right: you can take advantage of everything that GitHub offers in terms of versioning, change history, and so on, and transform your repo into a DataRich site in a few clicks.

More on how to create your own DataRich sites in [[tutorial|this tutorial]].
