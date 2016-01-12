# Fixes TRP Typesafe Reactive Platform version

Just a few small changes to fix ensime scalap and scala version

- Before doing sbt, export variable ```JDK_LANGTOOLS_SRC```
```
export JDK_LANGTOOLS_SRC=./src/sbt-test/ensime-sbt/ensime-server/openjdk-langtools/openjdk8-langtools-src.zip
```
- Clone this repository and later ```publishLocal```.
Remember to delete ivy cache (If you have downloaded the same version before)

Add these lines to `~/.sbt/0.13/plugins/plugins.sbt`

```scala
addSbtPlugin("org.ensime" % "sbt-ensime" % "1.0.1-SNAPSHOT")
```

## Sync changes with ensime github
### First time
- git remote add ensime git@github.com:ensime/ensime-sbt.git

### Later
- `go master` or `1.0`
- `git pull ensime master`
- `go trp_version`
- `git rebase -i master`

## Commands

* `ensimeConfig` --- Generate a `.ensime` for the project (takes space-separated parameters to restrict to subprojects).
* `ensimeConfigProject` --- Generate a `project/.ensime` for the project definition.

Note that downloading and resolving the sources and javadocs can take some time on first use.

(Copied from [EnsimePlugin.scala](https://github.com/ensime/ensime-sbt/blob/master/src/main/scala/EnsimePlugin.scala#L59))
