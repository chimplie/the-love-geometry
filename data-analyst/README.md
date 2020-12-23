Home Assignment: Pied Piper
===========================

Before working on the assignment we suggest you to read [why do we think](../WHY-TA-DEFENCE.md) that test assignment
and it's defence is a better way for you to express your skills and craftsmanship.

Also please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

Here is the Pied Piper project consisting several steps which graded independently. The necessary exercise is
[Step 1](#step-1-lower-saxonian-blow). Everything else is optional.

By completing each step of this home assignment you proof that you have some valuable feature. So, it's ok to not to
complete all of them.

But note that poor implementation of necessary steps won't give you enough grade. Which means that working on some
optional stuff may be a wise decision.

Technical Requirements
----------------------

Pay attention to the following requirements. They are simple but necessary for your success.

1. The solution SHOULD come in a form of a code bundle (`*.tgz` or `*.zip`).
1. The name of the bundle should be `pied-piper-<your full name>-v<version number>`. The version number starts from
   `1`. We accept multiple versions of the assignment. The final grade will be calculated for the latest version of your
   assignment.
1. You SHOULD not present this solution publicly. This will cause an immediate and inexcusable failure (:
1. There should be an OBVIOUS way to run the project described in the `README.md` provided in the root of the
   bundle. All command line steps should be described as if you are talking to a person without programming skills.
1. If some parts of your solution can't be included into the package (for example, you are using Tableau for presenting
   your results) then you have to write a manual of how to make your solution works and what tools can be used for that.
1. If project has prerequisites there should be a how-to manual for installing them.
1. We want you to use modern dialects of programming languages and recent version of tools.
   For example, if you are going to use Python, do not use Python 2.7, please.
1. All UI solutions, dashboards you create should be titled with your full name and the name of the project.
   1. For example, if you have a CLI script, it should prepend the output with your full name and project name.
   1. Any standalone script's sources should start from your full name in the header.
   1. If your solution is broken down into several scripts, each should explicitly output what kind of task it is
      intended to solve.

> ### On reasonable incompleteness 
>
> As a data analyst, you are not expected to build or manage all of your tools. That mean that you may not be
> able to make your solution to work out of the box. For example, you may use Tableau or Google Data Studio.
> We are okay if you will ship us only your source code and present your dashboards during the assignment defence.
>
> However, we encourage you to include selected screenshots from your solution into your package and link them to
> `README.md`.

Welcome to Pied Piper
---------------------

Imagine you just joined Pied Piper - a company where all the decision-making is driven by data.

You have received a connection string to a Postgres database, which contains data about the company sales (there are
two tables in the data-set - `orders` and `geodata`).

Pied Piper marketing team wants you to analyse all this data and present some meaningful insights.

Step 1. Lower Saxonian Blow 
---------------------------

Create a visual dashboard (use any tool of choice) to help the team analyse the following topics (the team is interested
in global, weekly, and country-specific insights):

1. Order processing time (difference between date_created and date_completed)
1. Revenue
1. Sellers
1. Returning customers
1. Missing values

If this is the only step you intend to complete, we advise you cover all the 5 topics in your analysis.
Otherwise, if you are to proceed with optional steps 2 and/or 3, to analyse just 3 of the topics in this step 
is sufficient.

### Completion Checklist

- [ ] Basic statistical estimators like mean (or mode for categorical variables) or standard deviation are provided for
  each considered variable globally and for each week, country and week/country split.
- [ ] Your dashboard presents these statistics as well as charts of you choice (histograms, pie-chars, scatter plots,
  et c.).
- [ ] Each chart has a meaningful title and legend.
- [ ] Additional statistical estimators are documented in `README.md` (if you have any).
- [ ] All variables are classified as real, categorical, ordinal et c. and documented in `README.md`.
- [ ] You have installation and running how-to manual in the `README.md`.
- [ ] Optional, when your dashboard can't be packaged: you project package and `README.md` contains selected screenshots
  from your solution.

### On the Value of Imperfection

We do not encourage you to spend too much time on this task unless it is interesting for you. For example, if
you believe that some statistical index is not meaningful for a particular type of the data, you'd better skip it
leaving a short explanation in `README.md`.

Also, once you've calculated enough statistical and revealed your data analysis skills, if you think that more can be
done with additional effort you can't spend at the moment, we suggest you to document your ideas in `README.md`.
This will ease the assignment defence process. What is more important, it will make it much more fun and meaningful. 

Step 2. Abstract Rodent (Optional)
----------------------------------

This optional step is an opportunity to showcase your data warehousing skills.

1. Set-up your own database.
1. Import the data.
1. Create migration that introduces “transaction” entity.
   1. There are two types of transactions:		
      1. Creation of order
      1. Completion of order
1. Reflect on the necessity of further normalisation of the data structure, based on your preferences (if you have any)
1. Include the respective transformation into your migration script.
1. Create backward migration that returns your data into the original state. 

### Completion Checklist

- [ ] Scripts for data import and migrations.
- [ ] Manual in `README.md` that describes how to reproduce your results. Including installation manual for a database.
- [ ] All data transformations are documented in `README.md`.
- [ ] A brief reflection on your work in `README.md`. In particular, why have you made your normalization decisions.

Step 3. The Rest Will Follow (Optional)
---------------------------------------

This optional step is an opportunity to showcase your skills in creating, evaluating and statistically reasoning about
(relatively) simple prediction models.

We are interested in two types of predictions:

* Will the order be completed?
* What is the estimated completion time for the order?

Create two predictive models that answers on the question below. For each model:

1. Provide predictions for missing values in our dataset. 
1. Provide model's KPIs like accuracy, precision or recoil.
1. Explain your choice of prediction algorithm.
1. Explain how to interpret the model provided by your algorithm.
1. Document all your data preprocessing and feature engineering steps.

### Completion Checklist

- [ ] Predicted data for each question.
- [ ] Scripts for model training, prediction and evaluation.
- [ ] Documentation in `README.md` that describes how to train/evaluate/predict with your model.  
- [ ] Document your algorithm choice and data preprocessing decisions in `README.md`.
- [ ] Provide and interpretation for your model in `README.md`.

### Notes on Reproducibility

Since is about reproducing results. Although we are okay with any tools for statistical modeling, we embrace open source
and cross platform solution. Therefore, in the context of this assignment, Octave is better than MatLab or SPSS and
Python/R is better than Octave. If you are going to use proprietary tools, you are expected to provide a detailed
(but not necessary technical) explanation of how these tool implement corresponding algorithms.

For example, tools like SPSS sometimes provide out of the box algorithms for regression analysis. If you are going to
use such "packaged" algorithms, then you have to include links to scientific papers that describe how these things work. 

Conclusion
----------

Hope you will find this assignment interesting.

We put so much stuff here because we want you to focus on exercise you find most exciting to you.

And no matter how far you will decide to go through the assignment, we would love to hear feedback from you.

Thank you and good luck!
