
# Project Operationalizing Machine Learning

In this project a cloud-based machine learning production model is configured, deployed and consumed in Azure. Also a pipeline will is created, published and consumed. The dataset being used is a Marketind data from a Bank and its users. The steps followed for this project:
1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline
8. Documentation

## Architectural Diagram

![ScreenShot](/screenshots/Architectural Diagram.png)

## Key Steps
 

Step 1: Authentication
Creating the "Service Principal" to enter the workspace. This is a good way to authenticate to Azure ML services
I used the lab Udacity and this was taken care of, so I skiped this step since I am not authorized to create a security principal. 

Step 2: Automated ML Experiment
First the Dataset is being uploaded
<Screenshot of "Registered Data" showing that Bankmarketing dataset is available>

Create an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment.
<Screenshot showing that the experiment is showwn as completed>

After the experiment run completes all the models and their metrics can be seen. The best model is at the top.
<Screenshot of the best model after the experiment completes>

Step 3: Deploy the Best Model
Deploying the Best Model will allow to interact with the HTTP API service and interact with the model by sending data over POST requests. Also download the config.json file of the best-deployed-model.

Step 4: Enable Application Insights
Enable Application Insights and retrieve logs. Script logs.py
<Screenshot showing that "Application insights" is enabled in the Details tab of the endpoint>
<Screenshoot showing logs by running the provided logs.py script>
    
Step 5: Swagger Documentation
Consume the deployed model using Swagger. Azure provides a swagger.json file for the deployed model. Swagger.sh downloads the latest swagger container. File serve.py will start a Python server.
<Screenshot showing that swagger runs on localhost showing the HTTP API methods and responses for the model>

Step 6: Consume Model Endpoints
Interact with the trained model. Script endpoint.py
<Screenshot showing that the endpoint.py script runs against the API producing JSON output from the model>
    
Benchmark
Load-test the model
<Screenshot showing that Apache Benchmark (ab) runs against the HTTP API using authenthication keys ti retreive performance results>

Step 7: Create, Publish and Consume a Pipeline
<Screenshot The pipeline section, showing the pipeline has been created>
<Screenshot showing the pipeline endpoint>
<Screenshot showing the Bankmarketing dataset with the AutoML module>
<Screenshot The "Published Pipeline Overview", showing a REST endpoint and a status of active>
<Screenhot in Jupyter Notebook showing that the "Use RunDetails Widget" shows the steps run>
<Screenshot showing the Scheduled run>
    
    
## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate  
    
   
## How to improve the project in the future    
Collect more data to improve the model accuracy
Data cleaning and feature engineering will be helpful in improving data quality
Try different models with hypertuned parameters   
    
    

