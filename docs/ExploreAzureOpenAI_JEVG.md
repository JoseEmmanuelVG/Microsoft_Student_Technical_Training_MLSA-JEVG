Explore Azure OpenAI

Azure OpenAI Service brings the generative AI models developed by OpenAI to the Azure platform, enabling you to develop powerful AI solutions that benefit from the security, scalability, and integration of services provided by the Azure cloud platform.

In this exercise, you’ll explore Azure OpenAI Service and use it to deploy and experiment with generative AI models.

This exercise will take approximately 25 minutes.

Before you start
You will need an Azure subscription that has been approved for access to the Azure OpenAI service for both text and code models, and DALL-E image generation models.

To sign up for a free Azure subscription, visit https://azure.microsoft.com/free.
To request access to the Azure OpenAI service, visit https://aka.ms/oaiapply.



## Provision an Azure OpenAI resource
Before you can use Azure OpenAI models, you must provision an Azure OpenAI resource in your Azure subscription.

Sign into the Azure portal.
Create an Azure OpenAI resource with the following settings:
Subscription: An Azure subscription that has been approved for access to the Azure OpenAI service.
Resource group: Choose an existing resource group or create a new one with a name of your choice.
Region: East US*
Name: A unique name of your choice
Pricing tier: Standard S0

![alt text](image-43.png)

* Different regions have different availability and quota for models. In this exercise, you’ll be using a GPT-35-Turbo model for text generation and a DALL-E model for image generation, both of which are suppoprted in East US.

Wait for deployment to complete. Then go to the deployed Azure OpenAI resource in the Azure portal.
![alt text](image-44.png)


## Explore Azure OpenAI Studio
You can deploy, manage, and explore models in your Azure OpenAI Service by using Azure OpenAI Studio.

On the Overview page for your Azure OpenAI resource, use the Explore button to open Azure OpenAI Studio in a new browser tab. Alternatively, navigate to Azure OpenAI Studio directly.

When you first open Azure OpenAI Studio, it should look similar to this:

![alt text](image-45.png)

View the pages available in the pane on the left. You can always return to the home page at the top. Additionally, OpenAI Studio provides multiple pages where you can:

Experiment with models in a playground.

![alt text](image-46.png)

Manage model deployments and data.

![alt text](image-47.png)



## Deploy a model for language generation
To experiment with natural language generation, you must first deploy a model.

On the Models page view the available models in your Azure OpenAI service instance.
Select any of the gpt-35-turbo models for which the Deployable status is Yes, and then select Deploy:

![alt text](image-48.png)




Create a new deployment with the following settings:
Model: gpt-35-turbo
Model version: Auto-update to default
Deployment name: A unique name for your model deployment
Advanced options
Content filter: Default
Deployment type: Standard
Tokens per minute rate limit: 5K*
Enable dynamic quota: Enabled
* A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.


![alt text](image-49.png)



### Use the Chat playground to work with the model

Now that you have deployed a model, you can use it in the Chat playground to generate natural language output from prompts that you submit in a chat interface.

In Azure OpenAI Studio, navigate to the Chat playground in the left pane.

The Chat playground provides a chatbot interface with which you can interact with your deployed model, as shown here:

In the Configuration pane, ensure that your model deployment is selected.

![alt text](image-50.png)


In the Assistant setup pane, select the Default system message template, and view the system message this template creates. The system message defines how the model will behave in your chat session.
In the Chat session section, enter the following user message.


![alt text](image-51.png)


Code
What is generative AI?
Observe the output returned by the model, which should provide a definition of generative AI.

![alt text](image-52.png)


Enter the following user message as a follow-up question:

Code
What are three benefits it provides?
Review the output, noting that the chat session has kept track of the previous input and response to provide context (so it correctly interprets “it” as referring to “generative AI”) and that it provides a suitable response based on what was requested (it should return three benefits of generative AI).

![alt text](image-53.png)




### Use the DALL-E playground to generate images
In addition to language generation models, Azure OpenAI Service supports the DALL-E 2 / Dalle3 model for image generation.

Note: You must have applied for and received access to DALL-E functionality in your Azure OpenAI service access application to complete this section of the exercise.

In Azure OpenAI Studio, navigate to the DALL-E playground in the left pane.

![alt text](image-54.png)


Enter the following prompt:

Code
 A robot eating spaghetti
Select Generate and view the results, which should consist of an image based on the description you provided in the prompt, similar to this:

![alt text](image-55.png)

![alt text](image-56.png)


Generate a second image by modifying the prompt to:

Code
 A robot eating spaghetti in the style of Rembrandt
Verify that the new image matches the requirements of the prompt, similar to this:

![alt text](image-57.png)


<details>
  <summary>🌟 Did you find any repository useful?</summary>
  If any project has been helpful to you, consider giving it a ⭐ star in the repository and follow my GitHub account to stay tuned for future updates! 🚀

  In addition, I am always open to suggestions, recommendations or collaborations. Feel free to [get in touch](https://www.linkedin.com/in/vazquez-galan-jose-emmanuel-664968221) if you have any questions or ideas for improving this project. I'm excited for your feedback and contributions.

  Thank you for your interest and support! 😊
</details>




<p align="center">
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
</p>
