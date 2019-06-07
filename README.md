# Twitter sentiment analysis in Azure
This contains the guidance to provision resources in Azure for the Twitter Sentiment Analysis.
You can do this in several ways:
* With a build and release pipeline
* With a script
* By doing it manually

## Here are the steps for doing it manually
Start by logging in to the Azure portal with your team account, https://portal.azure.com 

![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/AzurePortal.png)


* Setup azure resources by doing the following steps:
  * Select create resource and select "Template deployment (deploy using custom templates)"
  
![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/TemplateDeployment.png)  
  
  * Select "Build your own template in the editor"


![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/BuildYourOwn.png)    
  
  * Copy and paste code from [github](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/Azure/twsentiment-azresources.json), click save


 ![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/SaveTemplate.png)    
    
  * Select your resource group and a location close to you, leave CommonName as it is and write prod as the environment name. Agree to the terms and click purchase


  ![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/Purchase.png)    
  
  * When the provisioning is done open your resource group and select your app service. Select + next to functions and create new function. Select HTTP trigger based on C# and call the function TwitterSentimentFunction
 
  ![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/Createfunction.png)  
  
  ![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/Createfunction2.png)  
  
  * Click create and copy code from [github](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/Azure/TwitterSentimentFunction/AzureFunction.v1.csx), click save
  
  ![Screenshot](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/Createfunction3.png)  

# Using the resources for sentiment analysis
Once you have deployed these resources, you will need a twitter application (ConsumerKey,ConsumerSecret) and can configure one the following Azure DevOps extensions:
* [Twitter Sentiment Analysis as Release Gate](https://marketplace.visualstudio.com/items?itemName=ms-devlabs.vss-services-twittersentimentanalysis)
* [Twitter Sentiment Analysis on Dashboard](https://marketplace.visualstudio.com/items?itemName=solidify-labs.twitter-sentiment-dashboard-widgets)