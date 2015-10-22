# Testing Existing Cookbooks

This training walks a team through adding tests and refactoring an existing body of cookbooks.

## Setup & Environment

This content starts with the apache cookbook created in the original [Chef Fundamentals](https://github.com/chef-training/chef-fundamentals-repo).

This content assumes that the learner has the Chef Development Kit installed.

This content assumes that the learner is able to run Test Kitchen on their workstation.

## Outline

### 01 - Building Cookbooks with Tests

The learner creates an apache cookbook. They start by writing an integration tests. Watching the test fail. Implementing the recipe. Watching the test pass.

### 02 - Refactoring Cookbooks with Tests

The learner is asked to refactor the test to meet team standards. They refactor the recipe using `include_recipe`. They run their test suite and see that everything passes. We ask them to heckle their code (remove source code). They see that the tests still pass. This is because running `kitchen converge` and `kitchen verify` against an already running instance will not reset the instance so it is already in the previously desired state. We ask them to run `kitchen test`. The test fail.

> The outcome here is that while integration tests gives you fast feedback, there has to be a better (and faster) way to test for regressions when the code changes.

### 04 - Faster Feedback with Unit Testing

We will now introduce ChefSpec as a way to test even faster. Unit tests are useful to test that regressions do not break your code, especially when there is mutability. They are run in memory, so that means you can test really fast!

We will write unit tests for the apache cookbook, and then modify the integration tests as well to ensure tests pass for the refactoring effort. For each unit test we write, we'll run `rspec -f d -c` to ensure the test passes. We'll refactor the integration tests as well.

### 04 - Troubleshooting

So now that we’ve refactored our cookbook and integrated tests into them now,  we should probably know how to troubleshoot chef runs. We will show the ability to introspect your Chef run using tools like `pry` and `irb` to inspect and dissect our chef run.

### 05 - Ohai Plugin

We will then look at Ohai, the chef-client discovery plugin that runs at the inception of every chef-client run. We will inspect the data ohai discovers, the command line utility, and the ability to create plugins with Ohai to discover custom data. It will be good to refresh everyone's knowledge that Ohai attributes can be used in recipes to provide dynamic data for use in your cookbooks.

> The Ohai content exists within the Chef Intermediate material.

### 06 - Free Form

Now that we have a lot of good hands-on knowledge writing tests, we will go ahead and refactor a team cookbook. We will take the approach we learned from Day 1 to write some tests for that cookbook cookbook. We will setup a kanban board, assign tasks, and pair together to start adding tests to your cookbooks.
