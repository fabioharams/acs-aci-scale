# High scale kubernetes on Azure Container Services using Azure Container Instances

This document will help you to deploy Azure Container Instance on Kubernetes cluster (running on Azure Container Service). 
Azure Container Instance (ACI) allow to run containers directly on Azure, without the requirement to deploy hosts. You can find more information about this resource [here](https://azure.microsoft.com/en-us/services/container-instances/).

Note: until the date of this documentation (September 21 - 2017) the ACI feature is on Preview. Check the link above about more updates.

## Architecture

This deployment use ACI Connector to scale Pods, Deployments and Jobs to Azure Container Instance service. After the installation of the ACI Connector (using an YAML file) you will see the ACI Connector as an additional node.

![kubectl get node](./img/1.PNG)

Also you can check the ACI Connector as a Deployment and Pod

![deployment and pod](./img/2.PNG)

Using YAML to deploy on Kubernetes just add the parameter **nodeName** (use the name of the connector) to **Spec** field:

![yaml](./img/3.PNG) 

Diagram about the structure

![diagram](./img/4.PNG)


## Requirements

1. Deploy Kubernetes on ACS:

https://github.com/fabioharams/kubernetes

2. Deploy ACI Connector on Kubernetes

https://github.com/Azure/aci-connector-k8s

