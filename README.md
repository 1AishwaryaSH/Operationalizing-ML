

# Operationalizing Machine Learning

This project aims at using Microsoft Azure to configure a cloud-based machine learning production model, deploy it, and consume it and also to create, publish and consume a pipeline using python SDK.
In this project I used the data set containing a Bank's Marketing data that involves a target label of binary classification mentioning whether the customer will do a deposit or not, labelled with the name 'y'. 
 
## Architectural Diagram
![architecture](archi.JPG)
## Key Steps
Step 1: register the dataset
![dataset](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/datasets.JPG)

I registered the dataset from localfiles after downloading using the URL "https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv".

Step 2: Create an AutoML run
![AutoML](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/AutomatedML%20run.JPG)

I set up an autoML run using the above dataset.

The run generated various models.
![models](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/models.JPG)
The best model found was "VotingEnsemble" with an accuracy of 91.93%.
![best model](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/models.JPG)

Step 3: Deploy the best model
![deploy](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/deploy%20model.JPG)

Step 4: Insights
Once we deploy the model we should enable the application insights this is done in the logs.py file by service.update(enable_app_sights=True) and executing it.
![app insights](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/enable%20insights.jpg)

The log files shown as 
![log](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/log%20(2).JPG)

Once we run this we can find an URL in the deployed model providing the app insights
![insights](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/insights.JPG)


Step 5: Swagger
Swagger is run on the local host
* Get the swagger.json file from the URI available in the deployed model
* Download it into the same directory as the serve.py, swagger.sh files
![json](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/swagger.json.JPG)
* Run the shell script and you will find swagger at http://localhost:9000
![sl](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/swagger%20localhost.JPG)
* open a new git bash and execute the serve.py file 
* Type http://localhost:8000/swagger.json and you will get the deployed model there, along with the GET and POST requests.
DEPLOYED MODEL
![deploy](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/swagger%20deploy%20model.JPG)
GET
![get](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/get.JPG)
POST
![post](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/post.JPG)
![post](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/post1.JPG)

Step 6: Endpoint Consumption
We can find the json output by running the endpoint.py file.
![endpoint](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/endpoint%20result.JPG)

Step 7: Creating and publishing pipelines
We need to get the config.json file from the subscription area on the right side corner of the workspace.
![](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/pipeline%20submitted.JPG)
![](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/pipeline%20completed.JPG)
![](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/pipeline%20endpoint.JPG)
![](https://github.com/1AishwaryaSH/Operationalizing-ML/blob/main/screenshots/publish%20pipeline.JPG)

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
