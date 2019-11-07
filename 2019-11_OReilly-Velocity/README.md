# Velocity Conference 2019
O'Reilly learning platform 90 days for free `VLSAEU19`

## 06.11. - Wednesday

### Keynote
- James Mickens: pointless bashing various things at random
- Karthik Gaekwad (Oracle)
- Christine Yen (Honeycomb): building bridges between dev and ops : observability
- Lorenzo Saino (Fastly)
- Ana Oprea (Google): error budgets
- Heidi Waterhouse: very good talk about error budgets and resilience

### 11:35 - A beginner's guide to eBPF
*Liz Rice (Aqua Security)*
- eBPF = extended Berkeley Packet Filter

>eBPF does to Linux what JS does to HTML
>
- run code in the kernel without writing kernel modules
- written (restricted) C
- LLVM 
- BCC makes BPF easier to write
  - python, lua, C++ wrapper
- eBPF can be attached to different events, e.g. network package received
- eBPF maps 
- CNCF project falco
- `kubectl trace`
- tracee: trace fro containers, ignoring non-container stuff
- eBPF can alert, but can't prevent bad behavior

### 13:25 - The deputy shot the sheriff: Privilege escalation in build pipelines
*Andreas Sieferlinger (Scout24)*
- deplyoment workflow got more and more complicated over time
- confused deputy : legitamate server being tricked by another system to misuse its privileges
- CI / CD: big central system with huge blasst radius
  - masks original / triggering user
  - might make changes to the repo
  - hidden jump server
  - Acting on behalf of somebody else
- Scout24's CI/CD solution with ephemeral Jenkins agents
  - knows who the changes originates from
  - checks permissions
  - blast radius is reduced by using one CI/CD system per team from standardized instances with limited scope
- Push to git == full access to prod
  - use same auth source for everything
  - be careful when building forks/PRs (not prod credentials)
  - mandatory code reviews
  - rotate access keys frequently (< 1 hour)

### 14:20 - What remains of dashboards and metrics without the hype and anti-patterns
*Björn Rabenstein (GrafanaLabs)*
> if you can graph it, you can alert on it.

- wall of *meaningless* dashboards tend to lengthen the downtime
- keep your dashboards clear and meaningful
- your outage might be caused by something not on your dashboard at all
- Three Pillars of observability: logs, metrics, traces
- recommendation: youtu.be/EJV_CgiqlOE - Three pillars zero answers: we need to rethink observability (Ben Sigelman) @ KubeCon 2018
- three pillars do not answer all your problems but might help you building better software
- any of the pillars does not replace any other. you still need  to collect logs

### 15:50 - Configuration is (riskier than?) code
*Jamie Wilkinson (Google)*
- generally configuration changes not handle with the same care as code changes
- YAML tells the computer what to do --> is it programming?
- where does config come from? cli options, file inputs, env vars, etc.
  - feature flags? thresholds?
> Configuration = inputs to a program

- "infra as code" -> "software-defined software"
- configuration complexity spiral
  - hard coded -> config values -> rules engine -> DSL -> config for the DSL (e.g. Terraform)
- causes of cloud outages -> 32% "misconfiguration", 43% "software bug"
- if config is code and can cause outages just like the software code, then config testing should be part of CI/CD
- put EVERYTHING in version control
- Delete code to simplify config (feature toggles, machine-discoverable information)

### 16:45 - The elephant in the Kubernetes room: Team interactions
*Manual Pais*
- Topics
  - K8s as platform
  - Dev and Ops Equilibrium
  - Team Cognitive Load
  - team interactions
- Article: " How Airbnb simplified the Kubernetes workflow for 1000+ engineers"
- Who is responsible? / who is impacted?
- DevOps venn diagram: intersection is bigger than the differences!
- Using K8s reduced cognitive load
- using less AWS basic services, but more K8s
- offering K8s as a platform to reduce complexity for the devs
- treat platform as product (reivews, product management, resilience, etc.)

## 07.11. - Thursday

### Keynote
- Ingrid Burrington: *missed because call from Munich* 
- Jennifer Davis (Microsoft): it's not about adopting buzzwords like "Dev(Sec)Ops", but to build communities. Learn from each other and from you mistakes.
- Dave Cheney (WMware)
- Lena Reinhard (CircleCI): connection, collaboration, communication. clear, crisp messages, anticipating counter questions. avoid idioms.
- Kelly Shortridge (Capsule8): bringing security thinking to DevOps - D.I.E. - Distributed, Immutable, Ephemeral

### 11:35 - What happens when you type de.wikipedia.org?
*Effie Mouzeli (Wikimedia Foundation), Alexandros Kosiaris (Wikimedia Foundation)*
- LAMP stack monolith broken up to SOA (microservices)
- adopting K8s
- Kafka message queueing
- 5 data centers across the globe, own CDN
- moving from varnish cache to ATS

### 13:25 - Taking the ops out of DevOps
*Eleanor Saitta (Systems Structure ltd.)*
- the more work a human has to do to see or influence the state, the less net bandwidth (cognitive capacity)
- comparing strings is very hard for humans (searching for typos) --> configuration changes need to be verified
- good tools have: immediacy, fluency, Clarity, predictability, isolation, reversibility
- do not patch your systems - rebuild them from scratch --> immutable systems
- separate data from applications, even warm caches
- everything as code - everything goes through the same CI/CD framework - even during outages
- everything for running that application lives in the same repo
- debugging IaC (e.g. Terraform) is hard
- legacy systems are a hurdle for innovation

### 14:20 - Helping your dev teams succeed at ops, post-Kubernetes
*Michael Hobbs (MOO)*
- created a template app to ease the start at K8s
- embedded ops engineers in product teams
- k8s workshop (facilitator was shadowed and only did it once)
- Namespaces and quotas per resource limits (generous)
  - breaking qoutas as basis for a conversation
- monitored heavily and team-specific alert channels
  - auto test the alerts
- make informed decisions for alerts - first collect reference data
- have a conversation with the teams about what they are missing (e.g. in terms of observability)

### 15:50 - Revolutionizing a bank: Introducing service mesh and a secure container platform
*Janna Brummel (ING Netherlands), Robin van Zijll (ING Netherlands)*
- customer demands fast adapting, increasingly convenient, secure banking solution
- from peak load sized on prem to scalable, HA cloud solution
- using containers: from pets to cattle
- using service mesh for easy networking with built-in security best practices
- containerize application -> create CI/CD pipeline for containers -> run container on platform -> define team policies
- working with industry standers lets new hires get productive very fast
- automate toil wherever and whenever we can
- looking into new capabilities: chaos engineering, zero trust, everything pipeline

### 16:45 - Test-driven development (TDD) for infrastructure
*Rosemary Wang (HashiCorp)*
- why does it look like a signpost? YOLO-driven development, lack og knowledge, lack of automation, lack of tooling
- unit tests
  - conftest & `terraform validate`
  - unit test without calling out to AWS
  - unit test just checks TF file, but no logic or resource dependencies
- contract tests
  - "real" resources not required, validating interactions, compare infrastructure *state*
  - conftest & `terraform plan`
- integration tests
  - confirms *interaction* betwee 2+ resources, real resources
  - `terratest`, `kitchen-terraform`, `Sentinel`
- E2E tests
  - manual or fully automated
  - or smoke tests
