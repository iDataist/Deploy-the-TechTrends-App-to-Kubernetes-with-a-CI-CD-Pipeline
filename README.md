# TechTreds

## Overview
TechTrends is an online website used as a news sharing platform, that enables consumers to access the latest news within the cloud-native ecosystem. In addition to accessing the available articles, readers are able to create new media articles and share them. The first prototype of the TechTrends website was built. In this project, I packaged and deployed TechTrends to Kubernetes using a CI/CD pipeline.

The web application is written using the Python Flask framework. It uses SQLite, a lightweight disk-based database to store the submitted articles.Below you can examine the main components of the firsts prototype of the application:
![](screenshots/webapp_components.png)

Additionally, the initial sitemap of the website can be found below:
![](screenshots/techtrends_sitemap.png)

Where:

- About page - presents a quick overview of the TechTrends site
- Index page - contains the content of the main page, with a list of all available posts within TechTrends
- New Post page - provides a form to submit a new post
- 404 page - is rendered when an article ID does not exist is accessed

And lastly, the first prototype of the application is storing and accessing posts from the "POSTS" SQL table. A post entry contains the post ID (primary key), creation timestamp, title, and content. The "POSTS" table schema can be examined below:
![](screenshots/posts_table_schema.png)


This is a Flask application that lists the latest articles within the cloud-native ecosystem.

## Getting Started
This repository file structure can be found below:
```
techtrends/
├── README.md
├── __init__.py
├── app.py
├── init_db.py
├── requirements.txt
├── schema.sql
├── static
│   └── css
│       └── main.css
└── templates
    ├── 404.html
    ├── about.html
    ├── base.html
    ├── create.html
    ├── index.html
    └── post.html
```
Where:

- README.md contains the main steps of how to execute the TechTrends application
- __init__.py is a reserved method used to indicate that a directory is a Python package
- app.py contains the main logging of the TechTrends application
- init_db.py is a file that is used to initialize the posts database with a set of articles
- requirements.txt contains a list of packages that need to be installed before running the TechTrends application
- schema.sql outlines the posts database schema
- static/ folder contains the CSS files
- templates/ folder outlines the HTML structure of the TechTrends application

Within the project folder you will notice some extra folders and files that are related to the CI/CD pipeline.

- argocd - folder contains the ArgoCD manifests
- helm - folder contains the Helm chart files
- kubernetes - folder contains Kubernetes declarative manifests
- Vagrantfile - the file contains the configuration for the vagrant box
- *_commands - the files record commands 

To run this application follow these steps:

- Initialize the database by using the python init_db.py command. This creates or overwrites (if the file already exists) the database.db file that is used to store and access the available posts.
- Run the TechTrends application by using the `python app.py` command. The application is running on port 3111 and you can access it by querying the http://127.0.0.1:3111/ endpoint.

