Event-driven Architecture - MArtin Fowler (GOTO 2017)
[youtube](https://www.youtube.com/watch?v=STKCRSUsyP0)

Event-driven patterns
1.  Event notification. 
    + Decoupling of sender and receiver
    - No statement of overall behavior; who's listening to whom?
2.  Event-carried State Transfer.
    Send "change sets", the new version and a copy of the old version.
    + Even more decoupling
    + Reduced load on supplier
    - Replicated data, which leads to
    - Eventual consistency
3.  Event sourcing.
4.  CQRS: Command Query Responsibility Segregation.
    Separate read- and write commands
