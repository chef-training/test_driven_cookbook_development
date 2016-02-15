## Outline

This is the current proposed outline. This may not be inline with the current agenda or with the slides as this outline will change as new requirements surface.

### 01 - Introduction

Welcomes to the content. Sets expectations. Asks them to connect to their remote workstations.

### 02 - Why Write Tests? Why is that Hard?

This is a discussion based section that attempts to engage all the learners present in the training. Specifically this is to bring in the individuals that may feel outside of the group; those not convinced there is value in testing. This section does not try to dissuade them and instead it does my best work to try and embrace them and invite them to listen and discuss their feelings.

TODO: Have a discussion on 'Why write tests first before the code?'

### 03 - Writing a Test First

The learner creates an apache cookbook. They start by writing an integration tests. Watching the test fail. Implementing the recipe. Watching the test pass.

### 04 - Refactoring Cookbooks with Tests

The learner is asked to refactor the test to meet team standards. They refactor the recipe using `include_recipe`. They run their test suite and see that everything passes. We ask them to heckle their code (remove source code). They see that the tests still pass. This is because running `kitchen converge` and `kitchen verify` against an already running instance will not reset the instance so it is already in the previously desired state. We ask them to run `kitchen test`. The test fail.

> The outcome here is that while integration tests gives you fast feedback, there has to be a better (and faster) way to test for regressions when the code changes.

### 05 - Faster Feedback with Unit Testing

We will now introduce ChefSpec as a way to test even faster. Unit tests are useful to test that regressions do not break your code, especially when there is mutability. They are run in memory, so that means you can test really fast!

We will write unit tests for the apache cookbook's default recipe focusing on the two recipes that were included (install and service).

### 06 - Testing Resources in Recipes

We will use ChefSpec to test the remaining resources within the two recipes (install and service).

### 07 - Refactoring to Attributes

We will refactor the two recipes so that they use node attributes. We also introduce Pry to show you how you can use it to troubleshoot your recipes.

### 08 - Refactoring for Multiple Platforms

We will refactor the attributes to provide support for multiple platforms. We will define tests that simulate the various platforms in our unit tests. We will talk about adding a new platform to the integration testing.

### 09 - Implementing a Single Configuration

The next requirement is to have the ability to drop in a new site on the port 8080. This is done through a apache configuration file. The learner will first define an integration test that fails. Then the learner will explore the first platform to discover the location of where configuration files are placed. Implement the configuration for the first platform and watch the test pass.

Running the tests for all platforms the learner sees second platform fails. Then the learner will explore the second platform to discover the location of where configuration files are placed on that platform. Update the implementation so that the integration tests passes for both platforms.

The learner implements unit tests for each of the affected recipes and resources

### 10 - Refactoring to a Custom Resource

The current implementation of one configuration file that places a configuration file is prescriptive. Even with node attributes in the implementation the solution only allows for one site to be deployed on one configured port. The learner is walked through generating a custom resource that allows multiple configuration files to be implemented.

The learner writes unit tests that validate the new custom resource.
