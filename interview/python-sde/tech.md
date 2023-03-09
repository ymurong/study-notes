- [Tech Details](#tech-details)
  - [API Framework](#api-framework)
  - [Python vs Node](#python-vs-node)
    - [Python](#python)
    - [Nodejs](#nodejs)
      - [Tricky Concepts about JS](#tricky-concepts-about-js)
        - [Lexical Scopes (Static Scope)](#lexical-scopes-static-scope)
        - [Closure](#closure)
        - [Hoisting](#hoisting)


# Tech Details
## API Framework
FastAPI:
- pydantic (schema)
- sqlalchemy (orm)
- background_task (cron)
- sklearn
- pickle
- pytorch
- numpy
- panda
- pyspark
- duckdb
- unidecode
- scipy (online statistical testing)
- evidently (more industrialized data drifts detection, model monitoring)
- dedupe (deduplication)
- fairlearn (model fairness)
- lime, shap (model explaination)
- dowhy (causal)

Express:
- joi
- got
- node-cache
- cron
- sequelize
- websocket (forbidden security)


## Python vs Node
### Python
Python has much more and better libraries for various data mangling tasks, be it BI, data science, scientific computing, machine learning etc

### Nodejs
Due to its event-driven, single-threaded event loop and asynchronous non-blocking I/O model, Node.js performs best on intense I/O applications requiring speed and scalability with lots of concurrent connections, like video & audio streaming, real-time apps, live chats, gaming apps, collaboration tools, or stock exchange software.

Node has more and better libraries for streaming a/v and other buffery stuff, real-time networking, web sockets etc

#### Tricky Concepts about JS
##### Lexical Scopes (Static Scope)
- Lexical Scopes
- Arrow Function with Lexical Scopes


##### Closure
The closure is when a function "remembers" its lexical scope even when the function is executed outside that lexical scope. It preserves the link to a variable.

##### Hoisting
- var and function declaration hoist
- const, let don't hoist, TDZ error
- function expression don't hoist (assignment part)
