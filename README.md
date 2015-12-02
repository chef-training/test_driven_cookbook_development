# Test Driven Cookbook Development

## Agenda

Test Driven Cookbook Development is a comprehensive instructor-led course exploring Test-driven development (TDD) through explanation, demonstration, practice, and discussion.

Building cookbooks with tests will increase the speed at which you work by giving you consistent feedback throughout the entire cookbook development process.

Participants will learn how to confidently create and extend a cookbook using Foodcritic, Rubocop, ChefSpec, and ServerSpec. At the end of the course, learners will have created a code repository that can reviewed and applied to solve real business problems.

Course Agenda:

* Introduction
* Integration Testing
* Using and Configuring Foodcritic
* Using and Configuring Rubocop
* Refactoring Cookbooks with Tests
* Faster Feedback with Unit Testing
* Testing Resources in Recipes
* Testing while Refactoring to Attributes
* Testing while Refactoring to Multiple Platforms

## Setup & Environment

This content starts with the apache cookbook created in the original [Chef Fundamentals](https://github.com/chef-training/chef-fundamentals-repo).

This content assumes that the learner has the Chef Development Kit installed.

This content assumes that the learner is able to run Test Kitchen on their workstation.

## Outline

This is the current proposed outline. This may not be inline with the current agenda or with the slides as this outline will change as new requirements surface.

### 01 - Building Cookbooks with Tests

The learner creates an apache cookbook. They start by writing an integration tests. Watching the test fail. Implementing the recipe. Watching the test pass.

### 02 - Refactoring Cookbooks with Tests

The learner is asked to refactor the test to meet team standards. They refactor the recipe using `include_recipe`. They run their test suite and see that everything passes. We ask them to heckle their code (remove source code). They see that the tests still pass. This is because running `kitchen converge` and `kitchen verify` against an already running instance will not reset the instance so it is already in the previously desired state. We ask them to run `kitchen test`. The test fail.

> The outcome here is that while integration tests gives you fast feedback, there has to be a better (and faster) way to test for regressions when the code changes.

### 03 - Faster Feedback with Unit Testing

We will now introduce ChefSpec as a way to test even faster. Unit tests are useful to test that regressions do not break your code, especially when there is mutability. They are run in memory, so that means you can test really fast!

We will write unit tests for the apache cookbook's default recipe focusing on the two recipes that were included (install and service).

### 04 - Testing Resources in Recipes

We will use ChefSpec to test the remaining resources within the two recipes (install and service).

### 05 - Testing while Refactoring to Attributes

We will refactor the two recipes so that they use node attributes. We also introduce Pry to show you how you can use it to troubleshoot your recipes.

### 06 - Testing while Refactoring for Multiple Platforms

We will refactor the attributes to provide support for multiple platforms. We will define tests that simulate the various platforms in our unit tests. We will talk about adding a new platform to the integration testing.

### 07 - Implementing a Single Configuration

The next requirement is to have the ability to drop in a new site on the port 8080. This is done through a apache configuration file. The learner will first define an integration test that fails. Then the learner will explore the first platform to discover the location of where configuration files are placed. Implement the configuration for the first platform and watch the test pass.

Running the tests for all platforms the learner sees second platform fails. Then the learner will explore the second platform to discover the location of where configuration files are placed on that platform. Update the implementation so that the integration tests passes for both platforms.

The learner implements unit tests for each of the affected recipes and resources

### 08 - Refactoring to a Custom Resource

The current implementation of one configuration file that places a configuration file is prescriptive. Even with node attributes in the implementation the solution only allows for one site to be deployed on one configured port. The learner is walked through generating a custom resource that allows multiple configuration files to be implemented.

The learner writes unit tests that validate the new custom resource.
