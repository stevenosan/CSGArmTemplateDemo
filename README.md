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
1) Open Visual Studio 2017
2) Go to File > New > Project
3) Select Installed > Visual C# > Cloud > Azure Resource Group
4) Give it some name, some location (doesn't matter), select .NET Framework 4.7.1, and check Create New Git Repository
5) Select the "Web app" from the Visual Studio templates
6) Go ahead and save this and somehow import the solution directory into some Git client
7) Navigate to your VSTS Project
8) Create a new Build
9) Select the source that contains your solution (I used github), the pertinent repo and branch
10) Create an Empty Process
11) Give it some name, select the Hosted VS2017 agent queue.
12) Give the Phase 1 two steps. Build Solution and Publish Artifact
13) While this is building, let's create a Release
14) Select the "Azure App Service deployment" Template
15) Add an artifact, using the output of the build we created
16) For our first environment, let's call it Development, add an Azure Resource Group Deployment Task
17) For this example, fill out the Azure Subscription, Resource Group (give it a unique name, this will also be the websites name), Location and Template.
18) Go ahead and let this puppy run then go see your newly provisioned app service!

https://resources.azure.com/
