<div align="center">

# BetterReads

A book tracking app I rebuilt on my own from an earlier group project.
The application and the infrastructure it runs on.

[![App](https://img.shields.io/badge/betterreads-app-1F4D7A?style=flat-square&logo=github)](https://github.com/dahl-jar/betterreads)
[![Infra](https://img.shields.io/badge/betterreads-gitops--template-1F4D7A?style=flat-square&logo=github)](https://github.com/dahl-jar/betterreads-gitops-template)

![Java](https://img.shields.io/badge/Java-555?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-555?style=flat-square&logo=springboot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-555?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-555?style=flat-square&logo=redis&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-555?style=flat-square&logo=kubernetes&logoColor=white)
![Argo CD](https://img.shields.io/badge/Argo%20CD-555?style=flat-square&logo=argo&logoColor=white)

</div>

### [betterreads](https://github.com/dahl-jar/betterreads) &nbsp;·&nbsp; the application

A headless JSON API. The catalog pulls book data from six sources and merges it
field by field by trust ranking; a book stays in a staging table until it has
every field a detail page needs, then gets promoted. Descriptions are scored so
the best one wins.

Auth is short-lived access JWTs with refresh tokens that rotate on every use,
and reuse of an old token revokes the whole family. Email goes through a
transactional outbox so a crash mid-send never drops or doubles a message. Rate
limiting runs in Redis, search on Meilisearch.

### [betterreads-gitops-template](https://github.com/dahl-jar/betterreads-gitops-template) &nbsp;·&nbsp; the infrastructure

The Kubernetes setup behind it, pulled out into a template. Argo CD reconciles
the cluster from Git, so a deploy is a commit. Nothing listens on an inbound
port; a Cloudflare Tunnel dials out. A default-deny network policy opens each
flow by name. Secrets are sealed against the cluster key, so the encrypted form
sits in the repo and only the cluster can read it.
