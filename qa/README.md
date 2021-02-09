But a Whimper
=============

Before working on the assignment we suggest you to read [why do we think](../WHY-TA-DEFENCE.md) that test assignment
and it's defence is better way for you to express your skills and craftsmanship.

Also please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

Here is the "Not With a Bang" project consisting several steps which graded independently. The necessary exercises are only a
steps [1](#step-1-describe), [2](#step-2-plan-your-attack) and [3a](#step-3a-case-sensitive)/[3b](#step-3b-cucumber-time).

In optional [Step 4](#step-4-api-time-optional) you can try yourself as an automated testing engineer. This
is a star-type of assignment. We do not expect you to finish it but we will love to work with a person who can see
outside of the box of his/ner competency and specialisation.

By completing each step of this home assignment you proof that you have some valuable feature. So, it's ok to not to
complete all of them.

Technical requirements
----------------------

Pay attention to the following requirements. They are simple but necessary for your success.

1. The solution SHOULD come in a form of a bundle (`*.tgz` or `*.zip`).
1. The name of the bundle should be `whimper-<your full name>-v<version number>`. The version number starts from `1`.
   We accept multiple versions of the assignment. The final grade will be calculated for the latest version of your
   assignment.
1. All textual parts of the assignment should be presented in a single PDF document.
1. The title of the document should consist the assignment name, your full name and the version of the assignment.
1. If you will complete programming assignment then there should be a `README.md` in the root of your assignment with
   the guide to start your solution.
1. All texts should be written in English.
1. You SHOULD NOT present this solution publicly. This will cause an immediate and inexcusable failure (:

Meet Todo.ly
------------

[Todo.ly](http://todo.ly) is a simple site we will use in our test assignment. It helps to organize user's tasks. Explore it before staring to work on the assignment.  

Step 1. Describe
----------------

Write a short but complete description of the Todo.ly project. Try to focus on the most important parts of the project.
Describe what the application gives to the user. Avoid marketing stereotypes and promotion. More facts, less sentiments.   


Step 2. Plan your Attack
------------------------

Here we would like you to write a [test plan](https://en.wikipedia.org/wiki/Test_plan) for the Todo.ly project. You may use
[one of these](https://strongqa.com/qa-portal/testing-docs-templates/test-plan) as a template (or come up with your own, it's up to you). Try to fill as many parts as possible. For those paragraphs you will decide not to fill give a clear explanation why it is not relevant.

Step 3a. Case Sensitive
-----------------------

Please write test scenarios for main functionality of Todo.ly application. Use the format that you think is best (test cases, checklists, etc.). Don't aim for a full coverage, let's instead focus on priorities.

If you want to use [Cucumber](https://docs.cucumber.io/cucumber/) you can skip this task and
proceed to [Step 3b](#step-3b-cucumber-time).

Step 3b. Cucumber Time
----------------------

Write test scenarios for main functionality of Todo.ly application using [Cucumber](https://docs.cucumber.io/cucumber/).
Organise your scenarios in feature suits each in a separate file. Don't aim for a full coverage, let's instead focus on priorities. Add a short contents for Cucumber feature files in your PDF file or `README.md`. Prioritize your tests in that list.

If you'd rather use a different format, feel free to tackle [Step 3a](#step-3a-case-sensitive) instead. 

Step 4. API Time (optional)
----------------

Please use your favorite tool to to cover Todo.ly [Public API](http://todo.ly/ApiWiki/) with functional tests. Of course, you are not expected to cover all, just choose whatever you think is most important (given the limited amount of time and resources that can be spent on this).

You are free to use whatever tool you feel comfortable with (although we recommend to use Python as a main technology). Ensure that `README.md` contains all installation and run instructions for your tests.
