These guidelines are not here to annoy our GSOC students, but to make review, acceptance and on going maintenance of your work easier.

## Tests

Please develop tests in parallel with your implementation code and not as an after thought. Even better if the nature of the project lends itself to it, develop the tests first, see https://en.wikipedia.org/wiki/Test-driven_development

The expectation is for non-UI code that the coverage is near 100% and for UI code at least all "happy" paths have been exercised.

Run a static code analyser/checker on yout

## Building and source control

Please use gradle for building your project and git for source control.

GSOC projects code should preferably be hosted on github.

If you are coding against a code base that is being actively developed in parallel, please rebase regularly on the "main" (historically "master") development branch and expect to be asked to do that again immediately before your code is merged. Never ever, really: __NEVER EVER__, merge with the main branch, always rebase on it. The maintainer of the project will merge your branch/PR when it is ready.

If on the other hand your project is stand alone please setup a CI system that at least builds your project and runs your tests.

## Coding style

#### Java

- indentation 4 spaces
- opening braces  on the same line as the condition in control statements
- always bracket statements in control structures
- classes, methods, fields and variables should use Java naming conventions and qualifier ordering.

See https://www.oracle.com/technetwork/java/codeconventions-150003.pdf for examples.

#### Kotlin

See https://kotlinlang.org/docs/coding-conventions.html

## Annotations and documentation

#### Java

Please document all methods and arguments with javadoc, even if it seems a bit silly, it just makes working with modern IDEs so much easier.

Use @NonNull/Notnull and @Nullable annotations, do NOT use annotation systems that replace actual Java code (for example getters and setters) or create any kind of DSL.

## Language levels/versions

#### Java

For code that is expected to run on a conventional JVM (that is OpenJDK or Oracles Java), Java 11 should be targeted. Anything that has even the slightest chance of running on Android however (which is nearly everything these days) should target Java 8 for language features, and needs to take the partial implementation of the libraries on Android in to account, see https://developer.android.com/studio/write/java8-support. Note that there are often surprising omissions and that you should not be relying on the "Java 8+ API desugaring" support (which is bug ridden and not going to make you happy).

## Progress tracking

Using the available github tools (issues, projects) makes it a lot easier for you to document your progress, and allow the mentors to see what is going on at a glance.

## General

Please use available tools for quality assurance, coding style adherence and formatting.

You can expect your code to be run at least through Sonar so it would be prudent to do the same. Free accounts are available at https://sonarcloud.io/, code checks can be run automatically from your CI system. The output from all such systems should be taken with a grain of salt, and feel free to ignore warnings if you think that is warranted, however you should be ready to defend your decision.

## DON'T GET SIDE TRACKED

We often spend inordinate amounts of time on meta issues with our tools, build pipelines and so on. GSOC however is the google summer OF CODE, what counts in the end, and will be the most satisfactory outcome for you, is that you've produced useful, mergable code that is used in production. If you run in to hiccups with achieving that goal, please speak up early and contact your mentors.
