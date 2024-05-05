# Clean Architecture : Patterns, Practices, and Principles

## Course Overview

* Clean architecture
* Domain-centric architecture
* Application layer
* Commands and queries
* Functional organization
* Microservices
* Testable architecture
* Evolving the architecture

## Introduction

### Overview

* Purpose
    * Philosophy of architectural essentialism
    * Set of patterns, practices, and principles
    * Alternative to traditional architecture

* Focus
    * Enterprise applications
    * Agile architecture

* Audience
    * Developers
    * Architects

* Prerequisites
    * Basic programming experience
    * Basic architecture experience

### What is Clean Code?

* What is Software Architecture?
    * High-level
    * Structure
    * Layers
    * Components
    * Relationships

* Levels of Architectural Abstraction
    * System
    * Sub-systems
    * Layers
    * Components
    * Classes
    * Data and Methods

* What is Bad Architecture?
    * Complex
    * Incoherent
    * Rigid
    * Brittle
    * Untestable
    * Unmaintainable

* What is Good Architecture?
    * Simple
    * Understandable
    * Flexible
    * Emergent
    * Testable
    * Maintainable

* What is Clean Architecture?
    * Architecture that is desgined for the inhabitants of the architecture... not for the architect... or the machine.

### Why invest in Clean Code?

* Why invest in Clean Architecture?
    * Cost/Benefit
    * Minimize cost
    * Maximize value
    * Maximize ROI

* Why Clean architecture?
    * Focus on the essential
    * Build only what is necessary
    * Optimize for maintainability

* What do architects do?
    * Context is king
    * All decisions are a tradeoff
    * Align with business goals
    * Use the best judgement

## Domain Centric Architecture

### Introduction to Domain Centric Architecture

* Database-centric architecture
    * UI
    * Business Logic
    * Data Access
    * Database

* Domain-centric architecture
    * Presentation + Persistence + Infrastructure
    * Application
    * Domain
    * Database

* Essential vs. Detail in Domain Centric Architecture
    * Domain is essential
    * Use cases are essential
    * Presentation is a detail
    * Persistence is a detail

* Examples of such architecture
    * Hexagonal architecture
    * Onion architecture
    * Clean architecture

* Why use Domain-centric architecture?
    * Pros
        * Focus on domain
        * Less coupling
        * Allows for DDD
    * Cons
        * Change is difficult
        * Requires more thought
        * Initial higher cost

## Application Layer

### Introduction to Application Layer

* What are Layers?
    * Levels of abstraction
    * Single-responsibility
    * Isolate roles and skills
    * Multiple implementations
    * Varying rates of change

* What does Application Layer do?
    * Implements use cases
    * High-level application logic
    * Knnows about the domain
    * No knowledge of other layers
    * Contains interfaces

* Layer dependencies
    * Dependency inversion
    * Inversion of control
    * Independent deployability
    * Flexible and maintainable

* Why use an Application Layer?
    * Pros
        * Focus on use cases
        * Easy to understand
        * Follows Dependency Inversion Principle
    * Cons
        * Additional layer cost
        * Requires extra thought
        * Inversion of Control is counter-intuitive


## Commands and Queries

### Introduction to Commands and Queries

* Command-Query Separation
    * Command
        * Does something
        * Should modify state
        * Should not return a value
    * Query
        * Answers a question
        * Should not modify state
        * Should return a value

* Command-Query Separation exceptions
    * Pop a stack
        * Remove item (command)
        * Return top item (query)
    * Create a new record
        * Create record (command)
        * Return new ID (query)

* Types of CQRS
    * Single database CQRS
        * Single database
        * Commands use domain
        * Queries use database
    * Two database CQRS
        * Read and write databases
        * Commands use write DB
        * Queries use read DB
        * Eventual consistency
        * Orders of magnitude faster
    * Event sourcing CQRS
        * Store events
        * Replay events
        * Modify entity
        * Store new event
        * Update read database
        * Complete audit trail
        * Point-in-time reconstruction
        * Replay events
        * Multiple read database
        * Rebuild production database

* Why use CQRS?
    * Pros
        * More efficient design
        * Optimised performance
        * Event sourcing benefits
    * Cons
        * Inconsistent across stacks
        * More commplex
        * Event sourcing costs

## Functional Organization

### Introduction to Functional Organization

* Why use Functional Organization?
    * Pros
        * Spatial locality
        * Easy to navigate
        * Avoid vendor lock-in
    * Cons
        * Lose framework conventions
        * Lose automatic scaffolding
        * Categorical is easier at first

## Microservices

### Introduction to Microservices

* What do microservices do?
    * Subdivide monoliths
    * Clearly-defined interfaces
    * Small teams
    * Independent

* How does microservices segregate?
    * Bounded context
    * Cohesion/coupling
    * Single domain of knowledge
    * Consistent data model
    * Independence
    * Microservice per aggregate root
    * Database per bounded context

* Why use microservices?
    * Pros
        * Flatter cost curve
        * High cohesion/ low coupling
        * Independence in development
    * Cons
        * Higher up-front cost
        * Conway's low
        * Distributed system costs

## Testable architecture

### Introduction to Testable architecture

* The current state of testing
    * Very little testing
    * Ineffective testing
    * Inefficient testing
    * Not enough time
    * Not my job
    * It's too hard

* Test Driven Development
    * Create a failing test
    * Get the test to pass
    * Improve the code
    * Repeat until functionality is completed

* Why Test Driven Development?
    * Comprehensive suite of tests
    * Drives testable design
    * More maintainable
    * Eliminates fear

* Types of Tests
    * Based on what to test
        * Unit tests
        * Integration tests
        * Component tests
        * Service tests
        * UI tests
    * Based on why to test
        * Functional tests
        * Acceptance tests
        * Smoke tests
        * Exploratory tests
    * Based on how to test
        * Automated tests
        * Semi-automated tests
        * Manual tests

* Test Automation Pyramid
    * Unit tests
    * Service tests
    * UI tests
    * Manual tests

* Acceptance tests
    * Verify functionality
    * Language of the business
    * Criteria for completeness
    * Full tests are problematic

* How to perform acceptance tests
    * Eliminate user interface
    * Eliminate database
    * Eliminate dependencies
    * Focus on the essential
    * Minimize coded UI tests
    * Smoke test instead
    * Minimize manual tests
    * Exploratory test instead

* Why Create Testable Architecture
    * Pros
        * Easier to test
        * Improves design
        * Eliminates fear
    * Cons
        * Higher up-front cost
        * TDD requires discipline
        * Requires team buy-in
