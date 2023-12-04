# Tutorial: Publishing a Frictionless Dataset on Datahub (or Flowershow Cloud ❓❓❓)

In this tutorial we are going to cover how you can publish a Frictionless Dataset on DataHub.

## What is a Frictionless dataset

A Frictionless dataset, in this context, is a Data Package as specified in the Frictionless specification. This means we will create a dataset using the battle-tested Data Package specification, push it to GitHub, and render an impressive presentation for it on Datahub. You can read more about the specification [here](https://specs.frictionlessdata.io/guides/data-package/).

Without further ado, let's start building the Datahub project.

## Steps

### Create a GitHub repository

In order to render the Frictionless Dataset on Datahub, we first have to create a GitHub repo for it. You can give it the name you want, just make sure that the repo is public.

You can also use a repository your created in the [[datarich-tutorial|previous tutorial]].)

### Create a markdown file with Data Package metadata in the frontmatter

Create a new markdown file in your repo and add the following frontmatter to it:

```md
---

---
```

Note the "views" property in the above file. It determines what gets rendered in the visualisations section on DataHub. You can read more about Frictionless Views [here](https://specs.frictionlessdata.io/views/#specification). Currently, DataHub supports only line charts with the "simple" specType, but you can add other visualisations to the document in the README section using the LineChart, Vega, VegaLite, and Table components.

Also, note that the `group` and `series` properties point to fields in the resource specified above. You can change that to modify the chart behavior.

Since we are specifying a resource in the `datapackage.json` file, we also have to add the actual resource file to the repo. Create a `data` folder and inside it create a `vix-daily.csv` file with the following content:

```csv
Date,VIX Open,VIX High,VIX Low,VIX Close
2018-09-10,15.09,15.20,13.93,14.16
2018-09-11,13.96,14.92,13.21,13.22
2018-09-12,13.07,13.86,12.91,13.14
2018-09-13,12.91,12.91,12.30,12.37
2018-09-14,12.13,13.15,11.93,12.07
2018-09-17,12.72,13.75,12.32,13.68
2018-09-18,13.48,13.48,12.56,12.79
2018-09-19,12.61,12.77,11.66,11.75
2018-09-20,11.82,11.96,11.31,11.80
2018-09-21,11.76,12.03,11.10,11.68
2018-09-24,12.46,12.92,12.18,12.20
2018-09-25,12.28,12.60,11.80,12.42
2018-09-26,12.21,13.13,11.55,12.89
2018-09-27,12.77,13.00,11.94,12.41
2018-09-28,12.59,13.22,12.09,12.12
2018-10-01,11.99,12.40,11.57,12.00
2018-10-02,12.47,12.69,11.61,12.05
2018-10-03,11.66,12.14,11.34,11.61
2018-10-04,12.84,15.84,12.42,14.22
2018-10-05,14.29,17.36,11.72,14.82
2018-10-08,16.05,18.38,15.69,15.69
2018-10-09,16.12,17.49,15.27,15.95
2018-10-10,16.03,22.96,15.83,22.96
2018-10-11,23.07,28.84,20.65,24.98
2018-10-12,21.63,26.80,20.88,21.31
2018-10-15,21.97,22.89,19.47,21.30
2018-10-16,20.28,20.56,17.55,17.62
2018-10-17,17.06,19.55,17.06,17.40
```

You can push those two files we created to the repo and we are good to go. Now, let's create the README.md file.

## Push a README.md file to the repo

Create a README.md and add the following content to it.

```markdown 
CBOE Volatility Index (VIX) time-series dataset including daily open, close, high and low. The CBOE Volatility Index (VIX) is a key measure of market expectations of near-term volatility conveyed by S&P 500 stock index option prices introduced in 1993.

## Daily chart

<FrictionlessView viewId={0} />

```

Note that we are now using the `FrictionlessView` data component. This data component renders views specified on the `datapackage.json` file by index. You can also make this component full width by setting the `fullWidth` property:

```jsx
<FrictionlessView fullWidth viewId={0} />
```

Push this file to the repo and move to the next step.

## Go to the URL

The repo is ready, it's time to see how it looks on DataHub. Replace `{owner}` with your GitHub organization or user id and `{project}` with the name of the repo on the following URL and access it:

demo.datahub.io/@{'{'}owner{'}'}/{'{'}project{'}'}

If everything is right, your project should look similar to this one: https://demo.datahub.io/@datahubio/tutorial-frictionless-project-demo

___

Feel free to get in contact with us and let us know what you think : ).