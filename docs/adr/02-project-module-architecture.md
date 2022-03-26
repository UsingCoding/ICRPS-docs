# Project module architectur

* Status: accepted
* Deciders: Techical committee

## Context and Problem Statement

Application should be divided into modules to exclude factor of "Big ball of mud".

## Decision Drivers

* Application should be easy to support
* New features should not break previous features
* Some modules may be disabled in feature, so it should be simple for developer to disable module
* Modular application is easy to test nether when everything put in one place


## Considered Options

* Modular monolith
* Microservice architecture

## Decision Outcome

Chosen option: "Modular monolith", because modular single appliction suitable for simple icrps site needs. Microservice architecture is more expensive and gives no benefits for current Project level, only expenses.

## Pros and Cons of the Options

### Modular monolith

PHP monolith divided into modules (contexts)

* Good, because no separate instance for new module needed
* Good, because easier to developer at the beginning. When project complexity not increases too much
* Good, because CI/CD for monolith **much** cheaper than for microservices
* Good, because we can still divide project into separate contexts
* Bad, because not so cool
* Bad, since it`s monolith on PHP

### Microservice architecture

Cluster of microsevices each of which responsible for separate context

* Good, because cool
* Good, because scalable
* Good, because techology agnostic. Any microservice can be written in any language
* Good, because makes commands works more independent
* Bad, because increases project complexity and entry threshold
* Bad, because CI/CD is **much** expensive
* Bad, because requires some orchestrator like Kubernetes
