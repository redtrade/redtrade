# redtrade

Virtual trading platform.

## High level goals
* Learn some new things
* Follow best practices

## Low level goals
* Docker
  * Use Docker Compose to bring up the entire stack at once
  * Version control config files
  * Use official images
  * Keep images close to vanilla
  * Use latest images
  * Add healthchecks
  * Avoid "depends on", use retry logic, buffering, backpressure, until resource is available again
  * Add restart logic
* Services (General)
  * Make services decoupled, independantly scalable
  * Use microservices unnecesarily because all the cool kids are doing it
  * Use events unnecesarily
* Services (Java)
  * Use lombok
  * Use built-in Spring features
* CI/CD, Git
  * Use branches, PRs
  * Merges should go through Travis
  * Source code should be linted
* Testing
  * Develop and document test scenarios (integration tests only)
  * Create Spring profile for running integration tests locally
    * Sink requests to external dependencies when necessary
    * Test each dependency separately
  * Write watchdogs that continuously test scenarios in "production"
    * Fire events if scenarios start failing
* Telemetry
  * Make some sweet Grafana dashboards
  * Make some sweeter Grafana alerts because Kibana alerts aren't OSS yet
* Administration
  * Centralized authority for current system state
    * Get Alert information from Graphana periodically
    * Set global states (DDoS protection etc) automatically/manually, let services consume periodically
  * Kill/kick bad services automatically
  * Service control/backdoor
    * Kill services gracefully/abruptly, let Docker recover
    * Artificially create reliability drops
* Stretch goals
  * Security token generation for clients
  * Encryption
  * Agent network
    * Legitimate requests
    * Malicious requests
      * Password brute force/spraying

## Stack

* ***Angular/Bootstrap*** as frontend JavaScript frameworks or maybe just HTML and jQuery because I'm terrible at UI
* ***Spring Boot*** for backend
* ***nginx*** for serving UI content
* ***nginx*** for proxying to service layer
* ***Docker*** for containers
* ***Redis?*** for message passing
* ***redis** for HA object storage, clustering technique stolen from [here](https://github.com/AliyunContainerService/redis-cluster)
* ***PostgreSQL? Mongo?*** as a data repository
* ***ELK*** for log handling and metrics
* ***Graphana*** for telemetry visualization, alerting
