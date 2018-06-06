# sbt-datadog

This project is highly inspired by (actually, copied from) the fantastic [sbt-newrelic](https://github.com/gilt/sbt-newrelic) project.

We want to thanks [Gilt](http://tech.gilt.com) for their work on `sbt-newrelic` that permits us to create this project really quickly.
(The longuest part was the sbt <-> Bintray configuration 😄)

Prerequisites
-------------

The plugin assumes that sbt-native-packager has been included in your SBT build configuration.
This can be done by adding the plugin following instructions at http://www.scala-sbt.org/sbt-native-packager/ or by adding
another plugin that includes and initializes it (e.g. the SBT plugin for Play 2.6.x).


Installation
------------

Add the following to your `project/plugins.sbt` file:

```scala
addSbtPlugin("com.colisweb.sbt" % "sbt-datadog" % "0.1.0")
```

To enable the Datadog APM for your project, add the `DatadogAPM` auto-plugin to your project.

```scala
enablePlugins(DatadogAPM)
```

Configuration
-------------

To use a specific Datadog Java APM Agent version, add the following to your `build.sbt` file:

```scala
datadogVersion := "0.9.0"
```


For more configuration option, look at the Datadog Java APM agent documentation: https://docs.datadoghq.com/tracing/setup/java/