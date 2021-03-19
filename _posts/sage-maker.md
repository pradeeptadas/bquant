---
toc: true
layout: post
description: Derivative rules for matrices.
categories: [cs]
title: Sage Maker
---

https://aws.amazon.com/sagemaker/faqs/

A. What is AWS Sagemaker?
AWS (or Amazon) SageMaker is a fully managed service that provides the ability to build, train, tune, deploy, and manage large-scale machine learning (ML) models quickly. Sagemaker provides tools to make each of the following steps simpler:

1. Explore and process data
    - Retrieve
    - Clean and explore
    - Prepare and transform
2. Modeling
    - Develop and train the model
    - Validate and evaluate the model
3. Deployment
    - Deploy to production
    - Monitor, and update model & data

The Amazon Sagemaker provides the following tools:
    - Ground Truth - To label the jobs, datasets, and workforces
    - Notebook - To create Jupyter notebook instances, configure the lifecycle of the notebooks, and attache Git repositories
    - Training - To choose an ML algorithm, define the training jobs, and tune the hyperparameter
    - Inference - To compile and configure the trained models, and endpoints for deployments

A.1. Why is SageMaker a "fully managed" service?
SageMaker helps to reduce the complexity of building, training, and deploying your ML models by offering all these steps on a single platform. SageMaker supports building the ML models with modularity, which means you can reuse a model that you have already built earlier in other projects.

A.2. SageMaker Instances - Important to Read
SageMaker instances are the dedicated VMs that are optimized to fit different machine learning (ML) use cases. The supported instance types, names, and pricing in SageMaker are different than that of EC2. Refer to the following links to have better insight:
    - Amazon SageMaker ML Instance Types - An instance type is characterized by a combination of CPU, memory, GPU, GPU memory, and networking capacity.
    - Amazon EC2 Instance Types - To have you know the difference in naming and combinations of CPU, memory, storage, and networking capacity.

A.3. Supported Instance Types and Availability Zones
Amazon SageMaker offers a variety of instance types. Interestingly, the type of SageMaker instances that are supported varies with AWS Regions and Availability Zones.
    - First, you need to check the List of the AWS Regions that support Amazon SageMaker.
    - Next, you can check the various available Amazon SageMaker ML Instance Types, again.

the ml.m4.xlarge is needed at an early stage, while ml.p2.xlarge is needed while Deploying a Sentiment Analysis Model.
https://docs.aws.amazon.com/general/latest/gr/rande.html#sagemaker_region

### Note
Sagemaker quotas, also referred to as limits, are very tricky. Every AWS user does not get the default quotas for SageMaker instances, which is why the last column shows a range, e.g., 0 - 20. The Default Quota depends on the instance type, the task you want to run (see table above), and also the region in which the Sagemaker service is requested. Refer this document having a caveat that new accounts may not always get the default limits.
https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html

B. Shut Down SageMaker Instances, if not in use
Note: We recommend you shut down every resource (e.g., SageMaker instances, or any other hosted service) on the AWS cloud immediately after the usage; otherwise, you will be billed even if the resources are not in actual use.


A. AWS Service Utilization Quota (Limits)
You need to understand the way AWS imposes utilization quotas (limits) on almost all of its services. Quotas, also referred to as limits, are the maximum number of resources of a particular service that you can create in your AWS account.
    - AWS provides default quotas, for each AWS service.
    - Importantly, each quota is region-specific.
    - There are three ways to view your quotas, as mentioned here:
        1. Service Endpoints and Quotas,
        2. Service Quotas console,
        3. AWS CLI commands - list-service-quotas and list-aws-default-service-quotas
    - In general, there are three ways to increase the quotas:
        1. Using Amazon Service Quotas service - This service consolidates your account-specific values for quotas across all AWS services for improved manageability. Service Quotas is available at no additional charge. You can directly try logging into Service Quotas console here.
        2. Using AWS Support Center - You can create a case for support from AWS.
        3. AWS CLI commands - request-service-quota-increase
        4. https://aws.amazon.com/about-aws/whats-new/2019/06/introducing-service-quotas-view-and-manage-quotas-for-aws-services-from-one-location/
        5. https://console.aws.amazon.com/support/home?#