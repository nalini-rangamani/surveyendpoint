# Stack Overflow Survey Data Analysis



## What is it ?
Hasura project which gives endpoints to analyse the stackoverflow survey results

## How it Works
A survey has been done on Stackoverflow users to understand their demographics. This data is a CSV file. The relevant columns from it are loaded into a postgres database. The endpoints analyse the data and return the data which can be plotted as graphs by the frontend. This runs in a hasura cluster and uses hasura dat apis 

## What does it use

- [Hasura CLI](https://docs.hasura.io/0.15/manual/install-hasura-cli.html)
- [Git](https://git-scm.com)
- [Python 3](https://www.python.org/downloads/) and [pip](https://pip.pypa.io/en/stable/installing/) (required only for local development)



