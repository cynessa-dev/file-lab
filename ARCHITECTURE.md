# ARCHITECTURE

This file will talk about the planned architecture for the development of FileLab. Do note that, details here can change if project requires or if there are better options.

## Tech Stack

- Vue + TypeScript
- Go
- PostgreSQL
- Docker
- Terraform
- GitHub Actions
- Google Cloud

> P.S. Here's the FigJam, this is where I mostly plan things and make diagrams: [Figjam](https://www.figma.com/board/kzvXzC4wJvVQsub01CHcUH/FileLab-Architecture?node-id=4-24&t=nML5fwPFoORFKOlT-1)

## Overall Architecture

<img width="4528" height="2192" alt="v1_architecture" src="https://github.com/user-attachments/assets/314cdd63-0ad1-4822-b9d1-71c3072fff90" />
<br />
<br />

Based on the image above, that is the initial architecture on how FileLab will be developed and deployed. This is still the **version 1**, meaning there are still questions left unanswered and can potentially change the architecture.

For example, Docker will be used to containerized 3 services; Front-end, Back-end, and Database. This will allow an isolated dev environment allowing any developer to test and modify the source code in a controlled environment with the use of Docker Compose.

However, my experience with Google Cloud is limited, and thus the question is "how to manage the 3 containers in Production?" Although I have barely used Google Cloud, I believe that they have their own Orchestration and Database Service. Similarly, AWS has DynamoDB and ECS for such use case.

### Development

The Dev Environment will be isolated using Docker. This will give a ton of benefit for the developer:

1. The environment can be controlled for easy testing and cleaning;
2. Services doesn't need to be configured when sharing with others;
3. and, the services are separated for security and compatibility.

There are a lot more reasons like **scalability and more efficient pipeline**, but those 3 are the major reasons. Basically, it makes life easier for the developer.

The 3 services are:

1. Front-end (Vue + TypeScript)
2. Back-end (Go)
3. Database (PostgreSQL)

\
**FRONT-END**

Since this will be a small, MVP web app, Vue will be used for its speed and progressive nature. This will not only allow me to make the system light, but also improve my proficiency with Vue. TypeScript will be paired with it, mainly for Type-safety.

\
**BACK-END**

Back-end will be Go. Mainly because I want to improve my proficiency with it, building with Go is one of the effective ways to see its potential and benefits. For my research, Go is said to be efficient and fast, perfect for high-performance API.

\
**DATABASE**

Database will use PostgreSQL. Mainly for scalability, it should give the app room for growth such as complex queries, more data types, and data integrity. Of course, the trade-off is speed, but since this system handles files, security and integrity is priority over speed.

<br />

### CI/CD

We will choose GitHub Actions for simplicity as the source code will be placed in GitHub. We can checkout new technologies like Argo CD, but I would like to use that once the MVP is deployed for experimentation.

There will be 3 checks:

1. Format — For code consistency, normally this part always pass since code is formatted with Prettier in pre-commit.
2. Linting — This will help us spot unused variables and errors before they become an issue.
3. Build — We make sure the project actually compiles before deloying it.

### IaC

Terraform will be used as part of mastering and provisioning for Google Cloud. This will allow us to configure the deployment platform easily, and can be duplicated whenever.

### Cloud Computing Platform

Google Cloud is chosen for 2 main reasons:

1. To try out other platforms other than AWS;
2. and, to avoid getting charged.

> P.S. That last one is important. Google Cloud and AWS has different pricing and free tiers.

This will also give us an opportunity to get exposed with more cloud computing platforms to get to know them better. Just like AWS, I believe that Google Cloud has AWS-counterparts like for DynamoDB, ECS, and ECR. That's why this architecture will change in the future, but we do have an initial plan to follow, and that's alright.
