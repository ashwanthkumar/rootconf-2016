# Continuous deployment at Scale

From Premshree Pillai, Etsy, @premshree

## Agenda
- Principles
- Tooling + Culture
- Q & A

## Principles

- just ship
- enable innovation (you're creating products, not code)
- optimize for purpose
- optimize for ***mastery***
- experimentation
    - A/B testing
- quick iteration
    - imporve products
    - fail fast > stagnant code
- continous improvement
- low MTTR (Mean Time to Recover)

## Tooling
- Continous deliver / deployment
> commit -> build -> tests -> user tests -> release
- frequent check-ins (to master!)
- Feature flagging - github.com/etsy/feature
- ready to release
- TryLib - github.com/etsy/trylib
- Deployinator - github.com/etsy/deployinator
- anybody can push 
- be anxious ... but do not fear
- dark changes
    - template changes
    - css tweaks
    - unreferenced code
- config pushes
- push train - with pushbot - https://github.com/etsy/pushbot
- post deploy
    - supergrep - https://github.com/etsy/supergrep
    - dashboards
    - StatsD + Graphite

[poka-yoke](https://en.wikipedia.org/wiki/Poka-yoke) - there's only one way to do things

## Engineering Culture
http://www.slideshare.net/chaddickerson/code-as-craft-building-a-strong-engineering-culture-at-etsy

https://github.com/etsy/mixer

https://www.pagerduty.com/blog/etsy-engineer-exchange/

Blameless post mortems - https://github.com/etsy/morgue

This is seriously cool - https://codeascraft.com/2012/09/10/the-engineer-exchange-program/

https://codeascraft.com/

## From Q & A
- No Canary Releases
- Always use Feature toggles in all their deployments
