---
title: "IRDB: Phase 2"
permalink: /projects/irdb-phase-2
excerpt: "The second phase of this project focused on integrating the Correlates of War datasets with the UCDP/PRIO Armed Conflict dataset, the Polity IV dataset, the World Bank World Development Indicators, and CShapes. I worked on this project in Fall 2019 for the iSchool class Open Data Mashups."
header:
  image: /assets/images/project_irdbhome.jpg
  #teaser: assets/images/unsplash-gallery-image-1-th.jpg
sidebar:
  - title: Project Name
    text: "International Relations Database (IRDB)"
    #image:
  - title: "Description"
    text: "Phase 2 of the IRDB resulted in a country-year time series with variables drawn from the Correlates of War, UCDP/PRIO Armed Conflict, Polity IV, and the World Bank World Development Indicators."
  - title: "Relevant Classes"
    text: "Fall 2019: [IS590OM](/tags/#is590OM)"
  - title: "Github Repo"
    text: "[international-relations-database-extended](https://github.com/jenna-jordan/international-relations-database-extended)"
---

During my third semester, I took a project-based class called [Open Data Mashups](/blog/my-classes-for-fall-2019#is590om-open-data-mashups). The goal of this class was to produce a new dataset that integrated open data from 3-5 distinct sources, all while learning about project management, data management & curation, data provenance, reproducible workflows, version control, copyright & attribution, project & dataset documentation, and more.

I chose to expand upon my existing work with the Correlates of War datasets by integrating in other datasets commonly used by Peace/Conflict researchers: the UCDP/PRIO Armed Conflict dataset, the Polity IV dataset, the World Bank World Development Indicators dataset, and CShapes (historical country shape-files). When possible, I wrote scripts to acquire the data via API (UCDP/PRIO Armed Conflict, World Bank WDI). When needed, I normalized (3rd normal form) the datasets so they could be more easily manipulated (Correlates of War, UCDP/PRIO Armed Conflict). Some of the datasets were already in country-year format and didn't require too much wrangling (Polity IV, World Bank WDI).

One of the main challenges for this project was the fact that all 4 datasets used different country identifier schemes. CoW used their own CoW codes, UCDP/PRIO used the Gleditsch & Ward (G&W) codes, Polity IV used a version of the CoW codes that had been expanded, and the WorldBank used codes primarily based on the ISO 3-character country code standard. In order to connect these 4 similar but distinct schemas, I used Prof. Vincent Arel-Bundock's R package "countrycode". However, upon further investigation of the country-year panel dataset, I found several errors that I would need to correct in order to best integrate the 4 datasets.

The final product of this project is a country-year dataset (1946-2018) that includes variables from 2 datasets that separately track war and armed conflict (CoW & UCDP/PRIO), 1 dataset that tracks how autocratic/democratic a government is (Polity IV), and 1 dataset that tracks a wide variety of development indicators. Also included are the identifiers for historical country shape-files (CShapes) to more easily enable visualization.
