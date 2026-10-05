# Overview 

This example demonstrates the creation and use of a Legend service execution library.

`legend-guided-tour-application` depends on the `guided-tour-service-execution` service jar
(published to the GitLab Maven registry declared in its `pom.xml`) and runs the
`org.finos.legend.showcase.guided_tour.service.m2m.service1` service in-process via
`ServiceRunnerBuilder`.

## Prerequisites

- **JDK 17** (CI uses Eclipse Temurin 17; see
  [`.github/workflows/check-service-execution-example.yml`](../../.github/workflows/check-service-execution-example.yml)).
- Maven 3.6.3 or later.
- Network access to Maven Central and `https://gitlab.com/api/v4/projects/38029096/packages/maven`.

## Build and test

From `examples/service-execution-jar/legend-guided-tour-application/`:

```sh
java -version   # should report 17
mvn -B -ntp clean verify
```

`verify` runs `LegendApplicationTest`, which executes the M2M service and asserts the
returned firm legal names are, in order:

- `ACME Corp.`
- `Monsters Inc.`

Do not pass `-DskipTests`; the test is the end-to-end check of the service execution.

## Output

`package` produces two jars in `target/`:

- `legend-guided-tour-application-0.0.1-SNAPSHOT.jar` — the application classes only.
- `legend-guided-tour-application-0.0.1-SNAPSHOT-shaded.jar` — a self-contained jar with all
  dependencies, attached with the `shaded` classifier.

## Run

```sh
java -jar target/legend-guided-tour-application-0.0.1-SNAPSHOT-shaded.jar
```

`LegendApplication.main` executes the service but discards the result, so it prints no query
rows; a clean exit (status 0) means the service ran. Use the test above to see the firm names
checked.
