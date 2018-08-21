# CSGArmTemplateDemo
A Demo on Setting Up ARM Templates


# Pre-reqs
1) Azure Account
2) VSTS Account with Team/Project Setup
3) Visual Studio 2017 (could also potentially use Visual Studio Code)
4) Some sort of Git hosting (e.g. VSTS, Github)

# CLI Instructions
1) Go to Azure Portal
2) Create an App Service (probably want to set this guy to S1)
3) Wait for it to finish (this is probably a good time to go grab a beer or some food)
4) Once it's finished, navigate to the App Service
5) Select the Automation Script
  5a) Listen to Steve pontificate
6) Click "Download"
7) Extract the zip to some location (I chose C:\ )
8) Open powershell, navigate to the directory
9) Execute the deploy.ps1 powershell script
10) Retrieve your azure subscription from the subscription blade
11) .\deploy.ps1 -subscriptionid <yourSubscriptionId> -resourcegroupname <aResourceGroup> -deploymentname <whatever> -templatefilepath template.json 
12) Enter the appropriate azure credentials
13) watch some stuff spam across the screen
14) resourceGroupLocation = east us
15) Things are going to blow up
16) Update the nulls in the parameter.json with the values from the template
17) Go look at your newly created resource.

# CI/CD Instructions


https://resources.azure.com/
