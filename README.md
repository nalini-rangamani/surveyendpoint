# Stack Overflow Survey Data Analysis



## What is it ?
Hasura project which gives endpoints to analyse the stackoverflow survey results

## How it Works
A survey has been done on Stackoverflow users to understand their demographics. This data is a CSV file. The relevant columns from it are loaded into a postgres database. The endpoints analyse the data and return the data which can be plotted as graphs by the frontend. This runs in a hasura cluster and uses hasura dat apis 

## What does it use

- [Hasura CLI](https://docs.hasura.io/0.15/manual/install-hasura-cli.html)
- [Git](https://git-scm.com)
- [Python 3](https://www.python.org/downloads/) and [pip](https://pip.pypa.io/en/stable/installing/) (required only for local development)

## How to deploy it

1. Install hasura CLI
2. run hasura quickstart surveydir -hpdf
3. Pull all files from this repo to surveydir directory.
4. Do the following:
$ git add . && git commit -m "Deployment commit"
$ git push hasura master

After the git push completes:


$ hasura microservice list
You will get output like:
$ hasura ms list
USER MS NAME     STATUS      INTERNAL-URL             EXTERNAL-URL
app              Running     app.course77-user:80     http://app.course77.hasura-app.io

HASURA MS NAME     STATUS      INTERNAL-URL                           EXTERNAL-URL
platform-sync      Running
gateway            Running
notify             Running     notify.course77-hasura:80              http://notify.course77.hasura-app.io
session-redis      Running     session-redis.course77-hasura:6379
le-agent           Running
sshd               Running
postgres           Running     postgres.course77-hasura:5432
data               Running     data.course77-hasura:80                http://data.course77.hasura-app.io
filestore          Running     filestore.course77-hasura:80           http://filestore.course77.hasura-app.io
auth               Running     auth.course77-hasura:80                http://auth.course77.hasura-app.io



