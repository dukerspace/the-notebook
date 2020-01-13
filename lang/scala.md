---
id: scala
title: Scala
type: docs
path: the-notebook/lang/scala
---

#### SBT Check Dependencies

#### Common
- ถ้ารันบน sbt จะแบ่งแรมกับ jvm เช่น 512MB / 2

#### SBT Check Dependencies
- .sbt create folder name "plugins"
- create file "sbt-updates.sbt"
- in sbt-updates.sbt type "addSbtPlugin("com.timushev.sbt" % "sbt-updates" % "0.3.0")"
- use update cmd "dependencyUpdates"

#### SBT
libraryDependencies += "org.scalatestplus.play" %% "scalatestplus-play" % "2.0.0" % Test
libraryDependencies += "com.rabbitmq" % "amqp-client" % "4.1.0"
%% library ของ scala
% library ของ java

#### Learning
- https://www.scala-exercises.org/
- https://www.cs.helsinki.fi/u/wikla/OTS/Sisalto/examples/

#### SBT Stage
- sbt "project projectName" start, sbt "project webapp" start
- sbt > stage
- run ผ่าน git bash ./bin/webapp

#### Akka
- [AKKA สุดยอด Reactive Toolkit](www.howtoautomate.in.th/akka-best-reactive-toolkit)
- [Reactive Programing](http://www.somkiat.cc/reactive-programming/)
