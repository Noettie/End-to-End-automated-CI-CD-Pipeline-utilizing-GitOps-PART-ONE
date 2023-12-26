## Containerization-and-deployment-of-nodejs-application

## Goal
### To deploy an e-commerce application developed using React utilizing GitOps 

### The project workflow is shown below:


  ![Project1-diagram1](https://github.com/Noettie/End-to-End-automated-CI-CD-Pipeline-utilizing-GitOps-PART-ONE/assets/108426517/b56293f8-f11e-4745-80eb-edb06a1f4eb1) 



### Objectives

1. Containerize the application.
2. Push the docker image onto AWS Elastic Container Registry.
3. Deploy application onto digital ocean kubernetes cluster.
4. Make changes to manifest files that trigger automated deployment onto argocd.

### Tools:

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
* Developer commits code to github
* Jenkins checks out code and runs script on Jenkinsfile.
* Jenkins builds docker image.
* Jenkins pushes image to docker registry.

### Prerequisites:

1. _Spin up Jenkins server_.
2. _Create Dockerhub Credentials_.
3. _Create Github Credentials_.
4. _Configure github and docker credentials in Jenkins Credentials store_.

### CI Steps:

1. Navigate to the Jenkins dashboard, create a workspace which you will use for your jobs.
2. Create a new "Pipeline" job. Lets call it "amazon-build-job". (The application is an amazon prototype).
3. On the configuration page, navigate to the Pipeline section, select Pipeline script from SCM.
4. On the SCM section, select GIT and paste your repository https url.
5. On the Credentials section, if your repository is public, no need to input anything, if its private , add your credentials for authentication.
6. Specify branches to build, if it is the main branch type " */main" , if it is master type " */master ".
7. Script path: type Jenkinsfile.
_Save and Apply. The job will appear on your workspace_.
8. Create another job, lets call it "argocd-manifest-amazon"
_The name of this second job is important as it should be the same as the the name given on stage(Trigger manifest Update") on buildjob of the Jenkinsfile_
9. Navigate to Datadog tagging, and select " This job is parameterized"
_Add a parameter, and select String parameter_
_The name of the parameter is given on the  stage(Trigger manifest Update") of the Jenkinsfile as DOCKERTAG_.
10. Navigate to the Pipeline section and selection " Pipeline Script from SCM" and choose Git
_Paste the second github repository url with the Jenkinsfile and manifest files. 
_Save and Apply_
_Both CI and CD Jobs are configured on Jenkins and should appear on your workspace_

11. Click on build now of the CI Job.

The CI Job should build successfully as below: 

  ![jenkins-CI-job](https://github.com/Noettie/End-to-End-automated-CI-CD-Pipeline-utilizing-GitOps-PART-ONE/assets/108426517/a97788b6-7665-4cc1-b11f-7d9a7a1607bc)


 

   




