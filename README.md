## BetterReads

A book tracking app I rebuilt on my own from an earlier group project. Two repos:
the application and the infrastructure it runs on.

### [betterreads](https://github.com/dahl-jar/betterreads)

`Java` `Spring Boot` `PostgreSQL` `Redis` `Meilisearch`

A headless JSON API. The catalog pulls book data from six sources and merges it
field by field by trust ranking; a book stays in a staging table until it has
every field a detail page needs, then gets promoted. Descriptions are scored so
the best one wins.

Auth is short-lived access JWTs with refresh tokens that rotate on every use,
and reuse of an old token revokes the whole family. Email goes through a
transactional outbox so a crash mid-send never drops or doubles a message. Rate
limiting runs in Redis, search on Meilisearch.

### [betterreads-gitops-template](https://github.com/dahl-jar/betterreads-gitops-template)

`k3s` `Argo CD` `Cloudflare Tunnel` `Sealed Secrets`

The Kubernetes setup behind it, pulled out into a template. Argo CD reconciles
the cluster from Git, so a deploy is a commit. Nothing listens on an inbound
port; a Cloudflare Tunnel dials out. A default-deny network policy opens each
flow by name. Secrets are sealed against the cluster key, so the encrypted form
sits in the repo and only the cluster can read it.
