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
