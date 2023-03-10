- [About Our Application in Production](#about-our-application-in-production)
- [My job as Tech Lead](#my-job-as-tech-lead)
- [Methodology and Management Tools](#methodology-and-management-tools)
- [Tech Skills](#tech-skills)
- [My New Master](#my-new-master)
  - [Motivation](#motivation)
  - [New knowledge](#new-knowledge)
- [How to keep Tech Update](#how-to-keep-tech-update)
  - [Sources](#sources)
    - [Casual Discovery](#casual-discovery)
    - [Self Learning](#self-learning)
    - [Summarization and Revise](#summarization-and-revise)
  - [Time](#time)
- [Questions](#questions)


# About Our Application in Production
We build a marketplace-type application that allows end-users of the whole company to manage, expose and subscribe to web services for internal and external clients with close integration with api management, messaging brokers as well as access management.

# My job as Tech Lead
- Management Contributions
  - Manage a team of 4 people ranging from frontend developer, backend developer, and vendor product expert. Participate in the recruitment of offshore members. Provide guidance/coaching to team members
  - Together with product lead, manage roadmap, prioritize tasks, decouple deliverables, and guarantee deadlines. 
  - Communicate and coordinate with the stakeholders, product lead and other divisions to achieve shared objectives.


- Tech Contributions
  - Devops (Jenkins -> Gitlab CI,  AWS -> GCP, IAAS -> CAAS, complete CICD pipelines (testing, deploy -> dev, qa, prod))
  - Refactoring 
    - Many Nodejs from frontend and are not accustomed to proper OOP -> hard to maintain
    - [Design Pattern](../../system-design/design-pattern.md) 
    - Error handling + Documentation (customer faced and technical faced, we show them on our admin UI)
  - New Features
    - add event/messaging service (solace)
    - add scope based subscription with multiple identity provider support (subscribe-> request roles/scopes to service provider)
    - initiate the dashboard (more functional insights for billing/usage) -> technical insights we have dynatrace
  - other miscellaneous projects
    - Python: File transfer tool (cloud based)
      - daemon agent in python
      - cloud storage (new file trigger event) -> pubsub(listener) -> write to database -> UI (existing module -> transfer history)
    - Python: Ansible Runner API (automatic monitoring/config of nginx servers)
    - Java: Middleware custom extension (authentication module)
    - RabbitMQ Config API POC (not really used as we found it is better to use Gitlab with terraform and bash/python)
    - cloud function project (update apigee access token to our vhosts)


# Methodology and Management Tools
JIRA(KANBAN-> Sprints), Confluence(Documentation), Agile(Planning, Daily Standup, Retro)...
Personal schedule: Trello


# Tech Skills
Language: Nodejs, Python

GCP: 
- GKE: application runs on k8s (kustomization + kubectl, ingress + deployment)
- Cloud Function (Nodejs, update apigee token)
- Cloud storage: new file arrive -> trigger event to pubsub
- PubSub -> agent listen to event and write something to database
- Bigquery: cloud datawarehouse (ELT) -> streaming load
  - Strong skill in SQL/PL/SQL, my previous master is about analytical engineering ( Oracle (triggers, stored procedure ...) + SAP BO (dimensional modelling))
  - cloud datawarehouse (new to me but willing to learn, very interested in it)
  - Bigquery ML (good machine learning knowledge from school and practicals)

Azure:
- really want to learn...

Devops:
- CICD (daily)
- Docker (daily)
- TDD (daily)
- Ansible (extensive experience in deploying/configuration with a suite of middlewares) -> not like it very much
- Terraform (less experienced as not infrastructure engineer, mainly use it to manage resources for application needs)

Middleware:
- API Mananger, ESB
- IDP
- Vault


Database:
- Postgres (oltp)
- Sqlite (embedded oltp)
- Duckdb (embedded olap)
- NoSQL (only used in school but want to try, such as redis, mongo, dynamoDB, cassandra, elastic)


Data Pipeline:
- Spark
- Airflow (want to learn)

Broker:
- RabbitMQ
- Kafka (want to learn)

Clean, scalable & efficient code:
- Clean, Maintainable
  - OOP: SOLID + design patterns
  - function name 
  - explicit types 
  - documentation
  - pep8 format code
- Scalable code (server level???)
  - horizontal scalability 
  - cache
  - statelessness
  - functional programming
    - pure function -> same input, same output
- Efficient
  - appropriate algo: time & space complexity
  - using functions, class properly
  - eliminate unessential operations
  - minimal use of ifelse
  - avoid declaring unnecessary variables
  



# My New Master
## Motivation
- UVA is the father of python (Guido van Rossum)
- UVA has very high ranking in terms of AI, Data Science and computer science in general (top 10 in Europe)
- Python software/data engineer in DSE domain, empirical oriented
- Theoretical background knowledge with optimization and statistics
- usually skilled software engineers are unwilling to work on nodejs/python (less jobs, less paid, language issues/preference...???)


## New knowledge
- Machine Learning, Deep Learning, MLOps (feature stores, models etc...)
  - pretrained model with Computer Vision/NLP (school projects: most work in preprocessing, evaluation and tuning, actually really engineering oriented)
  - numpy, pytorch, panda, sklearn, scipy, networkx, nltk, PIL
  - image preprocessing (padding, data augmentation, CNN, Pooling, Relu)
- data engineering: data cleaning, data quality, data drifts
  - duckdb (olap), spark
  - References deduplication (fastapi)
  - Adyen: fraud detection (fastapi)
- ignore other more statistical/analytical knowledge (causal, graph)

# How to keep Tech Update
## Sources
### Casual Discovery
- Medium
- Youtube Channels (do have some serious content in a easy way)
- Github Followers
- Linkedin (So many marketers...)
- Wechat channels (only chinese)

### Self Learning
- Youtube Channels (do have some serious content in a easy way) but not complete and usually for beginners
- Serious stuff: Leetcode, http://highscalability.com/,  Algoexpert, Frontendmasters, Coursera, Udemy, Kaggle, Some websites, Books

### Summarization and Revise
- Really important to summarize otherwise would forget really quick and need to google every time
- Keep Blogs or Markdown Notes

## Time
- half day learning, friday afternoon (continuous) 
- weekend (if really necessary for jobs, otherwise not)


#  Questions
- location: paris? travel?
- salary currency, base salary ? stock options?
- transport allowance (1k/year), meal allowance? (1.5k), medical insurance (mutuelle)
- vacations: 25+10 RTT? extra?
- salary -> management style? churn rate problem? work overtime? 
- laptop ?
- company status quo? vision? 





