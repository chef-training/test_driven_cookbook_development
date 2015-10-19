# Testing Existing Cookbooks

This training walks a team through adding tests and refactoring an existing body of cookbooks.

## Setup & Environment

This content starts with the apache cookbook created in the original [Chef Fundamentals](https://github.com/chef-training/chef-fundamentals-repo).

This content assumes that the learner has the Chef Development Kit installed.

This content assumes that the learner is able to run Test Kitchen on their workstation.

## Outline

We will use the training apache cookbook for the basis of the trainings. Since the apache cookbook does not have tests, we will start by writing integration (serverspec) tests in CHEF-DK against that cookbook. We will iterate over each
test we write until all of our test “pass”. `kitchen converge` the VM with the apache cookbook. Write a test, run `kitchen verify`, rinse, repeat.

We then introduce refactoring the apache cookbook by splitting out the default recipe into separate recipes to make understanding the cookbook easier. We’ll re-run `kitchen verify` again, show the tests pass, then run `kitchen destroy` and `kitchen test`. The tests will now fail, because we were running tests against an already converged VM. At the point, we will retro on what we did, why it was valuable, and what were somethings we could do better. The outcome here is that while CHEF-DK integration tests gives you fast feedback, there has to be a better (and faster) way to test for regressions when the code changes.

We will now introduce ChefSpec as a way to test even faster. Unit tests are useful to test that regressions do not break your code, especially when there is mutability. They are run in memory, so that means you can test really fast!

We will write unit tests for the apache cookbook, and then modify the integration tests as well to ensure tests pass for the refactoring effort. For each unit test we write, we'll run `rspec -f d -c` to ensure the test passes. We'll refactor the integration tests as well.

So now that we’ve refactored our cookbook and integrated tests into them now,  we should probably know how to troubleshoot chef runs. We will show the ability to introspect your Chef run using tools like `pry` and `irb` to inspect and dissect our chef run.

We will then look at Ohai, the chef-client discovery plugin that runs at the inception of every chef-client run. We will inspect the data ohai discovers, the command line utility, and the ability to create plugins with Ohai to discover custom data. It will be good to refresh everyone's knowledge that Ohai attributes can be used in recipes to provide dynamic data for use in your cookbooks.

> The Ohai content exists within the Chef Intermediate material.

Now that we have a lot of good hands-on knowledge writing tests, we will go ahead and refactor a team cookbook. We will take the approach we learned from Day 1 to write some tests for that cookbook cookbook. We will setup a kanban board, assign tasks, and pair together to start adding tests to your cookbooks.
