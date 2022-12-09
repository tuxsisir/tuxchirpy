---
title: "Explore CI/CD"
date: 2020-06-12
draft: false
tags: ["devops"]
---

### Continous Integration / Continous Delivery / Continous Deployment

| Continous Integration                                      | Continous Delivery                         | Continous Deployment                         |
| :-------------------------------------------------------   | :---------------------------------------   | :------------------------------------------- |
| Integration of the overall codebase developed by the team. | Delivery to the Mock Server / Stage Server | Direct push to the production server (SCARY) |
|                                                            |                                            |                                              |

Some organization follow, CI, some follow CI Continuous Delivery, big comapnies will follow CI to Continous Deployment.

BUILD > AUTOMATION TEST > PUSH


| Development                             | Operations                                 | QA      |
| :-------------------------------------- | :----------------------------------------- | :-      |
| Responsible for developing and testing. | Responsible for taking work to production. | TESTING |
|                                         |                                            |         |

### Integration Testing
- testing the overall integrity of codebase developed by all the developers (Responsible: Operations)

### CI TOOLS

- bamboo
- buildbot
- travis ci
- jenkins

<img src="../../images/what-is-ci.png" align="center">

### What is DevOps?

DevOps is a software development approach which involves continuous development, continuous testing, continuous integration, continuous deployment, and continuous monitoring of the software throughout its development lifecycle. This is the process adopted by all the top companies to develop high-quality software and shorter development lifecycles, resulting in greater customer satisfaction, something that every company wants.

```
DevOps is a set of practices that combines software development
and information-technology operations which aims to shorten the systems development
life cycle and provide continuous delivery with high software quality.

- Wikipedia
```

https://dzone.com/articles/learn-how-to-setup-a-cicd-pipeline-from-scratch
