<div align="center">

# BetterReads

A book tracking app I rebuilt on my own from an earlier group project.

[![App](https://img.shields.io/badge/betterreads-app-1F4D7A?style=flat-square&logo=github)](https://github.com/dahl-jar/betterreads)
[![Frontend](https://img.shields.io/badge/betterreads--frontend-1F4D7A?style=flat-square&logo=github)](https://github.com/dahl-jar/betterreads-frontend)
[![Infra](https://img.shields.io/badge/betterreads-gitops--template-1F4D7A?style=flat-square&logo=github)](https://github.com/dahl-jar/betterreads-gitops-template)

[![Java](https://img.shields.io/badge/Java-555?style=flat-square&logo=openjdk&logoColor=white)](https://docs.oracle.com/en/java/javase/21/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-555?style=flat-square&logo=springboot&logoColor=white)](https://docs.spring.io/spring-boot/index.html)
[![React](https://img.shields.io/badge/React-555?style=flat-square&logo=react&logoColor=white)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-555?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-555?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/docs/)
[![Redis](https://img.shields.io/badge/Redis-555?style=flat-square&logo=redis&logoColor=white)](https://redis.io/docs/latest/)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-555?style=flat-square&logo=kubernetes&logoColor=white)](https://kubernetes.io/docs/home/)
[![Argo CD](https://img.shields.io/badge/Argo%20CD-555?style=flat-square&logo=argo&logoColor=white)](https://argo-cd.readthedocs.io/en/stable/)

</div>

### [betterreads](https://github.com/dahl-jar/betterreads)

A headless JSON API that combines book data from six sources using field-level
trust rankings. Books stay in staging until they have every field needed for a
detail page, and the best description is selected by score before promotion.

Authentication uses short-lived access JWTs and rotating refresh tokens. Reusing
an old refresh token revokes the whole family. Email uses a transactional outbox,
Redis handles rate limiting, and Meilisearch handles search.

### [betterreads-frontend](https://github.com/dahl-jar/betterreads-frontend)

The React and TypeScript client for BetterReads. It covers catalog search,
reading shelves, reviews and book discussions.

### [betterreads-gitops-template](https://github.com/dahl-jar/betterreads-gitops-template)

A k3s GitOps template extracted from BetterReads. Argo CD deploys from Git, and
Cloudflare Tunnel provides ingress without exposed ports. Default-deny network
policies restrict service traffic, and sealed secrets keep encrypted values in
the repository. Grafana Alloy sends pod logs and metrics to Grafana Cloud.
