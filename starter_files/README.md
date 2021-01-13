
# Project Operationalizing Machine Learning

In this project a cloud-based machine learning production model is configured, deployed and consumed in Azure. Also a pipeline will is created, published and consumed. The dataset being used is a Marketind data from a Bank and its users. 

## Architectural Diagram

The steps followed for this project:
1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline
8. Documentation

![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Architectural_Diagram.png)

## Key Steps

Step 1: Authentication
Creating the "Service Principal" to enter the workspace. This is a good way to authenticate to Azure ML services
I used the lab Udacity and this was taken care of, so I skiped this step since I am not authorized to create a security principal. 

Step 2: Automated ML Experiment
First the Dataset is being uploaded
Screenshots of "Registered Data" showing that Bankmarketing dataset is available:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Registered_Datasets_in_ML_Studio_1.png)

![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Registered_Datasets_in_ML_Studio_2.png)

Create an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment.
Screenshots showing that the experiment is shown as completed:
Jupyter Notebook view
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Experiment_completed_Notebook.png)

ML Studio view
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Experiment_completed_ML_Studio_1.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Experiment_completed_ML_Studio_2.png)

After the experiment run completes all the models and their metrics can be seen. The best model is at the top:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Models_%20experiment_complete.png)

The Algorithm name of the best model is VotingEnsemble with AUC weighted = 0.94672. Screenshot of the best model after the experiment completes:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Best_model_experiment_complete.png)

Step 3: Deploy the Best Model
Deploying the Best Model will allow to interact with the HTTP API service and interact with the model by sending data over POST requests. Also download the config.json file of the best-deployed-model. Deploy the model using Azure Container Instance.
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Best_model_deployed.png)

Step 4: Enable Application Insights
Enable Application Insights and retrieve logs. Script logs.py
Screenshot showing that "Application insights" is enabled in the Details tab of the endpoint
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Application_Insights_is_enabled_Details_Tab.png)

Screenshot showing that "Application insights" is enabled using GitBash
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Application_Insights_is_enabled_GitBash.png)

Screenshots showing logs by running the provided logs.py script in GitBash:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/logs_1.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/logs_2.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/logs_3.png)
    
Step 5: Swagger Documentation
Consume the deployed model using Swagger. Azure provides a swagger.json file for the deployed model. Swagger.sh downloads the latest swagger container. Script serve.py will start a Python server.
Screenshots showing that swagger runs on localhost showing the HTTP API methods and responses for the model:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Swagger_runs_on_localhost_1.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Swagger_runs_on_localhost_2.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Swagger_runs_on_localhost_3.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Swagger_runs_on_localhost_4.png)

Step 6: Consume Model Endpoints
Interact with the trained model. Script endpoint.py
Screenshot showing that the endpoint.py script runs against the API producing JSON output from the model
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/endpoint_1.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/endpoint_2.png)
Benchmark
Load-test the model
Screenshot showing that Apache Benchmark (ab) runs against the HTTP API using authenthication keys ti retreive performance results
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Apache_Benchmark_ab.png)

Step 7: Create, Publish and Consume a Pipeline
Screenshot The pipeline section, showing the pipeline has been created
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Pipeline_created_Azure_ML_Studio.png)

Screenshot showing the pipeline endpoint
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Pipeline_Endpoint_Azure_ML_Studio_1.png)
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Pipeline_Endpoint_Azure_ML_Studio_2.png)

Screenshot showing the Bankmarketing dataset with the AutoML module
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/The_Bankmarketing_Dataset_with_the_AutoML_module.png)

Screenshot The "Published Pipeline Overview", showing a REST endpoint and a status of active
Jupyter Notebook view:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/REST_endpoint_Notebook.png)

Azure ML Studio view:
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/REST_endpoint_Azure_ML_Studio.png)

Screenhot in Jupyter Notebook showing that the "Use RunDetails Widget" shows the steps run
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/Use_RunDetails_Widget_Notebook.png)

Screenshot showing the Scheduled run
![](https://raw.githubusercontent.com/silvanazdravevska/Project2-Microsoft-Azure-Nanodegree/main/starter_files/Screenshots/ML_Studio_scheduled_run.png)
       
## Screen Recording
Link to a screen recording of the project in action [https://drive.google.com/file/d/1Fus7SDQz4uRkIebdgXRnfTAVKPtiYgsp/view?usp=sharing](https://drive.google.com/file/d/1Fus7SDQz4uRkIebdgXRnfTAVKPtiYgsp/view?usp=sharing)  
  
## How to improve the project in the future    
Collect more data to improve the model accuracy
Data cleaning and feature engineering will be helpful in improving data quality
Try different models with hypertuned parameters   
    
    

