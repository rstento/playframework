<!--- Copyright (C) 2009-2017 Lightbend Inc. <https://www.lightbend.com> -->
# Examples and templates

Play provides example projects and templates to help you get started:

* To learn more about Play, try out the [example projects](#Using-Play-examples). Each showcases a particular feature or illustrates how to satisfy a common use case.
* When you are ready to build your own app, use a [template](#Using-templates). A template will set up the appropriate project structure and dev environment for you. 

**Note**: Templates are already configured with [[CSRF|ScalaCsrf]] and [[security headers filters|SecurityHeaders]], whereas example projects are not specifically set up for security out of the box.

This page provides information on:

* [Using Play examples](#Using-Play-examples)
* [Using templates](#Using-templates)
* 

## Using Play examples

Play examples are available from the Lightbend [Tech Hub](https://developer.lightbend.com/start/?group=play). The [Overview of available examples](#Overview-of-available-examples) section below briefly describes examples by category. For your first experience with Play, we suggest the Play Starter Project for Java or Scala.   

After choosing an example from [Tech Hub](https://developer.lightbend.com/start/?group=play), follow these steps:

1. Click CREATE A PROJECT FOR ME to download the zipped project.
1. Unzip the project in a convenient location.
1. In a command window, navigate to the top level project directory.
1. Enter one of the following commands:
   On OSx or Linux systems: `/sbt run` or `./gradle runPlayBinary`
   On Windows systems: `sbt run` or `gradle runPlayBinary`
  
   The build tool downloads dependencies and compiles the project. When it finishes, enter the following URL in a browser to view the app:
   
   `http://localhost:9000`
  
  
## Using templates

If you have [sbt 0.13.13 or higher](http://www.scala-sbt.org) installed, you can create a Play project using a minimal [giter8](http://foundweekends.org/giter8) seed template (similar to a maven archetype). This is a good choice if you already know Play and want to create a new project immediately. You can also create your own giter8 templates by forking from the https://github.com/playframework/play-java-seed.g8 or https://github.com/playframework/play-scala-seed.g8 github projects.

In a command window, enter one of the following lines to create a project using a seed template:

### Play Java Seed

```bash
sbt new playframework/play-java-seed.g8
```

### Play Scala Seed

```bash
sbt new playframework/play-scala-seed.g8
```

After that, use `sbt run` and then go to http://localhost:9000 to see the running server. If you plan to use forms in your application, enter `sbt g8Scaffold form` to create the scaffold controller, template and tests needed to process a form.

## Examples by category

Both Lightbend [Tech Hub](https://developer.lightbend.com/start/?group=play) and github offer a variety of Play examples. Some are available for different versions of Play. The following sections organize some of these examples by category, describe them briefly, and provide links to Tech Hub, where you can download them as zip files. 

### ORM layers 

Play examples demonstrate how to use the folloing ORMs:

* [Slick](http://slick.lightbend.com/docs/) is a Functional Relational Mapping (FRM) library for Scala that makes it easy to work with relational databases. It allows you to work with stored data almost as if you were using Scala collections while at the same time giving you full control over database access and data transfer. You can also use SQL directly. Database actions execute asynchronously, making Slick a perfect fit for your reactive applications based on Play and Akka. The following Play examples use Slick:
    * [play-isolated-slick](https://developer.lightbend.com/start/?group=play&project=play-scala-isolated-slick-example-2.5.x): This project uses a multi-module that hides Slick 3.x behind an API layer, and does not use Play-Slick integration.  It also contains sbt-flyways and use Slick's code generator to create the Slick binding from SQL tables.
    
    * [Computer Database with Play-Slick](https://github.com/playframework/play-slick/tree/master/samples/computer-database): This template uses [Play Slick](https://www.playframework.com/documentation/%PLAY_VERSION%/PlaySlick).  You will need to clone the `play-slick` project from Github and type `project computer-database-sample` in SBT to get to the sample project.

* play-scala-intro [for Scala](https://developer.lightbend.com/start/?group=play&project=play-2.4.x-scala-intro) or [for Java](https://developer.lightbend.com/start/?group=play&project=play-2.4.x-java-intro): This project demonstrates how to create a simple CRUD application.

* JPA This is a example template showing Play with Java Persistence API (JPA), using Hibernate Entity Manager.  It is included in the Play project itself. [play-java-intro](https://github.com/playframework/play-java-intro)

* This is an example template showing Play with [Anorm](https://github.com/playframework/anorm) using Play's [Anorm Integration](https://www.playframework.com/documentation/latest/ScalaAnorm).  It also uses [Play-Bootstrap](https://adrianhurt.github.io/play-bootstrap/) for easy template scaffolding. [playframework/play-anorm](https://github.com/playframework/play-anorm)


* This is an example template that uses [Ebean](https://ebean-orm.github.io/) using Play's [Ebean integration](https://www.playframework.com/documentation/%PLAY_VERSION%/JavaEbean). It also uses [Play-Bootstrap](https://adrianhurt.github.io/play-bootstrap/) for easy template scaffolding. [playframework/play-ebean-example](https://github.com/playframework/play-ebean-example)

### Streaming

* This is an example template that shows streaming responses through Comet or Server Sent Events (SSE), using Akka Streams:

    * [playframework/play-streaming-scala](https://developer.lightbend.com/start/?group=play&project=play-scala-streaming-example)
    * [playframework/play-streaming-java](https://developer.lightbend.com/start/?group=play&project=play-java-streaming-example)


* This is an example template that shows bidirectional streaming through the WebSocket API, using Akka Streams:
    * [playframework/play-websocket-scala](https://developer.lightbend.com/start/?group=play&project=play-scala-chatroom-example)
    * [playframework/play-websocket-java](https://developer.lightbend.com/start/?group=play&project=play-java-chatroom-example)

### Security and Cryptography

* Play Secure HTTP(SSL/TLS) Example uses the Java Secure Socket Extension API:
    * [for Scala](https://developer.lightbend.com/start/?group=play&project=play-scala-tls-example)
* Play Scala Secure Session Example shows how to encrypt and sign data securely with [Kalium](https://github.com/abstractj/kalium): [playframework/play-kalium](https://developer.lightbend.com/start/?group=play&project=play-scala-secure-session-example)

### Dependency Injection

* [[Compile time dependency injection|ScalaCompileTimeDependencyInjection]] can be done in Play in a number of different DI frameworks.

There are two examples shown here, but there are other compile time DI frameworks such as Scaldi, which has [Play integration](http://scaldi.org/learn/#play-integration) built in, and [Dagger 2](https://google.github.io/dagger/), which is written in Java.

* This is an example template showing how to use manual compile time dependency injection and manual routing with the [[SIRD router|ScalaSirdRouter]], useful for minimal REST APIs and people used to Spray style routing: [playframework/play-scala-compile-di-example]((https://developer.lightbend.com/start/?group=play&project=play-scala-compile-di-example)


This is an example template showing compile time dependency injection using [Macwire](https://github.com/adamw/macwire).  [playframework/play-macwire-di](https://github.com/playframework/play-macwire-di)