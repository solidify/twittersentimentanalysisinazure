# Twitter sentiment analysis in Azure
This contains the guidance to provision resources in Azure for the Twitter Sentiment Analysis.
You can do this en sevreal ways:
* With a build and release pipeline
* With a script
* By doing it manually

## Here are the steps for doing it manuellay
Start by logging in to the Azure portal with your team account, https://portal.azure.com 

[drag]: https://github.com/solidify/twittersentimentanalysisinazure/blob/master/documents/AzurePortal.png


* Setup azure resources by doing the following steps:
  * Select create resource and select "Template deployment (deploy using custom templates)"
  * Select "Build your own template in the editor"
  * Copy and paste code from [github](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/Azure/twsentiment-azresources.json), click save
  * Select your resource group and a location close to you, leave CommonName as it is and write prod as the environment name. Agree to the terms and click purchase
  * When the provisioning is done open your resource group and select your app service. Select + next to functions and create new function. Select HTTP trigger based on C# and call the function TwitterSentimentFunction
  * Click create and copy code from [github](https://github.com/solidify/twittersentimentanalysisinazure/blob/master/Azure/TwitterSentimentFunction/AzureFunction.v1.csx), click save
  

