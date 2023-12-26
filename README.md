# Containerization-and-deployment-of-nodejs-application

## Goal
### To deploy an e-commerce application developed using React utilizing GitOps 

### The project workflow is shown below:


  ![Project1-diagram1](https://github.com/Noettie/End-to-End-automated-CI-CD-Pipeline-utilizing-GitOps-PART-ONE/assets/108426517/b56293f8-f11e-4745-80eb-edb06a1f4eb1) 



## Objectives

1. Containerize the application.
2. Push the docker image onto AWS Elastic Container Registry.
3. Deploy application onto digital ocean kubernetes cluster.
4. Make changes to manifest files that trigger automated deployment onto argocd.

## Tools:

<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/docker/docker-original-wordmark.svg" width="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/kubernetes/kubernetes-plain.svg" width="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" width="80"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" width="80"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/argocd/argocd-original-wordmark.svg" width="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/jenkins/jenkins-original.svg" width="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/digitalocean/digitalocean-original-wordmark.svg" width="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/github/github-original.svg" width="60"/>
<div>
  

## First part of the project is the Continous Integration Job

### Work flow:
1. Developer commits code to github
2. Jenkins checks out code and runs script on Jenkinsfile.
3. Jenkins builds docker image. 
4. Jenkins pushes image to docker registry.

## Prerequisites:

1. Spin up Jenkins server.
2. Create Dockerhub Credentials.
3. Create Github Credentials.
4. Configure github and docker credentials in Jenkins Credentials store.

# Steps

1. Create first build pipeline Job
2. Create the 2nd Pipeline Job that will contain the kubernetes manifest files argocd will be watching, set string parameters for this job
3. Run the first build, this will also trigger the manifest update build
4. Spin up kubernetes cluster in digital ocean.
  



