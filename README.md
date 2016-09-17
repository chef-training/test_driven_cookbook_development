# Test Driven Cookbook Development

This is a repository for developing Test Driven Cookbook Development.

Within this repository you will find:

* Test Driven Cookbook Development Course (8 hours)
* Demo - Test Driven Cookbook Development (1 hour)
* Demo - Writing Great Unit Tests with ChefSpec (1 hour)

## Test Driven Cookbook Development Course

### Abstract / Description

Test Driven Cookbook Development is a comprehensive instructor-led course exploring Test-driven development (TDD) through explanation, demonstration, practice, and discussion.

Building cookbooks with tests will increase the speed at which you work by giving you consistent feedback throughout the entire cookbook development process.

Participants will learn how to confidently create and extend a cookbook using ChefSpec and InSpec. At the end of the course, learners will have created a code repository that can reviewed and applied to solve real business problems.

### Learner Requirements

Participants need a network-enabled laptop with a terminal that supports SSH.

* Windows 7+ through [Putty](http://www.putty.org/) or [Cygwin with OpenSSH](https://www.cygwin.com/).

* Mac OS X 10.11

* Ubuntu 14.04

It’s best that learners have some familiarity and comfort with the following:

* Chef Essentials or Chef Fundamentals or equivalent experience.

### Agenda

* Introduction
* Why Write Tests? Why is that Hard?
* Writing a Test First
* Refactoring Cookbooks with Tests
* Faster Feedback with Unit Testing
* Testing Resources in Recipes
* Refactoring to Attributes
* Refactoring to Multiple Platforms

### Published Content

The latest published version of these training materials are located as follows:

#### Participant Guide

The participant guide is a PDF that contains the notes export from the content slides.

This content can be found here: https://opscode.box.com/s/hl60vxbf3wn6236xnr9g19ea7xgsnhom

#### Instructor Kit

* All slides for each module

* Instructor Guide for you to learn from, practice with, and perhaps use as reference while teaching. The instructor guide contains the notes export from the content slides with additional instructor notes and lab setup instructions.

* Participant Guide

This content can be found here: https://opscode.box.com/s/njk1vp1969t3ljjdz8kupgudc5clmrju

### Known Issues

There are no known issues at this time.

### Workstation Setup

These modules focus on getting learners engaged with the content as quickly as possible. A workstation is provided to the learners.

#### Amazon Machine Instance

This workstation is currently being managed as a Amazon Machine Instance (AMI). This AMI is managed by Chef through the Training AWS Account.

* TDD Cookbook Development - CentOS 6.7 - 1.1.0 (ami-3f224d28)

> The AMI was generated with [Packer](https://github.com/chef-training/chefdk-fundamentals-image) and adheres to the following [policy](https://github.com/chef-training/chefdk-image/blob/master/cookbooks/workstations/recipes/tdd_cookbook_development.rb). It is based on a Marketplace AMI so it cannot be made public. If you would like access to this AMI to deliver training please contact [training@chef.io](mailto:training@chef.io) the request that includes your Amazon Account Id.

#### Creating the Workstation

> An chef recipe that automates the creation of the workstation can be found in the [ChefDK Image](
https://github.com/chef-training/chefdk-image/blob/master/cookbooks/workstations/recipes/tdd_cookbook_development.rb
) project

* Installation of ChefDK 0.17.17

* Create a user named 'chef' with the password 'chef'

* Ensure the yum package repository is up-to-date

```
$ yum update -y
```

* INSTALL various editors and tools that the participant will install: vim; emacs; nano; tree; and git.

* Install [Docker on CentOS](https://docs.docker.com/engine/installation/centos/)

* Allow Password Authentication

* Disable the iptables service

* Disable SELINUX

* Added an ec2 json hints file (content: `{}`) to `/etc/chef/ohai/hints/ec2.json`


## Test Driven Development Demo

### Abstract / Description

Building cookbooks with tests will increase the speed at which you work by giving you consistent feedback throughout the entire cookbook development process. The Chef Development Kit (ChefDK) includes tools that allow you perform both unit testing and integration testing.

In this webinar the facilitator will explain what is unit testing and integration testing, how they apply to the domain of cookbook development, and demonstrate building cookbooks with a test-driven approach. When we're done, you'll know when to apply these two tools, how to use these tools effectively, and know where to continue to build these skills.

### Agenda

* What is Test Driven Development?
* Writing a test first
* Refactoring with tests
* How can I make your feedback cycle faster?

### Workstation Setup

* Installation of ChefDK 0.10.10
* Working Test Kitchen Driver

Everything is created from scratch within the demonstration.

## Writing Great Unit Tests with ChefSpec Demo

### Abstract / Description

You're already building better cookbooks by incorporating tests into the development process but you want to move faster. Verifying a minor change takes minutes when you want it to take seconds. How can you achieve that fast feedback?

In this webinar the facilitator focuses on the power of unit tests. The show where they fit within a test-driven approach to cookbook development and demonstrates how they can speed up that process. Their tool of choice is ChefSpec. ChefSpec is a unit testing framework that allows you to write RSpec-style tests and its included in the Chef DK. At the end of the session, you'll know how to use ChefSpec to write great unit tests, and where you can go to improve your skills even more.

### Agenda

* Review Existing Cookbook
* Faster Feedback with Unit Tests
* Testing Resources
* Refactoring to Attributes
* A Quick Introduction to Debugging

### Workstation Setup

* Installation of ChefDK 0.10.10
* Working Test Kitchen Driver
* A cookbook named 'httpd' that has a default recipe that installs, configures, and starts the apache service with a single integration test that verifies a working web server.

> See the 'Review Existing Cookbook' section for the setup of the cookbook.
