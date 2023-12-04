# Tutorial: Publishing Data-Rich Documents on DataHub

Hi, welcome to DataHub. In this tutorial, we are going to cover the basics of publishing a data-rich document.

## But wait, what is a data-rich document?

A data-rich document is one in which the writer can easily mix formatted text content with data visualizations. This means that you don't have to code or embed your charts and tables; they can be added to the document with a very simple syntax, either by passing inline data or simply referencing your data files. What you end up with is a plain text, human-readable document that is simple to edit and looks awesome when rendered in DataHub!

## What does this syntax look like?

The structure and text formatting of the documents are created with markdown (take a look at [this guide](https://www.datopian.com/playbook/markdown) to learn more about markdown). But it's not just markdown; it's markdown on steroids: writers are capable of easily adding tables of contents, mathematical formulas, data visualizations, and more!

And guess what? What you are reading right now is a data-rich document powered by DataHub, that's why we can do this:

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

You can check out the full source of the data-rich document you are reading [here](https://github.com/datahubio/tutorial).

More on how to create charts and tables later, but now, this must be coming from somewhere, right?

## What is a DataHub project?

A DataHub project is simply a GitHub repo with a README and, potentially, data files. That's right: you can take advantage of everything that GitHub offers in terms of versioning, change history, and so on, and transform your repo into a data-rich document.

Imagine how cool it would be to store your reports, datasets, and analysis in this format. Now, let's learn how to actually do it.

## Steps

### Create a GitHub repo

First, create a repo under your organization or user in GitHub. DataHub currently does not support private repos, so make sure this new repo is public and that your main branch is named "main" (updates on this coming soon).

### Push a README.md file to the repo

Now, create a README.md file. In this file, feel free to use anything that markdown has to offer. For this tutorial, we are going to use the following basic structure:

```markdown
# Personal Annual Costs

This document tracks my personal annual costs.

## Table

## Chart
```

### Add tables

Let's add a table to the README file. There are different ways to specify the data that's going to be displayed in the table.

You can specify `data` and `cols`, like this:

```
<Table cols={[
    { key: 'id', name: 'ID' },
    { key: 'firstName', name: 'First name' },
    { key: 'lastName', name: 'Last name' },
    { key: 'age', name: 'Age' }
  ]} data={[
    { id: 1, lastName: 'Snow', firstName: 'Jon', age: 35 },
    { id: 2, lastName: 'Lannister', firstName: 'Cersei', age: 42 },
    { id: 3, lastName: 'Lannister', firstName: 'Jaime', age: 45 },
    { id: 4, lastName: 'Stark', firstName: 'Arya', age: 16 },
    { id: 7, lastName: 'Clifford', firstName: 'Ferrara', age: 44 },
    { id: 8, lastName: 'Frances', firstName: 'Rossini', age: 36 },
    { id: 9, lastName: 'Roxie', firstName: 'Harvey', age: 65 },
  ]}
/>
```

Or you can pass inline CSV data to the table:

```
<Table csv={`
Year,Temp Anomaly
1850,-0.418
2020,0.923
`} />
```

Or you can specify a url to a CSV file, which can be a relative link to a file in your repo (e.g `data.csv`) or an external URL:

```
<Table url='data.csv' />
```

For this tutorial, let's go with the second option, so, under the `## Table` header in your file, add the following snippet:

```
<Table csv={`
Year,Cost
2018,50345.50
2019,65272.20
2020,48413.80
2021,76213.50
2022,71653.60
`} />
```

Here's what it's going to look like:

<Table csv={`
Year,Cost
2018,50345.50
2019,65272.20
2020,48413.80
2021,76213.50
2022,71653.60
`} />

Note that tables can also be made full width by setting the `fullWidth` property:

```
<Table fullWidth csv={`
Year,Cost
2018,50345.50
2019,65272.20
2020,48413.80
2021,76213.50
2022,71653.60
`} />
```

Check out how this looks when rendered:

<Table fullWidth csv={`
Year,Cost
2018,50345.50
2019,65272.20
2020,48413.80
2021,76213.50
2022,71653.60
`} />

### Add graphs

Now, let's add a graph to the README file. There's a variety of ways to create charts in DataHub.

For charts that demand more customization, the Vega and VegaLite components can be used:

```
<VegaLite data={ { "table": [
      {
        "y": -0.418,
        "x": 1850
      },
      {
        "y": 0.923,
        "x": 2020
      }
      ]
    }
  } spec={
    {
      "$schema": "https://vega.github.io/schema/vega-lite/v4.json",
      "mark": "bar",
      "data": {
          "name": "table"
      },
      "encoding": {
          "x": {
              "field": "x",
              "type": "ordinal"
          },
          "y": {
              "field": "y",
              "type": "quantitative"
          }
      }
    }
  } />
```

To keep it simple, we are going to use the LineChart component on this tutorial. Add the following snippet to your README file under the `## Chart` header:

```
<LineChart data={
    [
        ["2018",50345.50],
        ["2019",65272.20],
        ["2020",48413.80],
        ["2021",76213.50],
        ["2022",71653.60]
    ]
  }
  />
```

This is what it will look like when rendered:

<LineChart data={
    [
        ["2018",50345.50],
        ["2019",65272.20],
        ["2020",48413.80],
        ["2021",76213.50],
        ["2022",71653.60]
    ]
  }
/>

And, just like with tables, line charts can also be made full width. Check out how this same line chart looks with the `fullWidth` property:

<LineChart fullWidth data={
    [
        ["2018",50345.50],
        ["2019",65272.20],
        ["2020",48413.80],
        ["2021",76213.50],
        ["2022",71653.60]
    ]
  }
/>
  

### Final document

At this point, your document should look like this:

```markdown
# Personal annual costs

This is the tracking of my personal annual costs.

## Table

<Table csv={`
Year,Cost
2018,50345.50
2019,65272.20
2020,48413.80
2021,76213.50
2022,71653.60
`} />

## Chart

<LineChart data={
    [
        ["2018",50345.50],
        ["2019",65272.20],
        ["2020",48413.80],
        ["2021",76213.50],
        ["2022",71653.60]
    ]
  }
/>

```

We now have a README file ready to be used on DataHub. Let's visualize our creation.

### Go to your project's page on DataHub

It's time to check the results. To do that, edit the following URL, replacing `{owner}` with your user or org ID and `{project}` with the name of your repo:

demo.datahub.io/@{'{'}owner{'}'}/{'{'}project{'}'}

Finally, access the URL.

___

Cool, isn't it? Get in contact with us and let us know what you think!
