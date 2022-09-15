# Microservice 

## History
- Micro web service: first used by Dr Peter Rogers - conference about cloud computing  - 2005
- Microservice: Introduced in Venice in 2011
- Microservices: Better name in 2012
- More popular today

## Who
- Netflix
- Amazon
- Uber
- Spotify
- Uber
- SoundCloud
- eBay
- ...

## What
- Microservices (or Microservice architecture) is an **archtectural style** that structures an application as **a collection of services**
- Service is:
    - Highly maintainable and testable
    - Loosely coupled
    - Independently deployable
    - Organized around business capabilities
    - Owned by a small team
- Example of an application deployed in monolith and microservices

## Pros and cons
For big application/system
### Pros
- Deployment
    - Indenpendent deployment
    - Git/5 people project illustration 
    - Tags: #Docker #GitLabCICD
- Scaling
    - Easily scale up/down a part of the system if needed
    - Horizontal scaling
    - Cost of scaling is smaller
    - Tags: #Kubernetes
- Fault taulerance
    - Cache (#MemCache, #Redis)
    - Retry mechanism (#SpringRetry)
- Understandable codebase
    - Single responsibility
    - Follow the organizational structure
    - Owning a small business domain
    - Small codebase
- Experimenting different technology
    - Different techstack
    - Different version
    - Experimental upgrading
### Cons
- Inter-service communication
- More resources (CPU/RAM/servers)
    - Higher cost
- Global testing and debugging
- Complex deployment
- Log aggregation and distributed tracing (#logstash, #elasticsearch, #kibana, #datadoglog)
- Hard to share code
- Monitoring (#datadog)
- Local environment (#minikube)
- Technology overload
- Cross database report
- Latency (#grpc)
- Data consistency


## Challenges
- Local development
    - Maintaining a single microservice is easy
    - Interservice testing is more complex
- Code duplication
    - Generation code from template
    - Tags: #cookiecutter
- Bounded context
    - A bounded context clarifies, encapsulates, and defines the specific responsibility to the model (real world things, e.g. users, products, access rights) -> independence and decoupling
    - Different models for the same real world entity (user: profile info/billing info/login info + roles)
    - Understanding the business domain well to determine the bounded context
- Service contract changing
    - Monolith: Changes can be verified at compile time
    - Microservices: 
        - Backward compatible changes
        - Backward incompatible changes
- Service contract testing
    - Consumer Driven Contract (CDC) testing: verify that provider components are compatible with consumer expectations
- Initializing and deleting customer data
    - Monolith:
        - Cascade deleting
        - Database transaction
    - Microservice: Saga pattern
- Tracing a request
    - Add correlation ID
    - Aggregating logs from multiple services
- DevOps practice
    - Heavy DevOps practice
    - Minimize the infrastructure cost
    - Monitoring the infrastructure
    - Troubleshooting
- Synchronous and Asynchronous communication
    - Sync: 
        - Retry mechanism on failure
        - Error handling (Error code)
        - Performance optimization
    - Async:
        - Idempotent implementation
        - Retry mechanism on failure
        - Message order guarantee
- Security
    - Monolith: Single server -> less vulnerable points
    - Microservices: Multiple servers -> more vulnerable points
    - Different technologies -> More security issues to fix
