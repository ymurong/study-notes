
- [Table of Contents](#table-of-contents)
  - [Design Patterns Types](#design-patterns-types)
  - [Behavioral Patterns](#behavioral-patterns)
    - [Strategy](#strategy)
      - [Analogy](#analogy)
      - [OOP Structure](#oop-structure)
    - [Chain](#chain)
      - [OOP Structure](#oop-structure-1)
    - [Observer](#observer)
      - [OOP](#oop)
    - [State](#state)
    - [Iterator](#iterator)
    - [Mediator](#mediator)
    - [OOP](#oop-1)
  - [Creational Patterns](#creational-patterns)
    - [Factory Method](#factory-method)
      - [OOP Structure](#oop-structure-2)
    - [Singleton](#singleton)
    - [Prototype](#prototype)
  - [Structural Patterns](#structural-patterns)
    - [Facade](#facade)
    - [Adapter](#adapter)
    - [Decorator](#decorator)
    - [Composite](#composite)
    - [Proxy](#proxy)
  - [My Experience](#my-experience)
    - [Strategy + Chain + Composite](#strategy--chain--composite)
    - [Factory](#factory)
    - [Singleton](#singleton-1)


# Table of Contents
## Design Patterns Types
- Creational patterns
- Structural patterns
- Behavioral patterns

## Behavioral Patterns
### Strategy
Strategy is a behavioral design pattern that lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.

#### Analogy
Imagine that you have to get to the airport. You can catch a bus, order a cab, or get on your bicycle. These are your transportation strategies. You can pick one of the strategies depending on factors such as budget or time constraints.

#### OOP Structure
Context Class -> Strategy Interface <- Concret Strategy Class

- Context Class select which strategy based on context
- Context.doSomething(data) would run selected strategy


### Chain
Chain of Responsibility is a behavioral design pattern that lets you pass requests along a chain of handlers. Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.

#### OOP Structure
ChainStrategy(Client) -> Abstract Role Handler <- Concrete Role Handler

- ChainStrategy setup all the needed handlers and defines the chain rule by using handler.setNext()
- the handler will call next handler to execute if it can not handler the request


### Observer
Observer is a behavioral design pattern that lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

#### OOP
Publisher -> Subscriber

### State
State is a behavioral design pattern that lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.

### Iterator 

### Mediator
Mediator is a behavioral design pattern that lets you reduce chaotic dependencies between objects. The pattern restricts direct communications between the objects and forces them to collaborate only via a mediator object.

### OOP
The Mediator interface declares a method used by components to notify the
mediator about various events. The Mediator may react to these events and
pass the execution to other components.

## Creational Patterns
### Factory Method
Factory Method is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

####  OOP Structure
Factory <- Concrete Product

### Singleton
Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.

### Prototype
Prototype is a creational design pattern that lets you copy existing objects without making your code dependent on their classes.

## Structural Patterns
### Facade
Facade is a structural design pattern that provides a simplified interface to a library, a framework, or any other complex set of classes.

### Adapter
Adapter is a structural design pattern that allows objects with incompatible interfaces to collaborate.

### Decorator
Decorator is a structural design pattern that lets you attach new behaviors to objects by placing these objects inside special wrapper objects that contain the behaviors.

### Composite
Composite became a pretty popular solution for the most problems that require building a tree structure. Composite’s great feature is the ability to run methods recursively over the whole tree structure and sum up the results.

### Proxy
Proxy is a structural design pattern that lets you provide a substitute or placeholder for another object. A proxy controls access to the original object, allowing you to perform something either before or after the request gets through to the original object.

## My Experience
### Strategy + Chain + Composite

Oauth2 Token contains the roles of a user (admin, api-ref, user ...). Each role represents different access. Api-ref don't have access to Admin resources.

2 strategies we need: 

- Default Strategy (Composite)
  - for loop all matched role handlers
- Chain Strategy
  - predefined chain rule: admin -> apiref -> user


### Factory
A new identity provider comes and our api system need to maintain two identity provider on the same time based on incoming oauth2 token. Different identity provider needs different implementation in terms of identity verification

- AuthFactory -> Abstract Authenticator <- Concrete Authenticator
- AuthFactory would deliver NetiqAuthenticator and OktaAuthenticator based on the incoming token issuer at runtime


### Singleton
- DBConnector (Connection pool)
- Cache



