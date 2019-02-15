# `hive-exec-jar`

## Purpose

This is meant only for Spark with Hive integration when using Hadoop 3.

Currently, Hive for Spark is of a special forked variant and can only reach up
to `1.2.1-spark2`, which doesn't support Hadoop 3 officially. It is possible to
successfully build with Hadoop 3 + Hive `1.2.1-spark2` integration, but using
Spark at runtime will start failing, with error message stating that Hive does
not recognize Hadoop 3 as a major version.

This repository exists to circumvent the above limitation by building a modified
version of Hive for `1.2.1-spark2` to generate the affected Hive JAR, but be
warned that there is no guarantee that Hive will run stably with the Hadoop 3
integration for Spark.

The build is done via CI/CD, and the affected JAR is publish as a GitHub
release.

## How to use

Simply replace the original
`${SPARK_HOME}/jars/hive-exec-1.2.1.spark2.jar` in your Spark with Hadoop 3 +
Hive integration, with this JAR of the same name in the release page.
