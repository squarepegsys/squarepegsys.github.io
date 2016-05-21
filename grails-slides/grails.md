count: false

## Introduction to Grails 3

### Mike Hostetler

![Grails](img/grails-logo.jpg)
---

## About Me

I work for ![OPI](img/2015-OPI-Logo-Stacked.gif)

I code in : Java, Groovy, Python (in any order)

Also a board game nerd, which will will get into later.

#### Contact me!

 <i class="fa fa-github"></i>  https://github.com/squarepegsys/

 <i class="fa fa-twitter"></i> https://twitter.com/mikehoss42

 <i class="fa fa-rss"></i> http://mike.hostetlerhome.com

---

## What is Grails?

"Grails is a powerful web framework, for the Java platform aimed at multiplying developers’ productivity thanks to a Convention-over-Configuration, sensible defaults and opinionated APIs. It integrates smoothly with the JVM, allowing you to be immediately productive whilst providing powerful features, including integrated ORM, Domain-Specific Languages, runtime and compile-time meta-programming and Asynchronous programming."


![Grail](/img/monty_grail.gif)
---
## So, yeah, what is Grails?

Grails is a JVM web framework that has:

* smart domain model
* easy MVC structure
* code generation


And, in the end, you just deploy a `war` file.

![Grail](/img/very_nice.gif)
---

## So, what?

Grails uses:

* Groovy
* Spring
* Hibernate
* a rich plugin structure

If you want to get into Spring and Hibernate, you can. Or you can just use what Grails exposes.


<img src="/img/rabbit.jpg" width="400"/>

---
## Show me

```groovy

package foo

class User {

    String username
    String firstName
    String lastName
    String password
}

```

That will create a table called `user` with columns `username`, `first_name`, `last_name`, and `password`.

---

## Show me more

```groovy

package foo

class UserService {


   def save(User user) {
      user.save()
    }

}

```

A simple service that just saves the `User` object. Note that we didn't implement the `save` method.

---

## Impress me

```groovy

package foo

class UserController {

   def userService

   def save(User user) {
       userService.save(user)
   }

}

```

A `UserService` object gets injected into this controller in the `userService` field.

---
### Wow it's....

<img src="/img/magic.gif" width="400"/>

---

### A Brief History of Grails

* 2.0.0 released on Dec 15, 2011
* Used a custom build process based on Gant (this was from Grails 1!)
* Used source plugins (i.e. you put a plugin in your build's config, and the source was downloaded)

Things have changed a lot since 2011.....

---

### The end days of Grails 2

* Lots of Grails plugins for CSS/JS frameworks... but now we have `npm`
* Who uses ANT/Gant anymore? Now we have Maven and Gradle
* Grails 2 used a lot of Groovy introspection, which can be slow

---

### Announcing Grails 3!

* Based on Spring Boot
* Build with Gradle (no more custom build config)
* Plugins are compiled jars
* Uses the power of Spring Boot, so no longer need most of introspection

But......

---

### Grails 2 vs 3


* Plugins aren't compatible
* Some paths are different (like for tests)
* Configuration has completely changed

Last version of Grails 2 is 2.5.x (and it's a really solid release)

---

### ... And politics

* In January 2015, Pivotal announced they were no longer support Grails after March 31 -- and Grail 3 will be released then.
* And Grails 3.0.0 was released on time.... but few of the main plugins were ready
     * Spring Security (the main authentication plugin) wasn't released for Grails 3 until August 2015.
* Object Computing Inc (OCI) picked up Grails sponsorship on Apr 15, 2015.
* Grails 3.1.0 was promised in Dec 2015 and not released until last Jan 2016


---

![Mess](img/mess.gif)

---

### Current versions

(as I wrote this last Saturday):

* 3.1.6
* 3.0.17
* 2.5.4


![Mess](/img/choose_wisely.jpg)
---

### In the end, it's all Spring Boot

![Disquise](img/disquise.gif)
---

### What does Spring Boot give us?

* You can create a fat jar, so run your web app with `java -jar mygrailsapp.jar`
* Use Spring Boot Components in your app (like Camel)



---
### Demo

<img src="/img/sir_robin.gif" width="400"/>

---
### A little about BoardgameGeek

<img src="/img/geeklist.png" width="400"/>

---
### BGGer

https://github.com/squarepegsys/bgger

![BGG](img/bgg.jpg)

---
### Follow me!

Grails blog:
https://objectpartners.com/author/mhostetler/
