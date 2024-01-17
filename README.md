This is a repository showing a problem with Maven `dependency:go-offline` with Maven Compiler plugin `annotationProcessorPaths`.
See https://issues.apache.org/jira/browse/MCOMPILER-571 for more information as well.

To reproduce the problem first run

```shell
./mvnw dependency:go-offline -Dmaven.repo.local=./local-m2-repo
```

and then run

```shell
./mvnw verify -Dmaven.repo.local=./local-m2-repo --offline
```

The second command fails to resolve the `mapstruct-processor` defined in the `annotationProcessorPaths` from the maven-compiler-plugin.
