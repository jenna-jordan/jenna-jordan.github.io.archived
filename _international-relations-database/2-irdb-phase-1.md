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

During my first semester, I took a [class on databases](/blog/my-classes-for-fall-2018#is490db-introduction-to-databases)  and a [class on python](/blog/my-classes-for-fall-2018#is452-foundations-of-information-processing). Both classes concluded with a final project of our own devising. I merged those two final projects into one: designing and creating the database that incorporated most of the Correlates of War Project datasets and then transforming and loading the data into the database using python.

For the database half of the project, I designed a database schema (and created the EER diagram), and then wrote a SQL script to create the database that contains, connects, and describes the disparate datasets published by the [Correlates of War project](http://www.correlatesofwar.org/). However, this only covers the creation of the tables and their referential integrity. The python half of the project involved writing scripts (using the Pandas library) to transform the CSV files into SQL insert statements. The transformation process ended up revealing several data quality issues, and the process of integrating the four War datasets was much more complicated than I initially thought.

Together, both sides of the project resulted in a Github repo that contains the necessary scripts to allow anyone to create and fill the database on their own machine.
