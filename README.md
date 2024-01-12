# Project Proposal: Clean Architecture with DDD and Hexagonal Architecture

## Overview

This repository contains a proposal for the architecture of our new project, aiming to leverage Clean Architecture
principles with a blend of Domain-Driven Design (DDD) and Hexagonal Architecture. The goal is to create a scalable,
maintainable, and highly testable system that aligns with the business domain and minimizes dependencies on external 
frameworks.

## Structure

The project is organized using the following directory structure:
```
/project-root
|-- /api-1
| |-- /cmd
| | |-- /lambda
| | |-- /ecs
|
| |-- /internal
| | |-- /customer
| | | |-- /application
| | | |-- /domain
| | | |-- /infrastructure
| | | | |-- /controller
| | | | |-- /repository
|  
| | |-- /product
| | | |-- /application
| | | |-- /domain
| | | |-- /infrastructure
| | | | |-- /controller
| | | | |-- /repository
|           .
|           .
|           .
| | |-- /another-domain
| | | |-- /application
| | | |-- /domain
| | | |-- /infrastructure
| | | | |-- /controller
| | | | |-- /repository
|
|-- /cdk
```


### Explanation:

- **/api-1**: Contains all the structure of an API, if we have more than one API, we can create more directories like this.

    - **/cmd**: The entry point of the API.

        - **/lambda**: Contains the lambda handler and the lambda function definition.

        - **/ecs**: Contains the ECS task definition and the ECS service definition.
      
    - **/internal**: Contains the internal modules of the API.

        - **/customer**: Contains the customer module.

            - **/application**: Contains the use cases and application-specific business logic.

            - **/domain**: Contains the core business domain, including entities, value objects, and repositories.

            - **/infrastructure**: Contains infrastructure concerns such as database access, external services, etc.

                - **/controller**: Contains the controller that handles interactions with the external world (UI, frameworks, etc.).

                - **/repository**: Contains the repository that handles the persistence of the entities.

        - **/product**: Contains the product module.

            - **/application**: Contains the use cases and application-specific business logic.

            - **/domain**: Contains the core business domain, including entities, value objects, and repositories.

            - **/infrastructure**: Contains infrastructure concerns such as database access, external services, etc.

                - **/controller**: Contains the controller that handles interactions with the external world (UI, frameworks, etc.).

                - **/repository**: Contains the repository that handles the persistence of the entities.

        - **/another-domain**: Contains another domain module.

            - **/application**: Contains the use cases and application-specific business logic.

            - **/domain**: Contains the core business domain, including entities, value objects, and repositories.

            - **/infrastructure**: Contains infrastructure concerns such as database access, external services, etc.

                - **/controller**: Contains the controller that handles interactions with the external world (UI, frameworks, etc.).

                - **/repository**: Contains the repository that handles the persistence of the entities.

- **/cdk**: Contains the CDK stack definition.

  - **/config**: Contains the configuration files for the CDK stack.
  
  - **/construct**: Contains the CDK constructs like the API Gateway, the Lambda functions, etc.
  
  - **/helper**: Contains helper functions for the CDK stack.
  
  - **/stack**: Contains the different CDK stacks.
