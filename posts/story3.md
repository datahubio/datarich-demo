---
layout: datapackage
frictionless:
  name: dataset-abc
  title: Dataset ABC
  resources:
  - dpp:streaming: true
    encoding: utf-8
    format: csv
    mediatype: text/csv
    name: dataset-abc
    path: dataset-abc.csv
    profile: tabular-data-resource
    title: Dataset ABC
    schema:
      fields:
      - format: any
        name: Date
        type: date
      - format: default
        name: Value
        type: number
      missingValues:
      - ''
  views:
  - name: graph
    spec:
      series:
      - Value
      type: line
    specType: simple
    title: Dataset ABC
---

## Some extra content

Here is some extra content written in the body of this markdown file.