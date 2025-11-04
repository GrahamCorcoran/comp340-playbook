# Deployment

> Deployment is the process of delivering the finished software to its intended users.

After the system has been developed and tested, it must be made available in a real-world environment. Deployment is often the point where careful preparation pays off, since mistakes here directly impact users. Unlike the prior phases which take place in controlled environments, deployment involves moving the software into production where reliability, performance, and user experience are critical.

```admonish info title="This Book Is 'On Prod' Too!"
Want an example of a live deployment pipeline? Why not take a look under the hood at the [COMP340 Playbook](https://github.com/GrahamCorcoran/comp340-playbook)? In the GitHub repository you can see:

1. The use of [mdbook](https://rust-lang.github.io/mdBook/), a tool written by [others](https://rust-lang.github.io/mdBook/misc/contributors.html) that I used to create this book. 
2. CICD Pipeline using GitHub Workflows in ./github/workflows
3. Handling of third-party dependencies: I wanted colourful "callouts" like you're reading now and the mdbook defaults weren't very good, so I installed [mdbook-admonish](https://github.com/tommilligan/mdbook-admonish).
```

**Deployment Planning:** Before release, teams prepare for how and when the system will go live. This may involve setting timelines, coordinating with stakeholders, and planning communication to users.

**Deployment Environments:** Software typically moves through several environments such as development, testing, staging, and production - before reaching end users. These stages help ensure issues are caught early and not released into production.

**Deployment Models:** Different approaches exist for putting software into production. For example, a system might be rolled out gradually to a subset of users (canary release), or updated all at once across the entire user base. Cloud-based systems also allow for flexible and scalable deployment strategies compared to traditional on-premises releases.

**Post-Deployment Verification:** Once software is live, teams must confirm it is working as intended. This may include smoke testing (quick checks of critical functionality) and monitoring system health through metrics and logs.

Generally speaking, deployment is not a single event but part of an ongoing cycle, especially in modern development practices where frequent, small releases are common.

## Deployment vs Release

When we refer to Deploying and Releasing something, often the terms are used interchangeably. However, they describe two slightly different parts of how software reaches our users.

**Deployment** refers to putting software into a production environment where it could be used. This doesn't necessarily mean users see it right away. For example, we might deploy a new feature to a production server but hide it behind a feature flag, keeping it invisible to most users until it's ready.

**Release** is the moment that deployed software is made available to end users. Releasing is about visibility and access. Releases can be broad, where everyone gets it at once, or controlled where only certain users or regions see it at first.

```admonish example title="Check Your Understanding"
1. Why is deployment considered one of the riskiest phases of the SDLC?  
2. What is the purpose of having multiple deployment environments (development, staging, production)?  
3. How does a canary release differ from deploying to all users at once? 
```
