# JUnit Categories and Cucumber Bug

Sample project to demonstrate a bug when using [JUnit Categories](https://github.com/junit-team/junit4/wiki/Categories) and Cucumber in the same Gradle project

When executing the following build command

    ./gradlew test

The build fails with an InitializationError and the following stacktrace is printed to the test report standard out:

```
java.lang.NullPointerException
	at org.junit.runner.Description.createSuiteDescription(Description.java:124)
	at org.gradle.api.internal.tasks.testing.junit.CategoryFilter.shouldRun(CategoryFilter.java:47)
	at org.junit.runners.ParentRunner.shouldRun(ParentRunner.java:434)
	...
```

## Credit
This bug was originally reported by [Kristian Rosenvold](https://discuss.gradle.org/users/Kristian_Rosenvold) on
the [Gradle Forum](https://discuss.gradle.org/t/npe-with-excludecategories-and-cucumber/13969) and this project is
essentially the test case he provided on that post.