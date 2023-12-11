# DataRich Documents Demo

Welcome to DataRich Documents Demo!

**Tutorials**:

👨‍🎓 [[datarich-tutorial|Publish data-rich stories with DataHub]]

👨‍🎓 [[frictionless-tutorial|Publishing datasets made simple with DataHub - just push a CSV + README to GitHub]]

**Demo pages:**

👀 [[story1|Data-rich story example]]

👀 [[story2|Dataset example]]

## But wait, what is a DataRich document?

![[data-rich-document.png]]

A data-rich document is just a classic markdown document but with some superpowers to make data storytelling and analysis easy to do.

And so, in data-rich document the writer can easily mix formatted text content with data visualisations. This means that you don't have to code or embed your charts and tables; they can be added to the document with a very simple syntax, either by passing inline data or simply referencing your data files. What you end up with is a plain text, human-readable document enriched with data visualisations, that is simple to edit and looks awesome when published with DataHub.

## What does the syntax look like?

The structure and text formatting of the documents are created with simple markdown. But it's not just markdown; it's markdown on steroids: writers are capable of easily adding tables of contents, mathematical formulas, data visualisations, and more!

And guess what? What you are reading right now is just his kind of data-rich document with rendering powered by DataHub. That's why we can do this:

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

For a full list of supported markdown features visit https://flowershow.app/docs/syntax

For a full list and API of available data visualisation components visit https://storybook.portaljs.org/?path=/docs/components-table--docs
