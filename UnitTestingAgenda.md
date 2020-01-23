##  UnitTesting Course Agenda

### Section 0:  Introduction

This section covers the overall theory of automated testing, generic and related to both local work and a CI/CD pipeline.

The first purpose of testing is to improve quality, but the second purpose is to use it to improve code progress and direction.  Tests can also be thought of as documentation, because it can clearly show how to use a particular piece of software.
Tests have to be easy to run, easy to write and maintain. One also need to strive to make them not overy implementation dependendant. We will look at goals of software testing to ensure a common understanding.

We cover the fundamentals of automated testing, including the basics of a *Shift Left* strategy for development.  It is not enough with only the low level unit tests, tests are needed on more comprehensive levels too. The way to organize this is to be establish *Levels* of testing, and we work through the general principles of this, and also do an exercise in how this can be done for your software. We also work through how this can be reflected in your code and source code structure conventions, so that this can be utilized in automated builds.

Tests should exist in the *developers face*.  This calls for practices like TDD, but also using tools like *live testing* if possible.  TDD is very hard to master, so we'll look at what it really means and how you can benefit without being overly zealous.  It calls for knowledge about making testable code, defining coupling, cohesion and contracts, and how you do mocking to isolate your code from its dependencies.

Tests should run during builds, and that may be a larger suite than what the developer normally does.  It should further be used for gating purposes, as part of pull request policies, and it should be used at approval stages.  We work through these principles, and see how you can decide where to apply what.

Tests do have a cost, and you should also be aware of the pitfalls.  Tests obsolence, over-testing, lack of test maintenance, slow tests, flaky tests,  are some of these. We will take a look at some architectural and process test anti-patterns.

Learning to identify test smells, and their corresponding test patterns is a good way to stay ahead of test mess.


### Section 1: Test Driven Development and Class Based Unit Testing

#### 1a: Fundamentals of TDD

We work through the fundamentals of how to do TDD, in a practical manner.  The way you code may affect how you add tests.  There is not necessarily a *one way* for everything and everybody.  We will look at how you can ensure your code ends up being testable and tested before you commit it.  

We will cover the use of fixtures and tests.

#### 1b: Using SRP thinking and interfaces for isolation

The Single Responsibility Principle comes out very clear when working with TDD. To be able to isolate your unit, you need to utilize interfaces, and define clearly *what* your interfaces are.  We work through how you can safely modify your code so as to make it more testable using these principles.

#### 1c: Mocking, autofixtures, stubbing and faking

Mocking frameworks are very useful when defining the behaviour of your dependencies.  There are also ways like stubbing and faking. We work with when you use what, and the effect of the different methods.  We also look at state versus behaviour testing, and how you can keep your testing code simple.

### Section 2: Testing legacy code

This can be a huge investment.  It is hard to add testing to existing code.  It may work for the simplest cases, but more often than not, it will require at least some refactoring, but often more drastic measures like rewrites or even redesign.  There are some ways to get at least a certain level of control, and we will work through some of these.  There are also some resolution patterns that can be used.  

The tests will be added after the fact, and this is one case where a broader scope testing can come in handy.  There is no golden path to the goal here, you need to work with all the principles in your toolbox to be successful.  

### Section 3: Data driven tests

Data driven tests can be done both at the class level and higher levels.  We'll focus on the class level since the same principles and practices apply to higher levels.  Data driven tests can be very useful and can simplify existing tests, but it can also lead to over-testing.  We'll look at the different ways of doing this, and also how you can use test functionality to minimize the data you need to inject.

### Section 4: Component and Integration testing

We will look at how components can be isolated, so that we can more easily test them one by one. This is dependent upon your dependency tree, and also on how you have managed to implement Dependency Injection in your system.  

Integration testing are done with multiple components, and often involve a data store. This causes more work to be done to set things up, and issues like test data maintenance comes up.  

### Section 5: Test automation and end-to-end testing

Testing at the API level is fine for some systems, but in some cases you will go all the way out to UI testing. There are frameworks for doing this kind of testing, and also test languages specifically for this purposes.  We will look at these, and see how and when they can be used, and what consequences they will have.

### Section 6: Testing during CI/CD

We'll see how you can add tests to a build used for CI/CD.  The exercises will focus on Azure DevOps Pipelines and Github actions. The way we do it is pretty similar.  We will also look at some of the reporting coming out of this.

In order to make this work, you need to have your test levels (see introduction) in place, and a proper convention for these in your source code structure and code.

We will then see how this can be used to gate pull requests, and ensure your master branch is clean.

### Section 7: Using metrics to evaluate testing

We will look at different metrics for how you can measure the effectiveness of your testing.  This includes code coverage, but there are also more ways to look at this.  Using code coverage also creates challenges regarding what you measure, what should be included and not, so that you get some meaningfullness in your results.

### Optional Section A: API and contract testing

If you have a serviceoriented system of some kind, you will need to test not only your services (Component/Integration), but also the contracts used between for the services.  Setting up a seperate test system for testing your services can prove very useful when things start to change.  This require a certain organization of your artifacts, but once done, this technique can prove very useful.

*Include this section if you have an extensive API based system*

### Optional Section B:  Test Reporting

Dependent upon your organisation, you may require a certain level of test reporting.  There are multiple ways to go about this, and we will look at some possibilities.  The build-in reporting in tools like Azure DevOps can be very useful, but there are also other tools than can be used to get a better view.

### Optional Section C:  The structure of Visual Studio testing infrastructure  

The optional section explains how the Visual Studio (including dotnet) test infrastructure is constructed, which components are involved and how they interact.  This also applies to Visual Studio Code and Jetbrains Rider IDE, and also when using the Resharper plugin.  It explains what components you should use, and which to avoid.  It also explains how you ensure your projects are properly set up for best use of the infrastructure.

Visual Studio have real time test discovery and it has live unit testing, how does this affect the developer, and what should the developer be aware of.
