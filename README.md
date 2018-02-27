# Stack Overflow Survey Data Analysis



## What is it ?
Hasura project which gives endpoints to analyse the stackoverflow survey results

## Contributors
Nalini Rangamani.

## How it Works
A survey has been done on Stackoverflow users to understand their demographics. This data is a CSV file. The relevant columns from it are loaded into a postgres database. The endpoints analyse the data and return the data which can be plotted as graphs by the frontend. This runs in a hasura cluster and uses hasura data apis. 

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
 From this, you can get the cluster-name. Replace course-77 with this cluster-name.

5. do hasura api-console and in the DATA section, create a table surveyresults with the following fields:
respondent - integer - primary key
professional - text
country - text.

6. From https://www.kaggle.com/stackoverflow/so-survey-2017/data copy the survey_results_public.csv file to the project folder. 

7. Open the file,in MS - Excel, delete all columns except respondent, country and professional. Save it as a csv file. Let it be survey results.csv. Open the surveyresults.csv file and delete the header line.

8. $ hasura microservice port-forward postgres -n hasura --local-port 6432 from git bash

9. From CMD , go to the project directory. 
psql -h localhost -p 6432 -d hasuradb -U admin -c "copy surveyresults from STDIN with delimiter as ',';" surveyresults.csv.
This will load the data to the table.

https://app.course77.hasura-app.io/get_country will return the different countries and their aggregate count. This can be used by the frontend to plot a graph.

https://app.course77.hasura-app.io/get_professional will return the different kind of professionals and their aggregate count. This can be used by the frontend to plot a graph.

## How to build on top of this?
This webhook is written in Python using the Flask framework. The source code lies in microservices/app/src directory. server.py is where you want to start modifying the code.

If you are using any extra python packages, just add them to microservices/app/src/requirements.txt and they will be "pip installed" during the Docker build.

## Support
If you happen to get stuck anywhere, please mail me at nalini.rangamani@gmail.com. 
