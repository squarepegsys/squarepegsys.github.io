count: false

## Catching a Ride on Apache Camel

### Mike Hostetler

![mickey](img/img1.gif)
---

## About Me

I work for ![OPI](img/2015-OPI-Logo-Stacked.gif)

I code in : Java, Groovy, Python (in any order)

Also a board game nerd (more on that later)

#### Contact me!

 <i class="fa fa-github"></i>  https://github.com/squarepegsys/

 <i class="fa fa-twitter"></i> https://twitter.com/mikehoss42

 <i class="fa fa-rss"></i> http://mike.hostetlerhome.com

---
## First off ....

<img src="img/firehose.gif" width="400">

---
## Agenda

* What is Camel?
* Use Cases
* Camel Routes
* Anatomy of a Message
* Camel Gotchas
* Demo


---

## What is Camel?

The official definition:

>    Apache Camel ™ is a versatile open-source integration framework based on known Enterprise Integration Patterns.
Camel empowers you to define routing and mediation rules in a variety of domain-specific languages, including a Java-based Fluent API, Spring or Blueprint XML Configuration files, and a Scala DSL. This means you get smart completion of routing rules in your IDE, whether in a Java, Scala or XML editor.

---

## What is Camel?

Mike's Definition

>    Apache Camel ™ is an open-source integration framework that allows you to use various DSLs to receive, move, convert, and deliver messages.

The Enterprise Integration Patterns (EIPs) are important too &mdash; they describe what Camel can do with messages.

---

## What is Camel?

EIPs are the beyond the scope of this talk, but see: http://www.enterpriseintegrationpatterns.com/

Common EIPs are:

* Routing
* Splitter
* Normalizer (A type of Transformer)
* Aggregator


---

## What is Camel?

Some endpoints (source and destination points)

* JMS
* Twitter
* Database
* Filesystem
* Quartz
* Spring Bean
* REST service
* XML service

These are specified by a URI-like entry:

     twitter://search?type=direct&keywords=camel....

     jms:queue:MyQueue

---

## What is Camel?

Here are other killer features

* Error handling
* Transactions
* Different ways to configure (DSL vs XML)

![Take Note](/img/take-note.gif)

---
## What is Camel?

In short, Camel delivers a message where you want and in the format you want them. You know, like a caravan.

![Caravan](/img/race.gif)
---

## Use Cases


Why use Camel?

![Why](/img/why.gif)

---

## Use Cases

Connecting different applications together

![Integration](/img/integration.png)
---

## Use Cases

Moving and transforming data from a database to an XML File and then sftp it.

![SFTP](/img/sftp.png)

---
## Camel Routes

![Jump](/img/camel_jump.gif)

---

## Camel Routes

 * Routes start with a `from` endpoint (`sftp`, `jms`, `quartz`, another route)
 * Routes end with a `to` endpoint (`sftp`, `jms`, `quartz`, another route)
 * You "do things" to the message in between

![eat](/img/camel_eat.gif)
---

## Camel Routes

### What things?

Like Common EIP Patterns

* Routing
* Splitter
* Normalizer
* Aggregator

![circus](/img/camel_circus.gif)

---
## Anatomy of a Message

![Anatomy](/img/camel_dromedary_diagram.jpg)
---


## Anatomy of a Message

![Exchange](/img/camel_exchange.png)
---


## Camel Gotchas

![Gotchas](/img/camel_attack.gif)

---
## Camel Gotchas

When working with the Exchange directly, alter the existing `IN` message instead of creating a new `OUT` message.The `OUT` message will get re-written and you will wonder where your message is! However it's easier to simply work with the `IN` message anyway.

We will see this in the demo.

![IN vs OUT](/img/in_out.gif)
---

## Camel Gotchas

There are different methods to send a message from one route to another. If you use `direct`, it's fast but it many not run under it's own transaction, even if you set it. If you use `seda`, it can run in it's own transaction but it will be slower.

![Transactions](/img/camel_transactions.gif)

---

## Demo

![Transactions](/img/camel_demo.gif)
---

## Things not covered

* Error handling - Dead Letter Channel
* Transactions Per Route
* Monitoring
