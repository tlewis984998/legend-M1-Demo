# Overview 

This example demonstrates the creation and use of a Legend service execution library.

## Prerequisites

- JDK 17 or newer
- Maven 3.6.3 or newer

The build's `maven-enforcer-plugin` rule fails fast on older JDKs or Maven versions.

## Build and test

```bash
cd legend-guided-tour-application
mvn -B -ntp clean verify
```

`LegendApplicationTest.testM2MMapping` executes the guided-tour M2M service and expects the firm names `[ACME Corp., Monsters Inc.]`.

## Run

The build produces a shaded jar with `org.finos.legend.demo.app.LegendApplication` as its `Main-Class`:

```bash
java -jar target/legend-guided-tour-application-0.0.1-SNAPSHOT-shaded.jar
```

## Dependency source

`org.finos.legend.showcase:guided-tour-service-execution` is resolved from the Maven registry of public GitLab project [38029096](https://gitlab.com/api/v4/projects/38029096/packages/maven) (no authentication required), pinned to snapshot `master-20230605.195306-3`.

## CI

[`.github/workflows/check-service-execution-example.yml`](../../.github/workflows/check-service-execution-example.yml) builds, tests, and smoke-runs this example on JDK 17 for pushes to `master` and pull requests that touch it.
