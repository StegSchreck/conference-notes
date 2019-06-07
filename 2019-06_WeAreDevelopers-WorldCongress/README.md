# We are Developers - World Congress 2019
- no breakfast on either day
- lunch had to be paid
- what is the wristband for?
- after party at the other end of the city
- pure marketing talks to be avoided - see Kaspersky and Exoscale
- Organizers learned from Day1 and took action - distributing water and enhancing the lunch offers
- some talks did not keep the timebox - ending late, starting early, starting late... hard to follow schedule this way
- poor wifi availability
- two music sources at the food court. both way too loud. had to yell to order food
- in general good mix of tech and social topics

## 06.06. - Thursday

### 11:00 Alvar Lumberg - Scaling autonomy in a fintech unicorn (Transferwise)
- Startups: learn as you go - fail. learn. repeat.
- speed of learning constrained by speed of decision-making
- let people make their own decisions to let them be able to learn
- team makes decisions - team owns the product
- weak ownership model
  - components are owned by teams - not people
- every component needs an owner - otherwise they rot
- big tech changes are hard - they need a separate driver/owner
- common platform teams is enabler and limiter
  - don't let the zoo grow too big
  - but enable teams to ramp up easily and fast
- engineering leadership provides priorities for effective autonomy
- think along, ask 'why?' a lot, and increase you impact

### 11:35 Ashish Kuthiala - Engineering your digital transformation
- nowadays apps for everything, some better than others
- how fast can get your app to the market and collect feedback
- MVP -> collect feedback fast
- MVC = minimal viable change
  - e.g. display basic informations, later enhance with images, testimonials etc
- setup fundament of infrastructure which you can trust (e.g. ci/cd pipeline)
  - take out the human error

### 12:10 Tomislav Tipuric - Brave new worlds of microservices - patterns, ideas, do's & don'ts
- Difference of Microservices vs. SOA
- don't force technology choice on devs
- enable them too (kinda) freely choose according to their skills and likes
- when doing microservice: not horizontally, but vertically cut
- microservices can be deployed independently
  - also: independently scaled (according to taffic shifts)
- use better suited frameworks for the task in a microservice
- version your exposed API to be able to make changes
- microservice architecture itself is part of the application (algorithm)
  - therefore diagrams look more complicated when compared to monoliths
- separate services by api gateways instead of using direct communication
- remember queueing if communication breaks
- be aware of single point of failure (single microservice of failure) - avoid central components
- cloud ready applications are microservices designed applications
- microservice = pattern  --  container = technology
- containers are mainly about smaller footprints compared to VMs

### 13:55 Svetlana Kouznetsova - Accessibility: Coding and Beyond
- deaf - sign language - with translator
- live captured speech
- 1.3 billion people with disabilities
- biggest minority in the world
- disability doesn't discriminate
- many parties involved. managers, dev, designer, writer
- POUR - perceivable, Operable, Understanding, Robust
- semantic markup
  - use button / input / etc instead of misused div
- WAI ARIA - how to improve Accessibility
  e.g. `aria-described-by` attribute at input field
- avoid captchas (picture)
- require phone numbers decreases number of signups
- pictures with content are not accessible
- diversity and inclusion means nothing without accessibility

### 15:05 Janos Pasztor - 10 things to learn to become DevOps Jedi
_In the end this was a marketing talk to promote Exoscale_
DevOps is about getting things into Prod fast
10. CI
9. Automated testing - also for your infrastructure
8. Containers - ship complete environments - not only code
7. Kubernetes - container orchestration
6. service mesh
5. Lambda Function - Serverless
4. Ansible - Automation
3. Immutability
2. Terraform
1. break the rules - do not blindly copy what google does

### 15:45 Steffen Heilmann - Get ready for warp speed: Building a scalable IT organization
- define a vision
- do changes gradually, low interference with product development
- every person should drive 1 topic at most in parallel
- communicating changes early, in detail and when ever possible to have everybody involved
- collect feedback individually in order to don't miss anyone
- ensure flexibility for ad-hoc requests
- celebrating small and big steps along the way
- leader is responsible to instill the vision but let the team do their thing

### 16:20 Alina Denisenko - Seeding culture in new locations during hypergrowth
- how to transfer our culture to newly founded offices
- build up tech brand to ease hiring
- hypergrowth = 40% CAGR
- identified challenge in new office: too many senior BE engineers
  - encourage role changes
  - PO, security expert, agile coach
- next challenge: onboarding the new hires
  - onboarding sessions explaining services, culture, etc.
  - let 'old' new hires take over onboarding sessions
  - buddy system
  - pair and mob programming
- transfer ownership of services to the new office to let them be independent
  - bystander effect
  - blameless post-mortems
  - let team understand common vision
- iterate on processes and continuously improve
  - 1on1
  - retrospectives

### 16:50 Sebastian Feldmann - Git Fu Developing
_not visited as directly adjacent to other talk and in different Building_

### 16:55 Vladimir Stashkov - Patterns of building Software which is prepared to survive in a rapidly changing world
- Resilience
- high test coverage
  - TDD
  - isolated tests
- versioning with SemVer
- CI / CD
  - build once and use compiled artifacts on every environment
- Infrastructure as code
  - drift monitoring
- document APIs with swagger
- centralized log storage
- separate business logic from frameworks
  - goal: execute unit tests on business logic without frameworks

### 17:25 Modood Alvi - Serverless is eating the stack
- The good
  - fast, autoscaling, easily deployed
- The bad
  - stateless -> databases
  - no long running tasks
- pitfalls
  - increasing complexity
  - increasing costs
  - limit on amount of connections (e.g. on database access)
- The ugly
  - logging, request tracing and analysis is  tricky
  - vendor lock-in
  - cold start costly
- Hexagon architecture
  - own event handler
  - message producer
  - repository
- lightweight, go experiment, enhance rather than migrate your current application


## 07.06. - Friday

### 09:00 Matias Niemelä - The future of Angular
- rather a platform than a framework
- ivy renderer
  - rewrite of the current compiler
  - not used components, libs and code will be removed by the compiler
  - optimizing bundle sizes
  - "Hello World" in 14 kB
  - tree shaking
- Angular elements for using single Angular components in non-Angular websites
- lazy loading
- bazel: only compile what needs to
- template level breakpoints
- state management
- i18n build-in --> probably not Angular 9
- Angular 9 will come in fall1

### How to do presentations
- do not start with your name
- start with a quote
- make a statement
- ask a question
- tell an anecdote or story
- introducing people: not state their first, but describe the person and state the name last

### 09:35 Panel - Company Culture & Diversity
- diversity is not (only) about gender or LGBT
- think about culture, e.g. right-to-left reading languages
- facebook targeted ads about developer roles to guys only
- giving everyone the same opportunities is the basis
  - think of the picture with the fence and the boxes
- if you are privileged person (white, straight male), you might not see the problem

### 10:10 Karla Schönicke - Your tech skills are not enough
- VUCA world
  - volatile
  - uncertain
  - complexity
  - ambiguous
- servent leadership - from manager to mentor
- ever changing world - adapt to change - be user-focused
- solve people's problems with tech instead of forcing a product upon them
- only 30% of your time for developing -> building up communication, coordination, culture
- meaningful conversations are work!
- reserve time to give constructive feedback to other (and go through received feedback)
- pair and mob programming are helping with knowledge sharing and collecting perspectives
- cross-functional means also that devs are testing etc.
- respect personal space
- work on person-to-person problems
- how successful you will be as developer depends also how good your non-technical skills are
  - give and receive feedback (talk about perceived perspectives)
    perception, effect, wish
    feeling, behavior, impact
  - ask questions
    understand context etc.
  - learning and unlearning
    unlearning bad habits etc.

### 10:45 Jaime Jorge - The evolution of static code analysis
- developer spends his time: 42% maintaining code; 20% reviewing
- evolution from commercial tools to poen source
- configurability for individual Projects
- plugins and extensibility
- integrations with Gitlab, Github, CI server
- auto fix for simple issues like whitespaces etc.
What is the future?
- languages designed to mitigate some use cases - e.g. NullPointerException in Kotlin
- learning linter, recommending fixes
- interoperability of linters, exposed API
- in 5 years linters will be as basic as using IDEs and CI servers

### 11:55 Sebastian Witalec - Add native mobile to your Angular Projects: the migration story
- shared project structure
- `tns.xomponent.tns.html` namespacing
- `tns run android --bundle` for build the app version
  webpack renames files with corresponding `*.tns.*` files
- some parts can be reused, e.g. Services
- concentrate on differences - e.g. UI markup --> separate components?
- command for generating tns files `ng generate migrate-component --name=home`

### 12:50 Mike Acton - Building a data-oriented future
_DELAYED --> skipped_

### 13:35 Andre Vella - Riding the Storm: Scaling the early Team
- hypergrowth scaling causes friction
- making structures and responsibilities transparent for new hires
- storming/norming are not a state but continuously experienced
- welcome culture - sweets on the desk and offer help
- buddy system
- platform team as enabler for product teams to onboard faster and more efficient
- leader vs. manager
- set expectations and visions
- affinity groups - communities of practice
- encourage autonomy, but create common basis by cultural manifesto
- try tools for easing communication where appropriate
- bus factor not only for humans but also for applications
- be more attractive as employer by enabling remote collaboration

### 14:20 Reghu Ram Thanumalayan - What is your leading code?
- striving for excellence
- curiosity
- leave your ego at the entrance

### 14:45 Jan Ramm - How many developers fit into a taxi? Our journey to a multi-service app
- moving from radio-based to smartphone based
- 1.2 passengers per ride - 30% utilization rate of taxi driver
- integrating different solutions for different vehicles
  - by extracting common services and use APIs
- focus on fast time-to-market will create technical or organizational debt

### 15:20 Angelo Laub - Zero-Knowledge-Services
- modern life generates lots of data
- data can be used against us
- "data is the pollution problem of the information age"
- collecting data is a liability
- TCO for data is higher than cost for disk space
- use encryption for everything (data in transition + at rest)
- let customer own the data

e2e encryption?
- rather collect less data - what do you really need?
- the less data you need, the less to encrypt/store
- less data --> less risk of liability (even if not responsible for data leak)
- disadvantage: recipient has to be known first (for async decryption)

key management service?
- need to trust third party for storing the keys
- no data analytics possible

decentralized key management system
- shamir secret sharing: method for distributing shares of a key
- to decrypt, a minimum number of parts has to be collected
- single part has no value on its own
- mathematically proven secure
- e.g. privEOS - based on EOS blockchain

### 16:05 Markus Decke - 1+1>2 : Impacts of pair programming
- pair programming as part of eXtreme Programming (Kent Beck)
- pairing is about fast feedback
- split up as driver and navigator
- talk! and help each other
Things to avoid
  - don't shine out your partner (hide your ego)
  - if you are not focused, take a break
  - don't get distracted by mail, slack, phone during the session
  - detach people from their code - do not criticize on personal level
Things to encourage
  - talk to each other - embrace ideas and discuss
  - switch your pairing partner once in a while
  - timebox the session to keep focused
  - respect each other and be cooperative --> collective code ownership
- experiment with feedback after the sessions
- regularly switch the desk involved
- PingPong technique: A writes test, it fails -> B implements and makes the test green and writes next test and so on.
  --> can also be done as mob
- Pomodoro technique: set timer to 25 min - stop when interrupted  - 5 min break - repeat
- shared domain knowledge
- focus on getting things done, even in noisy office
- after some practice: faster ticket resolving with better quality
