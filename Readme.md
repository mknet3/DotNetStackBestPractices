# DotNet Stack - Best Practices

⭐ *Make quality great again.* ⭐

Welcome to my little space of best practices. This is a guide, not a bible. Take what you need.

## [Clean code](cleancode.md)

## [DDD](ddd.md)

## [Performance](performance.md)

## [Git](git.md)

## Project structure
Project structure should make sense. Something like this has worked to me in multiple projects:

```
📦repo
 ┣ 📂deployment
 ┃ ┣ 📂infrastructure
 ┃ ┃ ┣ 📜database.tf
 ┃ ┃ ┗ 📜monitoring.tf
 ┃ ┗ 📂services
 ┃ ┃ ┗ 📂contoso-api
 ┃ ┃ ┃ ┣ 📂templates
 ┃ ┃ ┃ ┃ ┣ 📜configmap.yaml
 ┃ ┃ ┃ ┃ ┣ 📜deployment.yaml
 ┃ ┃ ┃ ┃ ┗ 📜service.yaml
 ┃ ┃ ┃ ┣ 📜Chart.yaml
 ┃ ┃ ┃ ┗ 📜values.yaml
 ┣ 📂docs
 ┃ ┗ 📜architecture.md
 ┣ 📂pipelines
 ┃ ┣ 📜cd.yaml
 ┃ ┗ 📜ci.yaml
 ┣ 📂src
 ┃ ┣ 📂Contoso.API
 ┃ ┗ 📂Contoso.Domain
 ┣ 📂test
 ┃ ┣ 📂Contoso.API.FunctionalTests
 ┃ ┣ 📂Contoso.API.UnitTests
 ┃ ┗ 📂Contoso.Domain.UnitTests
 ┣ 📜Contoso.API.sln
 ┣ 📜Directory.build.props
 ┣ 📜global.json
 ┗ 📜Readme.md
```
Repositories should always have a **`Readme`** with a path to configure the development environment to run projects. If new members join the team should be able to configure their environment without difficulties.

This is an structure example, the most important thing is to be consistent across projects and make sense.