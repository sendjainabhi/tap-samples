# Tanzu Application Platform Samples
This repo provide the Tanzu application platform application accelerator and various ready to use samples.

## Prerequisites
To use these Application Accelerators samples you need to have access to an installation of VMware Tanzu Application Platform.

## How does Application Accelerators work?
Application Accelerators allow you to generate new projects from files in Git repositories. An accelerator.yaml file in the repository declares input options for the accelerator. This file also contains instructions for processing the files when you generate a new project.

## Register accelerator with Tanzu developer portal 
You can follow below instruction to deploy custom accelerator into tanzu developer portal 
```
# Register accelerator with public git repo 

#execute following command 
tanzu accelerator create simple --git-repository ${GIT_REPOSITORY_URL} --git-branch ${GIT_REPOSITORY_BRANCH}

#sample  
tanzu accelerator create spring-ai-chat --git-repository https://github.com/sendjainabhi/tap-samples/tree/main/spring-ai-chat --git-branch main

# Register accelerator with private git repo 

# create private git repo secret

kubectl create secret generic <secret name> \
    --namespace accelerator-system \
    --from-literal=username=<git user> \
    --from-literal=password=<git repo token>

# apply custom accelerator yaml file on tap k8 cluster
kubectl apply -f <file path of accelerator.yaml>

```

