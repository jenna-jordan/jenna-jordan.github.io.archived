---
title: "IRDB: Phase 1"
permalink: /projects/irdb-phase-1
excerpt: "This project assembles together various projects that collect data on international relations (i.e. Correlates of War, ICOW, Polity IV) into one cohesive relational database. The GitHub repo contains the database schema, the original CSV files, and python scripts for transforming those CSV files into tables for the database."
header:
  image: /assets/images/project_irdbhome.jpg
  #teaser: assets/images/unsplash-gallery-image-1-th.jpg
sidebar:
  - title: Project Name
    text: "International Relations Database (IRDB)"
    #image:
  - title: "Description"
    text: "Phase 1 of the IRDB involves designing a relational database for the Correlates of War datasets and writing python scripts to transform the available datasets into SQL insert statements."
  - title: "Relevant Classes"
    text: "Fall 2018: [IS452](/tags/#is452), [IS490DB](/tags/#is490db)"
  - title: "Github Repo"
    text: "[international-relations-database](https://github.com/jenna-jordan/international-relations-database)"
gallery:
  - url: /assets/images/unsplash-gallery-image-1.jpg
    image_path: assets/images/unsplash-gallery-image-1-th.jpg
    alt: "placeholder image 1"
  - url: /assets/images/unsplash-gallery-image-2.jpg
    image_path: assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
  - url: /assets/images/unsplash-gallery-image-3.jpg
    image_path: assets/images/unsplash-gallery-image-3-th.jpg
    alt: "placeholder image 3"
---

During my first semester, I am taking a [class on databases](/blog/my-classes-for-fall-2018#is490db-introduction-to-databases)  and a [class on python](/blog/my-classes-for-fall-2018#is452-foundations-of-information-processing). Both classes conclude with a final project of our own devising. I have merged those two final projects into one: creating the database and then loading it with the appropriate data.

For the database side of the project, I will write a SQL script to create a database that contains, connects, and describes the disparate datasets published by the [Correlates of War project](http://www.correlatesofwar.org/). However, this only covers the creation of the tables and their referential integrity. The python side of the project will involve writing scripts to transform .csv files into SQL insert statements.

Together, both sides of the project will result in a Github project repo that contains the necessary scripts to allow anyone to create and fill the database on their own machine. I plan to incorporate proper attribution, metadata, and meaningful context drawn from the codebooks into the database, as well as include SQL scripts for example views that transform the complex database back into the tabular form political scientists are used to for analytical work.

<!--{% include gallery caption="This is a sample gallery." %}-->
