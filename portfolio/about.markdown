---
layout: page
title: Sample Deployment Guide
permalink: /deploymentguide/
---
# How To Deploy Child Applications 
Identifying information has been redatcted and random characters have been input instead. 
## Deploying To Cloud 
Before you begin deploying, ensure that you have updated all versions in helm-charts and (for UI applications) update the package.json and production/index.html
* You can find the latest deployed version of your app by searching for it in Rancher. 

> Not sure what version number your app should be bumped up to? Check out this quick guide on [Semantic Versioning](https://semver.org/)

### Build Your Docker Image
To build your docker image, run the following command where {image_name} is the project

` docker build -f path/to/Dockerfile -t $$$$/$$$$/{image_name}:{tag} . `

If you are building a UI image, append the following build argument to the command above

` --build-arg npmConfigCmd=setConfig:cloud `
### Push Docker Image To Cloud Harbor Registry
Run the following docker command where {image_name} is the project

` docker push $$$$/$$$$/{image_name}:{tag} `

### Update App Configuration
* Find the application you are deploying at $$$$$$ 
* Click on the row, and hit edit
* Update the version and bundle version to match the versions of application you are deploying
* Hit Save

### Update Secrets & Deploy Image To Kubernetes
Before deploying your image to kubernetes using Helm charts, make any secret/configmap updates that are necessary. 
Run the following helm command where {release_name} is the project and {chart_directory} (for templates and yaml files) is LIKELY also the project.


`helm --tiller-namespace=$$$$ --namespace=$$$$ upgrade -i {release_name} {chart_directory} --set=image.repository=$$$$/$$$$/{image_name}, image.tag={tag}, ingress.env=$$$$,ingress.domain=$$$$ `

## Internal Deployments
In Jenkins, run the "External to Internal" job for your application. This moves the source code from the Dev Cloud Bitbucket to the On-Prem Bitbucket. 

For Internal Deployments, you must deploy to Dev and Test in that order. You must also perform any tests necessary to ensure the application is working in each environment prior to deploying to any higher environment. 

### Setting Up Docker Image

#### Update Helm Charts
Commit and push Helm chart changes (if any) to the $$$$ Bitbucket repo for this application.
Make sure to commit your changes to the $$$$ branch in $$$$, NOT the master branch.

#### Build & Push Docker Image 
* Using SSH, login to $$$$ using Moba Xterm Pro
* Either clone or `cd` into your project and pull down the updated changes. 
* Build Docker Image 
    * Run the following docker command 

        `sudo docker build -f path/to/Dockerfile -t artifactory-rco.$$$$.com/$$$$/{image_name}:{tag} .`
    * If you are building a UI image, append the following argument to the above command

    ` --build-arg npmConfigCmd=setConfig:internal` 

#### Login to Artifactory
This should only need to be done the first time you push an image, or if you recently changed your password. Make sure to specify a Docker config file in your home directory. 

* Run the following docker command

    `sudo docker --config $HOME/.docker login artifactory-rco.$$$$.com`
* When prompted, enter your username and password 

#### Push Image to Artifactory
Make sure to specify a Docker config file in your home directory. 

* Run the following Docker command 

    `sudo docker --config $HOME/.docker push artifactory-rco.$$$$.com/$$$$/{image_name}:{tag}`

* Logout of Docker by running the following Docker command 

    `sudo docker --config $HOME/.docker logout artifactory-rco.$$$$.com`

### Deploying to Dev
* Add new bundle.js file to $$$$ app config in $$$$ (only needed if deploying a $$$$ child application)
* Go to $$$$ and login using your AD credentials.
   * Click on $$$$
   * Click on $$$$-pipelines
   * Click on $$$$
   * Click on $$$$ 
* If there are secret/configmap updates that need to be made for your application, upload the new secrets/configmaps using the $$$$ Jenkins job under Utils.
* Build the $$$$ Jenkins job, selecting the appropriate dropdown item for your application and entering the image tag you just pushed to Artifactory.
*Go back to $$$$ > $$$$-$$$$ > $$$$-$$$$ and click on the tab $$$$.
There should be a new pipeline at the top of the screen with the first step complete. Ensure that the DockerTag and DockerProject values are correct.
* Run the $$$$ Jenkins job from the pipeline view by clicking "trigger" which looks like a small clock
After validating the app has successfully deployed, remove the previous bundle.js file from Dev $$$$ (if applicable).

### Deploying To Test
* Add new bundle.js file to $$$$ app config in $$$$ 
* If there are secret/configmap updates that need to be made for your application, upload the new secrets/configmaps using the $$$$ Jenkins job under Utils.
* Go to the $$$$ view in Jenkins, and run the $$$$ Jenkins job for the pipeline that was created when deploying to Dev.
* After validating the app has successfully deployed, remove the previous bundle.js file from $$$$ (if applicable).





