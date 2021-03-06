# Deploying a Modern Reactive Serverless Microservice to the Cloud 
### (*Note* Due to the limited time of the Build Stuff 2020 Workshop, the hands-on lab will only cover the OpenShift setup, the creation of the Reactive Java Vert.x application, and the deployment of the application.  The rest of the info and exercises in this guide are intended as an optional "take-home" lab, as you will have up to 24 more hours to access the complimentary OpenShift cluster.)

## Learning objectives

This workshop is all about creating and deploying a reactive Java app as a Knative service on OpenShift. After this workshop you learned how to:

* Create a Reactive Java application using Vert.x
* Deploy this application as Knative service
* How to create and use OpenShift pipelines to deploy your app   (*Extra info as optional "take-home" exercise)
* How to leverage Quarkus to create reactive Java applications   (*Brief intro without the exercise)

Let's start with exploring Knative a bit more...

## Why is deploying a Knative service easier than a Kubernetess deployment? 

![Knative Logo](openshift/images/knative-logo.png)

Knative is a framework running on top of Kubernetes that makes it easier to perform common tasks such as scaling up and down, routing traffic, canary deployments, etc. According to the Knative web site it is "abstracting away the complex details and enabling developers to focus on what matters. It solves the 'boring but difficult' parts of deploying and managing cloud native services so you don't have to."

## What is Knative? 

It is an additional layer installed on top of Kubernetes. 

It has two distinct components, originally it were three. The third was called Knative Build, it is now a project of its own: [Tekton](https://tekton.dev/). 

* __Knative Serving__ is responsible for deploying and running containers, also networking and auto-scaling. Auto-scaling allows scale to zero and is probably the main reason why Knative is referred to as Serverless platform.
* __Knative Eventing__ allows to connect Knative services (deployed by Knative Serving) or other Kubernetes deployments with events or streams of events.

This workshop will **focus on a quick deployment using Knative Serving** and will cover the following topics:

1. Prerequisites (access to an OpenShift cluster, work environment, etc.)

1. Installing the required OpenShift Operators

1. Create, change and deploy a Vert.x example app as Knative service

[The followings are extra info for optional "take-home" exercises]

1. Create an OpenShift pipeline and deploy your Vert.x app with it   

1. Creating a Knative Revision

1. Traffic Management

1. Auto-Scaling

1. Create a reactive Java application using Quarkus

Click the link below to get started & have fun!! Happy coding :smiley:

---

**[OpenShift Serverless on Red Hat OpenShift on IBM Cloud](openshift/1-Prereqs.md)**

To complete this workshop, basic understanding of Kubernetes/OpenShift and application deployment on Kubernetes is instrumental!

---

## Tools:

In this workshop we will be using the IBM Cloud Shell which has all required tools installed.

Should you prefer to run the workshop completely off your own workstation you need the following tools.

Tool  |Source       
----------------|----
git CLI|https://git-scm.com/downloads 
ibmcloud CLI|https://cloud.ibm.com/docs/cli?opic=cli-install-ibmcloud-cli
ibmcloud plugin|https://cloud.ibm.com/docs/cli?topic=cli-plug-ins -- Install kubernetes-service plugin
oc|Download from OpenShift Web Console, click on question mark
kn|https://knative.dev/docs/install/install-kn/
hey|HTTP Load generator: https://github.com/rakyll/hey

## Resources:

You can find detailed information and learn more about Knative here:

1. [Knative documentation](https://knative.dev/docs)

1. [Quarkus Getting Started](https://quarkus.io/get-started/)

1. [Red Hat Knative Tutorial](https://redhat-developer-demos.github.io/knative-tutorial/knative-tutorial/index.html)

1. [Deploying serverless apps with Knative (IBM Cloud Documentation)](https://cloud.ibm.com/docs/containers?topic=containers-serverless-apps-knative)

1.  A series of blogs on Knative:
      - [Serverless and Knative – Part 1: Installing Knative on CodeReady Containers](https://haralduebele.blog/2020/06/02/serverless-and-knative-part-1-installing-knative-on-codeready-containers/)
      - [Serverless and Knative – Part 2: Knative Serving](https://haralduebele.blog/2020/06/03/serverless-and-knative-part-2-knative-serving/)
      - [Serverless and Knative – Part 3: Knative Eventing](https://haralduebele.blog/2020/06/10/serverless-and-knative-part-3-knative-eventing/)
      - [Knative Example: Deploying a Microservices Application](https://haralduebele.blog/2020/07/02/knative-example-deploying-a-microservices-application/) -- The YAML files for this example are in the `code-nodejs/cloud-native-starter` directory


