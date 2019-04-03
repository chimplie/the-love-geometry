Home Assignment: Not With a Bang
=============

Before working on the assignment we suggest you to read [why do we think](../WHY-TA-DEFENCE.md) that test assignment
and it's defence is better way for you to express your skills and craftsmanship.

Also please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

Here is the "Not With a Bang" project consisting of several steps, each graded independently. All exercises are necessary, 
especially [Step 4](#step-4-a-clockwork-cucumber), as QA automation will be one of the key aspect of this role.

By completing each step of this home assignment you show-case some valuable expertise. Hence, you may pay attention
to some steps more than others. Consider that steps from 1. to 3. prepare you for the better solution of the final 
[Step 4](#step-4-a-clockwork-cucumber), which is the summit of this home assignment.

Technical requirements
----------------------

Pay attention to the following requirements. They are simple but necessary for your success.

1. The solution should come in the form of a bundle (`*.tgz` or `*.zip`).
1. The name of the bundle should be `whimper-<your full name>-v<version number>`. The version number starts from `1`.
   We accept multiple versions of the assignment. The final grade will be calculated for the latest version of your
   assignment.
1. All textual parts of the assignment should be presented in a single PDF document.
1. The title of the document should consist the assignment name, your full name and the version of the assignment.
1. For completing the programming assignment you should provide a `README.md` in the root of your assignment with the
   guide to start your solution.
1. All texts should be written in English.
1. You SHOULD NOT present this solution publicly. This will cause an immediate and inexcusable failure (:

Meet Noisli
-----------

[Noisli](https://www.noisli.com/) is a nice and simple site we will use in our test assignment. It helps to organize
user's sound environment. Explore it before staring to work on the assignment. 

Step 1. Describe
----------------

Write a short but complete description of the Noisli project. Try to focus on the most important parts of the project.
Describe what the application gives to the user. Avoid marketing stereotypes and promotion. More facts, less sentiments.   


Step 2. Plan your Attack
------------------------

Here we want you to write a [test plan](https://en.wikipedia.org/wiki/Test_plan) for the Noisli project. You may use
[this one](https://www.softwaretestinghelp.com/test-plan-sample-softwaretesting-and-quality-assurance-templates/) as a
template. Try to fill as much parts as possible. For those paragraphs you will decide not to fill give a clear
explanation why it is not relevant.

Step 3. Cucumber Time
---------------------

Write test scenarios for main functionality of Noisly application using [Cucumber](https://docs.cucumber.io/cucumber/).
Organise your scenarios in feature suits each in a separate file.

Add a short contents for Cucumber feature files in your PDF file or `README.md`. Prioritize your tests in that list.

Step 4. A Clockwork Cucumber
----------------------------

Use your favorite tool to convert Cucumber into automated tests. You can use anything you think is appropriate here. It
is possible to automate only the most important subset of your Cucumber scenarios to pass this task.

Obvious suggestions:
* [Cucumber.js](https://github.com/cucumber/cucumber-js) — Javascript
* [Letuce](http://lettuce.it/) — Python
* [Cucumber for Rails](https://github.com/cucumber/cucumber-rails) — Ruby on Rails (still implies overhead in a form of
  Rails app) 

Ensure that `README.md` contains all installation and run instructions for your tests.
