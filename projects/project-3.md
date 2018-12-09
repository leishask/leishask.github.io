---
layout: project
type: project
image: images/Formula1.jpg
title: Formula 1 Database
published: false
permalink: projects/formula1-database
# All dates must be YYYY-MM-DD format!
date: 2017-12-04
labels:
  - Microsoft Access
  - Databases
  - SQL
  - Formula 1
  - ICS 129
summary: A group project to create a database on a chosen topic for ICS 129 at Leeward Community College.
---

<img class="ui medium right floated rounded image" src="../images/Formula1ERDiagram.png">

For this group project, we were required to create a database from scratch using the 2-step process: information-level design and physical-level design. The database had to have a purpose and a general theme.

My group decided to create a database for Formula 1 racing. The database included four tables that represented the teams, drivers, tracks, and scheduled races. Expanding further, each table included at least four relevant attributes, a primary key, and foreign keys that linked the tables together. Also, forms and reports were created for data input and data viewing. After our database was completed, we presented it to our professor as a final project.

Overall, I acquired a leadership role on this project. I took the position of the "leader" role because I had a clear understanding of how a database is created and implemented in Microsoft Access. Essentially, I made the big decisions on the approach we should take and the materials we should utilize.

With the theme we chose, I created and implemented the database tables and relationships. I created the ER Diagram of the database, the Microsoft Access database file, a running log for ideas and the task list, and took the lead on the presentation. I also retreived Formula 1 Racing data for the track, team and race tables. This project allowed me the opportunity to further experience a leadership role and implement a database that could be used in a real life situation.

Here are the SQL Statements we used in our Microsoft Access database:

```SQL
CREATE TABLE TEAM (
TeamNum Number PRIMARY KEY,
TeamName Text NOT NULL,
Base Text NOT NULL,
NumChampTitles Number NOT NULL,
TotalPoints Number NOT NULL);

ALTER TABLE DRIVER
ADD DriverPoints Number;

ALTER TABLE DRIVER
ADD CONSTRAINT BirthDateRule
CHECK (BirthDate BETWEEN #12/4/1917# AND #12/4/1999#);

ALTER TABLE RACE
ADD CONSTRAINT EventDateRule
CHECK (EventDate BETWEEN #3/26/2017# AND #11/26/2017#);
```
