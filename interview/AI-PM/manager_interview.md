# self intro

Currently I am on gap year, doing my master on data science in UVA. Besides, I already have a master in information system specialised in BI/Data Engineering in France and a business licence in china.

Before the gap year, I am a Tech Lead / Tech product owner in Renault in charge of an IT marketplace application that allows developers of the whole company to manage/subscribe/expose the contracts of web services, aka: api/event. 

The application we build 
5951 users, 12996 active subscriptions, 1464 consumers in production


# Product Details (One Example)
Two subjects I have been responsible on (Scope based access management, New Event Contract Life Cycle)

- Scope based access management
  - Situation: New Identity Server (Okta)
  - Task: 
    - Assumption: Current system do not support the New Identity Server. If we evolve our current access management module wen can support a smooth transition and accelerate the process new IDP adoption. (5 why)
    - Why new access management system 
      - Tech Constraints
        - from Role-based -> Scope-based (tech constraint)
        - syncrhonous -> asyncronous (tech constraint)
      - User Perspectives
        - Better visibility/fine control of API Access
        - Vulgariser l'usage
  - Action:
    - Think Big: Feature design and estimation (business value, tech feasibility, time-to-market) together with Dev team, IDP team and User Representatives Team from each DIR
    - Communication with API Governance/Security (manage expectations and progress)
    - Start Small to show early wins (Declarative -> UX, Full Automation -> Tech): Dev Organization: Big Epic -> Sprints -> Spike
  - Results: 
    - Simplified Scope Life cycle management for service creators and service subscribers (Full Visibility of Scopes and its status, Automated Workflow, Dashboard show Migration Progress, etc)

# Exciting features (Simple Idea but Big Value)
- Before (what)
  - Contract Edit Panel with different environments (4 environments)
- Before (Why）
  - Personal Feeling + Interview with Key Users with open questions
  - Low efficiency
  - Human error

- During:
  - What:
    - Two-sided Edit Panel with comparator between different environments with highlights of differences
  - Why:
    - low difficulties (existant UI module)
    - improve efficiency and lower the human error

- Afterwards:
  - How: many key users found the features really useful
    - they don't need to open two pages ....
    - they know exactly the differences between two contracts and dont need to figure them out themselves


# WildCard Topic Search Bar in Subscription Form
Problem: Managers Not familiar with Wildcard (people just go nuts and put * everywhere)
- make sure user entry correct and understand what are the topics they are gonna subscribe for otherwise would be refused by service providers


Service Discovery:
    - Soft matching retrieval (service description, ...)


# Questions
1. Major Clients (internes/externes) of BU Data SMB: Internal Marketing/Finance/HR, Internal DS/AI team? External SAAS Solution: GED?
2. About Tech Team (how many people, DE, DEV, Devops, Analysts, MLE)
3. Major expectation of this role (data product owner)
4. Can I know more about the AI recommendation engine (codename : "d’Artagnan"), why do we need this AI recommendation engine? any pain points that we need AI to solve?
5. How closely is maileva with other filiales in docaposte, like I heard those projects related to european wallet, numspot european cloud provider, docaposte just bought idemia's electrical signature business, do we have something to do with it?
6. Documents summarizations?



# Recommender system
## Content based recommender has three main components
- content analyzer -> content representation
- profile learner -> user preference representation 
- filtering and recommendation -> matching user preference representation to the content representation
- new trends:
  - knowledge graphs
  - user generated content 
  - multimedia sources

### Advantages
    - user independence
    - transparency
    - new items

### Problems 
  - new user: not enough interactions (cold start)
  - limited content analyzer (automatic/manual features not enough to distinguish items)
  - overspecialization: solely relies on the interests of the target user

## Collaborative filtering
using the similarities between users and items to provider recommendations 

- neighborhood based
  - user based: similar users has similar ratings on the same items (serendipity-> unexpected recommendation)
  - item based: similar items are rated in the similar way by the same user (justifiability)


- model based
  - matrix factorization (latent features k: MxK @ KxN, M users, N items)


- Neural based model
  - non-linear
  - sequence (temporal)
  - representation

