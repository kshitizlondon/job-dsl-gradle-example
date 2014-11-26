[![Build Status](https://buildhive.cloudbees.com/job/sheehan/job/job-dsl-gradle-example/badge/icon)](https://buildhive.cloudbees.com/job/sheehan/job/job-dsl-gradle-example/)

# Jenkins Job DSL Gradle Example 

An example [Job DSL](https://github.com/jenkinsci/job-dsl-plugin) project that uses Gradle for building and testing.

## File structure

    .
    ├── jobs              # DSL script files
    ├── src
    │   └── main
    │       └── groovy    # support classes
    │   └── test
    │       └── groovy    # specs
    └── build.gradle      # build file

## Commands

* `./gradlew test` runs the specs.
* `./gradlew workspace` copies src files and DSL scripts to `build/workspace`.

## Seed job configuration settings

* Invoke Gradle script → Use Gradle Wrapper: `true`
* Invoke Gradle script → Tasks: `clean test workspace`
* Process Job DSLs → DSL Scripts: `build/workspace/**/*.groovy`
* Publish JUnit test result report → Test report XMLs: `build/test-results/**/*.xml`
