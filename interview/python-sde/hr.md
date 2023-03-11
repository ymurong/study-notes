- [About Our Application in Production](#about-our-application-in-production)
- [My job as Tech Lead](#my-job-as-tech-lead)
- [Methodology and Management Tools](#methodology-and-management-tools)
- [Tech Skills](#tech-skills)
- [My New Master](#my-new-master)
  - [Motivation](#motivation)
  - [Master Courses](#master-courses)
  - [School Projects (Python Based)](#school-projects-python-based)
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
  - Refactoring by applying the SOLID principle and design patterns (NodeJS) 
    - Strategy, Chain, Composite, Singleton, Factory, Facade, Proxy
    - Error handling + Documentation (customer faced and technical faced, we show them on our admin UI)
  - New Features (NodeJS)
    - add event/messaging service (solace)
    - add scope based subscription with multiple identity provider support (subscribe-> request roles/scopes to service provider)
    - initiate the dashboard (more functional insights for billing/usage) -> technical insights we have dynatrace
  - Tooling (Python)
    - File transfer tool 
      - Agent will listen to PubSub's queue (new file arrival), push to local queue and use ThreadPoolExecutor to run file transfer jobs and ack when transfer is done correctly
      - Transfer records would be stored/updated in database and shown in UI (useful for debugging purpose)
    - Ansible Runner API (Flask)
      - A wrapper of ansible runner module that can be configured to run ansible playbooks through API and return results
      - Very useful when we have a large list of servers to configure/monitor
    - Cron Jobs via Cloud Function
      - update access tokens for our middleware every hour
      - enhance security by integrating Vault
  - Devops
    - Migrate from Jenkins to GitlabCI (scripting)
    - Migrate from AWS to GCP K8S (terraform + kustomize)
    - App Containerization (IAAS -> CAAS)
    - Complete CICD pipelines (Testing, Deploy)


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


## Master Courses
- Statistics and Optimizations: Inferential Statistics: parametric/non-parametric tests (anova, ancova, kruskal, etc), model diagnostics, uncertainty analysis, Integer Linear / Combinatorial / Simulation / Stochastic Dynamic Optimization
- Applied Machine Learning: text processing, classic ML, deep learning (computer vision)
- Applied Forecasting in Complex Systems: probabilistic and time series modeling
- Bigdata: distributed big data processing, programming models for parallelizable programs
• Causal Data Science: causal inferences modeling and testing
• NLP 1: fundamental techniques for a range of tasks in natural language processing (NLP), with a particular focus on statistical and machine learning approaches
• Information Retrieval 1: state-of-the-art techniques that constitute the core of information retrieval (IR) systems, such as search engines, recommender systems, conversational agents, etc.

My career motivation is Python software/data engineer in DSE (DS/AI/Data Engineering) domain. The master program equips me with not only theoretical background knowledge with optimization and statistics but also crucial foundational skills in terms of machine learning, deep learning and data engineering. What's more, the master also provides me with crucial people network with university researchers and professors in CV, NLP, BigData domain as well as skilled classmates who are passionate about AI/DS. Combined with my previous software engineering/devops skills and experience, I could become a valuable asset to future engineering teams in building AI products of the future.

## School Projects (Python Based)
The following projects requires familiarity with most common python libraries in data science, machine learning and deep learning. some projects are built with FastAPI framework. 
Neural-based projects are based on pre-trained models with fine-tuning

- CV: Food Image Recognition Multi-Class Classification with EfficientNet
- NLP: Question Answer Multi-Class Classification with Bert
- IR: Document Search Engine from Scratch (Traditional: TFIDF + BM25 + Neural: Bert cross-encoder, bi-encoder, sparse-retrieval)
- (FastAPI) Classic ML: Explainable/Fair Fraud Detection in Payment Industry - Adyen (Random Forest, XGBoost, LGBM, Voting)
- (FastAPI) BigData: Academic References Deduplication at Scale

Libraries: fastapi, pydantic, sqlalchemy, pickle, scipy, pytorch, transformers, numpy, pandas, duckdb, sklearn, nltp, networkx, fairlearn, lime, shap, etc



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


Data science master in University of Amsterdam, available beginning of Avril 2023 for job opportunities.

Related Projects:


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





