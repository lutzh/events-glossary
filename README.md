# Events Glossary

A curated list of terms used to describe events in event-driven architecture or event sourcing.

<a id="event-notification"></a>**Event Notification**
An event that only signals that something changed in the sender's domain. It carries minimal data: an identifier and a link back to the source. Receivers ask the source if they need more detail, and the sender expects no response.[^1]

<a id="event-carried-state-transfer"></a>**Event-Carried State Transfer**
An event that carries the changed data itself, so receivers can update their own copy of the source's state without ever calling the source.[^1]

<a id="event-sourcing"></a>**Event Sourcing**
Every state change is stored as an event, and the event log is the primary source of truth. Current state is derived by replaying the log.[^1]

<a id="cqrs"></a>**CQRS (Command Query Responsibility Segregation)**
Separate models for writing and reading data. It is not an event pattern itself and works without events, but it is often combined with them.[^1]



## Following & Contributing

To be updated about changes, follow me on <a href="https://mastodon.social/@lutzhuehnken" rel="me">Mastodon</a>, [Bluesky](https://bsky.app/profile/huehnken.de) or [LinkedIn](https://de.linkedin.com/in/lutzh). If you find this interesting, you might also like my [blog](https://www.reactivesystems.eu/blog/).


Please read the [contribution guidelines](contributing.md) if you'd like to contribute.

## Sources

[^1]: Martin Fowler: [What do you mean by “Event-Driven”?](https://martinfowler.com/articles/201701-event-driven.html)



