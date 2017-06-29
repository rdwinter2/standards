# Software Development Lifecycle


Flow's Software Development Lifecycle (SDLC) is focused on creating an amazing environment for individuals and teams to contribute safely to Flow's growth. One pillar of our culture is trust and empowerment - and our SDLC is informed by and designed to demonstate and further this value.

## Philosophy

We pursue several practices to ensure our SDLC achieves its goals of providing very high productivity while continually reducing risk.

  - We remind ourselves constantly that **failure is a mandatory component of success**. As people, learning and failure go hand in hand.
  
  - Not all failures are created equal. We use the word **Intentionality** to describe an intentional change to a system. In particular, failures that result from intentional changes are the changes we expect to learn from; by contrast, a lack of intentionality leads to negligence or carelessness which erodes trust and therefore is contrary to our culture.
  
  - We **learn and adapt from prior learnings**; In particular, from Kaizen, we adopt the learnings of continuous improvement. When failure occurs, we immediately determine what needs to be done to prevent recurrence and focus on those tasks. We learn about antifragile - the notion that following each learning, we emerge stronger as an organization for the future. We learn from Scrum and Kanban ways to organize our work; but we also learn their shortcoming and adjust appropriately for our environment.
  
  - We focus on software and architecture that continually reduces the risk of changes. These practices focus on:
  
    - isolation - truly ensuring that one change cannot impact another. For example, our focus on API design and micro service architecture on the backend is one technique we use to create isolation.
    
    - continuous delivery - by releasing small changes continuously to our production environment, we minimize the impact of any one change and significantly decrease time to resolution.
    
    - automation - by writing software to manage and implement our processes - including testing, patching and deployment - we focus on capturing our assumptions during the development process and building leverage to ensure our assumptions remain valid over time.
    
    - rollback - by ensuring that every application change can be rolled back, we enable faster resolution when problems arise. For example, our practice of managing database schema changes independently of application changes provides the means to ensure every application change can itself be rolled back.
    
    - incremental rollout - by rolling out application changes to production incrementally, and verifying that they work, we minimize the impact of a problem before it affects all of our users.
    
    - monitoring and alerting - by instrumenting our applications - via logging and external monitoring services - we can capture our assumptions and receive notification on variance to minimize customer impact.

    - secure by design - We consider security throughout the entire software development life cycle. For example, we deny access by default: That is, something must be true in order for authorization to be granted.

### The Open Source Way

We are strong proponents of open source software, including the overall process of developing open source software. The Open Source Way is a framework we use to help us answer many questions about software design, deferring to how the open source community works.

Examples:

  - *How much documentation do we write?*
  
    Let's look at our favorite open source projects and see how their documentation looks. One example we like is the [react project](https://facebook.github.io/react/)

  - *What level of testing do we use?*

    Let's look at our favorite open source projects and see how their testing looks. One example we like is the [play framework](https://www.playframework.com/documentation)

  - *What type of API should I build?*

    Let's look at our favorite open source projects and look at their APIs. One example we like is [Stripe](https://stripe.com/docs/api)

## Application Development at Flow

### Design

Design of the system starts as soon as we begin discussing use cases and requirements. While the design stage starts early in our process, it is not concluded until the application is successfully completed - simple, stable, tested, in production, and meeting the needs of users.

APIs designed for our customers must also meet the requirements of the 'api' repository - https://github.com/flowcommerce/api - and designed using [apidoc](apidoc.me/flow)

### Environments

Flow provides three environments:

1. Local development environment
2. Local integration environment, supported by [workstation](https://github.com/flowcommerce/workstation)
3. Production, supported by [delta](https://delta.flow.io)

To simplify local integration environments, and manage dependencies between applications, each application must be created in [registry](https://github.com/flowcommerce/registry). Registry provides the following key features:

  - Unique port allocations, simplifying configuration for local integration environments
  - Declared dependency which informs which other applications, including databases, need to be running and healthy for a given application to work

Docker artifacts must be produced as they are used in both the integration and production environments. Docker artifacts are built from the master branch of each repository. Docker artifacts are stored and managed by [Docker Hub](http://hub.docker.com).

### Development

Source code should be written to be simple for an external reader to understand and correct, as guaranteed by the automated tests, and instrumented for easy debugging and monitoring. Contributions must follow the [Contribution Guidelines](Contributing.md)

  - [Source code management - Non Top Secret](https://github.com/flowcommerce)
  - [Source code management - Top Secret](https://github.com/flowvault)
  
We prefer our applications to be developed with similar style, making it easy for a developer to move from one project to another. Thus you will see very similar style of development across all Play/Scala applications at Flow and across all NodeJs applications.

For JVM based libraries, we publish our jars to [Artifactory](https://flow.jfrog.io/flow/webapp/#/login)

Note: local development activities are supported by a command line interface named [dev](https://github.com/flowcommerce/workstation) - dev is the place to provide tooling and utilities to replace repeated manual tasks with documented automation.

### Testing

We write automated tests at Flow, and depend on them for the correctness of our applications. We use the testing frameworks best suited to our application environments.

Every repository should have automated continuous integration tests enabled with [Travis](https://travis-ci.com/flowcommerce). Integration tests should run on Pull Requests and Commits, and tests should pass prior to merging Pull Requests.


### Dependendency Management

We strive to minimize the number of external dependencies. When we introduce dependencies, we are responsible for reviewing the code as if it is our own and we remain accountable for its performance and security at Flow.

To consume third party APIs - our preference is to document the API using [apidoc](apidoc.me/flow) which then ensures we can consume the third party API using the standard apidoc clients, as opposed to introducing new dependencies.

To track third party dependencies, for Scala based applications, we use [dependency](dependency.flow.io) and for Node applications, we use npm outdated. We commit to "OCD Fridays" where we spend the morning every week upgrading to the latest versions of all libraries. This practice of continuous upgrade aligns with our philosophy of continuous delivery.

### Code Review

Code review at flow should focus most critically on:

  - Identifying security risks, including topics covered in our [Secure Coding Presentation](https://docs.google.com/a/flow.io/presentation/d/1V067rPCNpz7zbugo2IAU6BAhnVV87fEMHT5ytEsmBPs/edit?usp=drive_web)

  - Identifying race conditions or other concurrent problems. These are very difficult to diagnose once in production
  
  - Identify other bugs / error conditions that should be handled / should not be handled
  
  - Identify suggestions for improving clarity to a non contributor

### Deployment

In non Top Secret environments, deployment is via [delta](https://github.com/flowcommerce/delta) - available at [https://delta.flow.io](https://delta.flow.io)

In Top Secret environmnents, refer to the deployment instructions for each application for details on secure deployment.

All infrastructure runs on AWS, preferring the use of their shared services for storage (e.g. RDS).

### Errors

When errors occur, teams should immediately respond:

  - If necessary, rollback by either deploying an earlier tag or revert changes and create a new git tag
  - For any non trivial error, announce immediately in Slack and make sure the people that can help are helping (e.g. interrupt any discussion or meeting, call them, etc)
  - Report any security issues (real or perceived) to security@flow.io
  
Once stable, commit to our process of continuous improvement by reviewing with team to determine how we prevent recurrence in future; share these findings at one of our weekly show and tell sessions or via email to tech@flow.io

### Communication

We encourage free and informal communication across the entire Tech org. Standard communication channels at Flow include:

  - Slack
  - Email (tech@flow.io)
  - Monday morning company wide standup
  - Friday afternoon tech Show and Tell
