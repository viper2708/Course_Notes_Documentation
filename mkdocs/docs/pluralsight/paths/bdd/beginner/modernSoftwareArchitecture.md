# Modern Software Architecture: Domain Models, CQRS, and Event Sourcing

## DDD at a Glance

### Introduction

* Key Points
    * Repositioning Domain-Driven Design
    * Exploring Supporting Architectures
    * UX-first Design Methodology

### DDD in History

* Domain-Driven Design in History
    * Introduced 10+ years ago by Eric Evans
    * Primary intent of tackling complexity in the heart of software
    * Innovative guidelines and approach to design

* Where does the complexity comes from?
    * Big Ball of Mud (BBM)
        * A system that's largely unstructured, padded with hidden dependencies between parts, with a lot of data and code duplications and an unclear identification of layers and concerns - a spaghetti code jungle

### DDD Today

* Why is DDD so Intriguing?
    * Captured known elements of design process
    * Organized them into set of principles
    * Made domain modeling the focus of development
    * Different approach to building business logic

* DDD is still about the business logic
    * Crunch knowledge about the domain
    * Recognize subdomains
    * Design a rich domain model
    * Code by telling objects in the domain model what to do

* Supreme Goal of DDD
    * Tackling complexity in the heart of software
    * DDD represents a significant landmark in software development
        * Took root in the Java space
        * Blissfully ignored in .NET until recently
    * DDD is more about analysis than about actual coding strategies
    * The main focus of DDD has shifted
        * Discovering the domain architecture more than organizing the business logic
        * Domain Model remains a valid pattern to organize the business logic but other patterns can be used as well like:
            * Object-oriented models
            * Functional models
            * CQRS
            * Classic 3-tier
            * 2-tier

### DDD Misconceptions

* Common summary of DDD
    * Build an object model for the business domain
        * Call it a "domain model"
    * Consume the model in a layered architecture
        * 4 layers, business logic split and renamed
        * Application layer and domain layer
    * DDD has two distinct parts. One is always needed but the other can be happily ignored
        * Analytical
            * Valuable to everybody and every project
        * Strategic
            * One of many supporting architectures

## Discovering the Domain Architecture through DDD

### Ubiquitous Language

* What is Ubiquitous Language
    * Vocabulary of domain-specific terms
        * Nouns, verbs, adjectives, idiomatic expressions and even adverbs
    * Shared by all parties involved in the project
        * Primary goal of avoiding misunderstandings
    * Used in all forms of spoken and written communication
        * Universal language of the business as done in the organization

* Motivation
    * People use different languages
    * Common terminology
    * Help making sense of user requirements

* Definition
    * Natural language, not artificial
    * Comes out of interviews and brainstorming
    * Iteratively composed and refined along the way
    * Unambiguous and fluent
        * Meets expectation of domain experts
        * Meets expectations of technical people

* Ubiquitous language used in
    * User Stories and RFC
    * Meetings
    * Emails
    * Technical documentation
    * Schedule
    * Source Code

* Structure
    * List of terms saved to Office documents
        * Glossary of terms fully explained
        * Made available to everyone
        * Part of the project documentation
    * Continuously updated
        * Responsibility of the development team

### Defining the Ubiquitous Language

* Use the language model as the backbone of a language
    * Discovering the ubiquitous language
    * Leads you to understand the business domain
    * In order to design a model
    * Any model works. Not necessarily an object-oriented model

* Ubiquitous Language
    * Words and verbs that truly reflect the semantics of the business domain
    * No ambiguity
    * No synonyms

### Ubiquitous Language Tips

* Dealing with acronyms
    * Domain-specific
    * Hard to remember
    * Avoid if possible

* Ubiquitous language is in sync with the code

* Scenarios where Ubiquitous Language is key to have
    * Really a lot of domain logic is tricky to digest
        * Ensures all relevant terms are understood
        * No other term is used to indicate same/similar concepts
    * Business logic not completely defined
        * Business is young and growing with the system (i.e. startup)
        * Domain logic discovered along the way

* Ubiquitous language in Code
    * Naming conventions
        * Classes
        * Members
        * Namespaces
    * Extension methods
        * Domain-specific language
        * C#, Java, Kotlin
    * Tools
        * Code assistants
        * Refactoring tools
        * Gated check-ins
    * Agnostic
        * No mandated technology
        * No mandated paradigm

### Bounded contexts

* What is bounded contexts?
    * Delimited space where an element has a well-defined meaning
        * Any elements of the ubiquitous language
    * Beyond the boundaries of the context, the language changes
        * Each bounded context has its own ubiquitous language
    * Business domain split in a web of interconnected contexts
        * Each context has its own architecture and implementation

* Motivation for bounded contexts
    * Remove ambiguity and duplication
    * Simplify design of software designs
    * Integration of external components

### Discovering bounded contexts

* Bounded contexts
    * Ubiquitous language
    * Independent implementation (eg. CQRS)
    * External interface (to other contexts)

* Integrity at risk without bounded contexts
    * Same term that means differently to different people
    * Same term to indicate different elements
    * Dependency on external subsystems
    * Dependency on legacy code
    * Functional areas of the application that are better treated separately

### Context mapping

* Web of Bounded Contexts
    * Systems may result from the composition of multiple contexts
    * Number of bounded context often reflects physical organization

* What is Context Map
    * Context map is the diagram that provides a comprehensive view of the system being designed
    * Direction of relationship
        * Upstream context influences
        * Downstream context
        * Aspects being influenced
            * Binaries
            * Schedule
            * Request-for-changes

### Event storming

* What is event storming
    * Exploring a business domain starting from observable domain events
    * Developers and domain experts together in a meeting room

* How it works
    * Identify relevant domain events
        * Use a sticky note of a given color to put events on the wall
    * Find what causes the event
        * User action? Add a sticky note of a different color
        * Asynchronous event? Add a sticky note of a different color
        * Another event? Add another sticky note of same color on top
    * Look at the modeling surface as a timeline
        * Add notes with markers
    * Facilitator
        * Leads the meeting
            * Starts the meeting asking questions
            * Sticks first notes on the wall to show the way
        * Guides the modeling effort
            * Asks questions to better understand the emerging model
            * Ensure ideas are represented accurately
            * Keep focused and moves ahead

* Benefits
    * Comprehensive vision of the business domain
    * Bounded contexts and aggregates in each context
        * Aggregate handles commands and controls persistence
    * Types of users in the system
        * Personas who runs command and why
    * Where UX is critical
        * Sketches of relevant screens

## The DDD Layered Architecture

### Introduction

* Key points
    * Layers and tiers
        * Segmentation of a Software system
    * Domain layer
        * Patterns for organizing the Business Logic
    * Other Layers
        * From Persistence to Presentation

### The Layers of a Software System

* Spaghetti-code vs. Lasagna-code
    * Spaghetti-code : Messy tangle of instructions leading nowhere near to any flicker of solid software.
    * Lasagna-code : Layered block of modules easy to cut vertically and/or horizontally and easy to deploy.

* Layered architecture
    * Presentation layer -> UX
    * Application layer -> Use-cases
    * Domain layer -> Business
        * TX Script
        * Table module
        * Domain model
        * CQRS
        * Event sourcing
    * Data layer -> Persistence
        * Relational
        * NoSQL
        * Memory

### The Presentation Layer

* What is presentation layer?
    * Responsible for providing the user interface to accomplish any required tasks
    * Responsible for providing an effective, smooth and pleasant user experience

* Attributes of presentation layer
    * Task based
    * Device-friendly
    * User friendly
    * Faithful to real-world processes

### The Application Layer

* What does application layer do?
    * Reports to the presentation
        * Serves ready-to-use data in the required form
    * Orchestrates tasks triggered by presentation elements
        * Use-cases of the application's frontend
    * Doubly-linked with presentation
        * Possibly extended or duplicated when a new frontend is added
