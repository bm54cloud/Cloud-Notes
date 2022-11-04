# **Continuous Delivery & DevOps**

## Continuous Delivery Pipeline
Small unit tests --> Medium/Integration tests --> Large/System tests --> Manual Validation --> Deployment
- Large (System) Tests have many names
    - Functional tests
    - Non-functional tests
    - Acceptance tests
    - Contract tests
    - System tests
    - End-to-end tests
- May do Performance tests to make sure product performs under high load of users
- May do Security tests 

## What is DevOps?
- DevOps is a way to get a more continuous capability in your pipeline
- Helps streamline the workflow between developers, testers, and operates
- Interdisciplinary teams (members from all three) may make the pipeline flow better
- Focus on automation across all three parts 

## The Job of Development in DevOps


## The Job of Test in Devops
- Developers are writing unit tests, small tests
- Progressive delivery is popular; move new features and new content to production but turn this off so that customers can’t use it; then turn on for certain customers to make sure it is working properly
- Black box testing (give input, it generates expected output)
- White box testing is everything else, paying attention to how the software is actually implemented

## The Job of Ops and Devops
- Creating resources to run the software on and keeping that software running
- Ops teams are creatinine an infrastructure that that dev teams can upload their product to and test
- Thus instead of the Ops team actually doing those upgrades, they’re creating a common infrastructure that makes sense for everybody to use
- Can use a 3rd party server like AmAzon or Heroku or a Google Cloud engine to run the software on (called serverless)
- Site reliability engineer (SRE) is a job that focuses on automating and standardizing whatever it is your company is trying to do by to bring resources online, update custom code, update common code, etc, using online automation tools to do this

