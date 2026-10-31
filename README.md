# Events Glossary

A list of terms used to describe events in event-driven architecture or event sourcing, in alphabetical order.


<a id="clickbait-event"></a>**Clickbait Event**:
An alternative name for [event notification](#event-notification), [trigger event](#trigger-event), and [signal event](#signal-event) that captures how these events appear to the receiver: They tell that something happened, but to find out what, you have to follow a link. 

<a id="command"></a>**Command**:
Not an [event](#event). A command expresses an intent, usually to change some state on the recipient side. A command usually yields a response, indicating if the command was executed successfully, or execution failed. See also [event](#event) and [query](#query).

<a id="cqrs"></a>**CQRS (Command Query Responsibility Segregation)**:
Separate models for writing and reading data. It is not an event pattern itself and works without events, but it is often combined with them.[^1][^4]

<a id="domain-event"></a>**Domain Event**:
An [event](#event) that describes something interesting has happened in a domain[^3]. Often this is the creation or change of state of some entity. This term distinguishes domain events from technical events without business meaning (e.g. log events, sensor data in IoT), as well as from events that are purely for data replication (see [Replication Event](#replication-event)).   
In another context, the term is used to distinguish events that are internal to a [bounded context](https://martinfowler.com/bliki/BoundedContext.html) from [integration events]() that travel between bounded contexts.[^2]

<a id="ephemeral-event"></a>**Ephemeral Event**:
An [event](#event) that is explicitly marked as being only valid until the next event of the same type arrives.[^6]

<a id="event"></a>**Event**:
Something that has happened in the past [^4]. A fact (it has been observed, it is undisputed). Often used as a synonym for [Event Message](#event-message). Events do not have a dedicated recipient; they are broadcast and can be consumed by services that the issuer of the event does not know about at runtime. Events do not yield a response; they are published in a "fire and forget" manner.

<a id="event-carried-state-transfer"></a>**Event-Carried State Transfer**:
An [event](#event) that carries the changed data, so receivers can update their own copy of the source's state without ever calling the source. The source of the term [^1] is vague about how much data the event contains (Quote: _"events that contain details of the data that changed"_). It is now often used as a term for events that carry a complete representation of the entity that changed. See also [REST Event](#rest-event), [Fat Event](#fat-event), [Replication Event](#replication-event), [God Event](#god-event).

<a id="event-notification"></a>**Event Notification**:
An [event](#event) that only signals that something changed in the sender's domain, without containing the changed data. It carries only a reference to the source of the event. Receivers ask the source when they need more detail.[^1] Synonyms are [signal event](#signal-event), [trigger event](#trigger-event), and [clickbait event](#clickbait-event).

<a id="event-sourcing"></a>**Event Sourcing**:
To persist entities or domain objects, every state change is stored as an event. The event log is the primary source of truth. Current state is derived by replaying the log (also known as [hydration](#hydration)).[^1][^7]. Event sourcing is a persistence strategy internal to a service, as opposed to [event streaming](#event-streaming) and [event collaboration](#event-collaboration), which describe communication between services.

<a id="event-stream"></a>**Event Stream**:
In [event streaming](#event-streaming), an event stream is a flow of events from a source system that other systems can observe and/or process. In [event sourcing](#event-sourcing), however, it's an ordered sequence of events that represent state changes of a specific entity or domain object.

<a id="fat-event"></a>**Fat Event**:
An [event](#event) that not only carries the changed data, but also unchanged data, specifically to reduce the type of events the consumer has to listen to.[^6] For example, if the event informs about an invoice being created, it may also carry information about the customer the invoice is for. Sometimes also used as a synonym for [god event](#god-event) or [REST event](#rest-event). See also [event carried state transfer](#event-carried-state-transfer).

<a id="god-event"></a>**God Event**:
An [event](#event) that carries a complete representation of the entity that changed[^5]. Synonym for [REST event](#rest-event). See also [fat event](#fat-event) and [event carried state transfer](#event-carried-state-transfer).

<a id="passage-of-time"></a>**Passage of Time Event**:
An [event](#event) that indicates, in a generic manner, that a period of time has passed. Examples would be a `DayHasPassed {date}` event at midnight, or a `QuarterHasPassed {year, quarter}`.[^6]

<a id="query"></a>**Query**:
Not an [event](#event). A query asks for information. It yields a response that either contains the requested information or indicates that nothing matching the query could be found. See also [event](#event) and [command](#command).

<a id="rest-event"></a>**REST Event**:
An [event](#event) that carries a complete representation of the entity that changed, like the full resource representation you would retrieve from a RESTful API[^3]. Synonym for [god event](#god-event). See also [fat event](#fat-event) and [event carried state transfer](#event-carried-state-transfer).

<a id="signal-event"></a>**Signal Event**:
An [event](#event) that only signals that something changed in the sender's domain, without containing the changed data. It carries only a reference to the source of the event. Receivers ask the source when they need more detail.[^3] Synonym for [event notification](#event-notification), [trigger event](#trigger-event), and [clickbait event](#clickbait-event).

<a id="summary-event"></a>**Summary Event**:
An [event](#event) that summarizes the outcome of a business process which consists of a sequence of more detailed events which are not interesting to subscribers.[^6]

<a id="trigger-event"></a>**Trigger Event**:
An [event](#event) that only signals that something changed in the sender's domain, without containing the changed data. It carries only a reference to the source of the event. Receivers ask the source when they need more detail.[^3] Synonym for [event notification](#event-notification), [signal event](#trigger-event), and [clickbait event](#clickbait-event).

<!--
<a id="replication-event"></a>**Replication Event**:
TO DO

<a id="event-message"></a>**Event Message**:
TO DO

<a id="integration-event"></a>**Integration Event**:
TO DO

<a id="thin-event"></a>**Thin Event**:
TO DO

<a id="wide-event"></a>**Wide Event**:
TO DO

<a id="delta-event"></a>**Delta Event**:
TO DO

<a id="message"></a>**Message**:
TO DO

<a id="event-streaming"></a>**Event Streaming**:
TO DO

<a id="event-storming"></a>**Event Storming**:
TO DO

<a id="event-sourcing"></a>**Event Sourcing**:
TO DO

<a id="event-collaboration"></a>**Event Collaboration**:
TO DO

<a id="pivotal-event"></a>**Pivotal Event**:
TO DO

<a id="projection"></a>**Pivotal Event**:
TO DO

<a id="hydration"></a>**Pivotal Event**:
TO DO

-->

## Following & Contributing

To be updated about changes, follow me on <a href="https://mastodon.social/@lutzhuehnken" rel="me">Mastodon</a>, [Bluesky](https://bsky.app/profile/huehnken.de) or [LinkedIn](https://de.linkedin.com/in/lutzh). If you find this interesting, you might also like my [blog](https://www.reactivesystems.eu/blog/).


Please read the [contribution guidelines](contributing.md) if you'd like to contribute.


[^1]: Martin Fowler: [What do you mean by “Event-Driven”?](https://martinfowler.com/articles/201701-event-driven.html)

[^2]: Microsoft: [Domain events versus integration events](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/domain-events-design-implementation#domain-events-versus-integration-events)

[^3]: Frank de Jonge: [The different types of events in event-driven systems](https://frankdejonge.nl/blog/the-different-types-of-events-in-event-driven-systems/)

[^4]: Greg Young: [CQRS Documents](https://cqrs.wordpress.com/wp-content/uploads/2010/11/cqrs_documents.pdf)

[^5]: Toli Apostolidis: [EDA in Practice](https://youtu.be/wM-dTroS0FA?si=t-pwjXc-r9Jkn-6h&t=1350)

[^6]: Mathias Verraes: [DDD and Messaging Architectures](https://verraes.net/2019/05/ddd-msg-arch/) 

[^7]: Martin Fowler: [Event Sourcing](https://martinfowler.com/eaaDev/EventSourcing.html)

