


# About our application
We build a marketplace-type application that allows end-users of the whole company to manage, expose and subscribe to web services for internal and external clients with close integration with api management, messaging brokers as well as access management.

# My job
My role consists of not only technical aspects but also managerial tasks such as:
- Manage a team of 4 people ranging from frontend developer, backend developer, and vendor product expert. Participate in the recruitment of offshore members. Provide guidance to team members.
- Manage roadmap, prioritize tasks, decouple deliverables, and guarantee deadlines. 
- Communicate and coordinate with the product lead and other divisions to achieve shared objectives.


# Methodology and Tools
JIRA, Confluence, Agile....
Personal schedule: trello


# Tech Environment
Language: Nodejs, Python

GCP: 
- GKE: application runs on k8s (ingress + deployment)
- Cloud Function (Nodejs, update apigee token)
- Cloud storage: new file arrive -> trigger event to pubsub
- PubSub -> agent listen to event and write something to database
- Bigquery: cloud datawarehouse (ELT) -> streaming load
  - BQ ML

Devops:
- ansible 
- terraform
- cicd
- docker
- test driven


clean code:
- function name 
- explicit types 
- documentation
- pep8 format code
- design patterns

# New Knowledge 
- Machine Learning, Deep Learning, MLOps (feature stores, models etc...)
- data engineering: data cleaning, data quality, data drifts