---
title: "IRDB: Phase 1"
permalink: /projects/irdb-phase-1
excerpt: "The first phase of this project focused on combining the main CoW datasets into a relational database. I started this project during the Fall 2018 semester, and finished in Spring 2019."
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
---

During my first semester, I am taking a [class on databases](/blog/my-classes-for-fall-2018#is490db-introduction-to-databases)  and a [class on python](/blog/my-classes-for-fall-2018#is452-foundations-of-information-processing). Both classes conclude with a final project of our own devising. I have merged those two final projects into one: creating the database and then loading it with the appropriate data.

For the database side of the project, I will write a SQL script to create a database that contains, connects, and describes the disparate datasets published by the [Correlates of War project](http://www.correlatesofwar.org/). However, this only covers the creation of the tables and their referential integrity. The python side of the project will involve writing scripts to transform .csv files into SQL insert statements.

Together, both sides of the project will result in a Github project repo that contains the necessary scripts to allow anyone to create and fill the database on their own machine. I plan to incorporate proper attribution, metadata, and meaningful context drawn from the codebooks into the database, as well as include SQL scripts for example views that transform the complex database back into the tabular form political scientists are used to for analytical work.
