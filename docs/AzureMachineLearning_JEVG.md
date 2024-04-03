# Exploring Automated Machine Learning in Azure Machine Learning

In this exercise, you will use the automated machine learning feature of Azure Machine Learning to train and evaluate a machine learning model. You will then implement and test the trained model.

## Creating an Azure Machine Learning Workspace

To use Azure Machine Learning, you must provision an Azure Machine Learning workspace in your Azure subscription. You can then use Azure Machine Learning Studio to work with the resources in the workspace.

**Tip:** If you already have an Azure Machine Learning workspace, you can use it and move on to the next task.

Sign in to Azure Portal with your Microsoft credentials at [https://portal.azure.com](https://portal.azure.com)

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/7d284816-7e5b-4122-83ff-421c033d3339" width="500" height="100">
<br ><em><strong>Create a new resource into Azure Portal.</strong></em><br />
</p>

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/141aff35-1a00-44de-9133-5bc57bc3819c" width="500" height="500">
<br ><em><strong>Example of Azure Portal browser and dashboard.</strong></em><br />
</p>

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/e3755aad-b983-40d6-bc82-e6ce948bf0d7" width="500" height="500">
<br ><em><strong>Azure services overview.</strong></em><br />
</p>

Select + Create a resource, search for Machine Learning and create a new Azure Machine Learning resource with the following settings:
- Subscription: your Azure subscription.
- Resource Group: create or select a resource group.

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/3318a4b1-7af6-4779-8b67-c79af5573858" width="500" height="500">
<br ><em><strong>Creating a new Azure Machine Learning resource.</strong></em><br />
</p>

- Name: type a unique name for the workspace.
- Region: select the nearest geographical region.
- Storage account: note the new default storage account to be created for the workspace.
- Keystore: note the new default keystore that will be created for the workspace.
- Application Insights: Note the new default Application Insights resource that will be created for the workspace.
- Container record: None (one will be created automatically the first time you deploy a model in a container).

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/3415d721-546d-43ef-a8cc-3729e758ff46" width="500" height="500">
<br ><em><strong>Configuring new Azure Machine Learning workspace settings.</strong></em><br />
</p>

Select Review + create and then select Create. Wait for the workspace to be created (this may take a few minutes), and then go to the deployed resource.

Select Launch Studio (or open a new browser tab, go to [https://ml.azure.com](https://ml.azure.com) and sign in to Azure Machine Learning Studio with your Microsoft account). Close all messages that are displayed.

In Azure Machine Learning Studio, you should see the newly created workspace. If not, select All Workspaces from the menu on the left, and then select the workspace you just created.

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/fc20fc1d-7eab-496e-8bc3-dc7c5ae589bd" width="500" height="500">
<br ><em><strong>Azure Machine Learning Studio workspace.</strong></em><br />
</p>





![alt text](image-1.png)





## Using automated machine learning to train a model

Automated machine learning allows you to test various algorithms and parameters to train several models and identify the best one for your data. In this exercise, you will use a dataset of historical bicycle rental details to train a model that predicts the number of bicycle rentals to expect on a given day, based on seasonal and weather characteristics.

Citation: The data used in this exercise is derived from Capital Bikeshare and used in accordance with the published data license agreement.

In Azure Machine Learning Studio, see the Automated Machine Learning page (under Creation).

<p align="center">            
<img src="image.png" width="500" height="500">
<br ><em><strong>Automated Machine Learning page overview.</strong></em><br />
</p>

Create a new automated ML job with the following configuration, using Next as needed to progress through the user interface:

<p align="center">            
<img src="image-2.png" width="500" height="500">
<br ><em><strong>Creating a new automated ML job.</strong></em><br />
</p>

### Basic settings:

- Job name: mslearn-bike-automl
- New experiment name: mslearn-bike-rental
- Description: Automated machine learning for bike rental prediction.
- Tags: none

<p align="center">            
<img src="image-3.png" width="500" height="500">
<br ><em><strong>Basic settings for the ML job.</strong></em><br />
</p>

### Task and data type:

<p align="center">            
<img src="image-4.png" width="500" height="500">
<br ><em><strong>Data set creation and selection.</strong></em><br />
</p>

- Select task type: Regression
- Select data set: create a new data set with the following settings:
    - Data type:
    - Name: bicycle rental
    - Description: Bicycle rental historical data
    - Type: Tabular

<p align="center">            
<img src="image-5.png" width="500" height="500">
<br ><em><strong>Task and data type settings.</strong></em><br />
</p>


### Data Source:

- Select from web archives

<p align="center">            
<img src="image-6.png" width="500" height="500">
<br ><em><strong>Data source selection.</strong></em><br />
</p>

- Web URL: `https://aka.ms/bike-rentals`
- Omit data validation: do not select

<p align="center">            
<img src="image-7.png" width="500" height="500">
<br ><em><strong>Web URL configuration.</strong></em><br />
</p>


### Settings:

- File format: Delimited
- Delimiter: Comma
- Encoding: UTF-8
- Column headers: only the first file has headers
- Skip rows: None
- Dataset contains multi-line data: do not select

<p align="center">            
<img src="image-8.png" width="500" height="500">
<br ><em><strong>Settings for data import.</strong></em><br />
</p>



### Schema:

- Include all columns other than Path.
- Review automatically detected types

<p align="center">            
<img src="image-9.png" width="500" height="500">
<br ><em><strong>Schema configuration and review.</strong></em><br />
</p>

Select Create. Once the dataset is created, select the bike rental dataset to continue submitting the automated ML job.

<p align="center">            
<img src="image-10.png" width="500" height="500">
<br ><em><strong>Final step: Dataset creation confirmation.</strong></em><br />
</p>


### Task Setup:

- Task type: regression
- Dataset: Bicycle Rental
- Target Column: Rentals (integer)
- Additional configuration settings

<p align="center">            
<img src="image-11.png" width="500" height="500">
<br ><em><strong>Task setup for regression on Bicycle Rental dataset.</strong></em><br />
</p>

Primary Metric: Normalized Mean Square Error
Explain best model: Not selected
Use all supported models: Unselected. Will restrict the job to test only a few specific algorithms.

<p align="center">            
<img src="image-12.png" width="500" height="500">
<br ><em><strong>Selection of models and primary metric.</strong></em><br />
</p>

### Limits: Expand this section

- Maximum number of tests: 3
- Maximum number of simultaneous trials: 3
- Maximum number of nodes: 3
- Metric score threshold: 0.085

<p align="center">            
<img src="image-13.png" width="500" height="500">
<br ><em><strong>Setting limits for the automated ML job.</strong></em><br />
</p>

### Validation and testing:

- Validation type: training validation split.
- Percentage of validation data: 10
- Test data set: None

<p align="center">            
<img src="image-14.png" width="500" height="500">
<br ><em><strong>Validation and testing setup.</strong></em><br />
</p>

### Computation:

- Select process type: No server
- Virtual machine type: CPU
- Virtual machine level: Dedicated
- Virtual Machine size: Standard_DS3_V2*

<p align="center">            
<img src="image-15.png" width="500" height="500">
<br ><em><strong>Computation and virtual machine settings.</strong></em><br />
</p>

Submit the training job. It starts automatically.

Wait for the job to finish. It may take a while, now might be a good time to have a coffee!

<p align="center">            
<img src="image-16.png" width="500" height="500">
<br ><em><strong>Job submission confirmation.</strong></em><br />
</p>

### Check the best model

<p align="center">            
<img src="https://github.com/JoseEmmanuelVG/Microsoft_Student_Technical_Training_MLSA-JEVG/assets/89156254/1322afc1-5aba-4da7-924b-81a83fae6d4b" width="600" height="300">
<br ><em><strong>It isnt finish.</strong></em><br />
</p>



Once the automated machine learning job is finished, you can review the best model you have trained.

In the Automated Machine Learning Job Overview tab, note the best model summary. Screenshot of the best model summary from the automated machine learning job with a box around the algorithm name.

**Note** You may see a message in the status "Warning: User specified output score has been reached...". This is an expected message. Proceed to the next step.

Select the text in Algorithm name to see the best model to view its details.

Select the Metrics tab and select the residuals and predicted_true graphs if they are not already selected.

Review the graphs that show the performance of the model. The residuals plot shows the residual values (the differences between the predicted and actual values) as a histogram. The predicted_true plot compares the predicted values with the actual values.

**NOTE:** Once you are done, you can delete the content security resource from the Azure Portal. Removing the resource is one way to reduce the costs that accrue when the resource exists in the subscription. To do this, go to the Content Security Resource Overview page. Select Delete at the top of the screen.




<details>
  <summary>🌟 Did you find any repository useful?</summary>
  If any project has been helpful to you, consider giving it a ⭐ star in the repository and follow my GitHub account to stay tuned for future updates! 🚀

  In addition, I am always open to suggestions, recommendations or collaborations. Feel free to [get in touch](https://www.linkedin.com/in/vazquez-galan-jose-emmanuel-664968221) if you have any questions or ideas for improving this project. I'm excited for your feedback and contributions.

  Thank you for your interest and support! 😊
</details>




<p align="center">
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
</p>
