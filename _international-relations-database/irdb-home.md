---
title: "IRDB Home"
permalink: /projects/irdb-home
excerpt: "Final project for IS490DB and IS452. Contains SQL scripts for creating a database of states, conflicts, and associated entities, as well as Python scripts for transforming .csv files from COW, ICOW, and Polity IV into SQL insert statements for the database."
header:
  image: /assets/images/project_irdbhome.jpg
  #teaser: assets/images/unsplash-gallery-image-1-th.jpg
sidebar:
  - title: Project Name
    text: "International Relations Database (IRDB)"
    #image:
  - title: "Description"
    text: "Final project for IS490DB and IS452. Contains SQL scripts for creating a database of states, conflicts, and associated entities, as well as Python scripts for transforming .csv files from COW, ICOW, and Polity IV into SQL insert statements for the database."
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

For the database side of the project, I will write a SQL script to create a database that contains, connects, and describes the disparate datasets published by the [Correlates of War project](http://www.correlatesofwar.org/), the [Issue Correlates of War project](http://www.paulhensel.org/icow.html), and the [Polity IV project](http://www.systemicpeace.org/polityproject.html).

However, this only covers the creation of the tables and their referential integrity. The python side of the project will involve writing scripts to transform .csv files into SQL insert statements.

Together, both sides of the project will result in a Github project repo that contains the necessary scripts to allow anyone to create and fill the database on their own machine. I plan to incorporate proper attribution, metadata, and meaningful context drawn from the codebooks into the database, as well as include SQL scripts for example views that transform the complex database back into the tabular form political scientists are used to for analytical work.

<!--{% include gallery caption="This is a sample gallery." %}-->
