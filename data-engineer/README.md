Home Assignment: Imaginarystan COVID-19 stats API.
===========================

Before working on the assignment we suggest you to read [why do we think](../WHY-TA-DEFENCE.md) that test assignment
and its defence is a better way for you to express your skills and craftsmanship.

Also please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

In the middle of nowhere there is a small country called Imaginarystan. Nobody really took care about this country,
before COVID-19 started to recently spread across it.


![Imaginarystan](https://images.pexels.com/photos/994605/pexels-photo-994605.jpeg?cs=srgb&dl=pexels-fabian-wiktor-994605.jpg&fm=jpg "Imaginarystan")
Photo of Imaginarystan beach :)

Below are list of exercises, where you will build data processing system, that will help world community
to analyze a situation with COVID-19 in Imaginarystan.

The necessary exercise is
[Step 1](#step-1-covid-19-statistics). Everything else is optional.

By completing each step of this home assignment you proof that you have some valuable feature. So, it's ok to not to
complete all of them.

But note that poor implementation of necessary steps won't give you enough grade.

Technical Requirements
----------------------

Pay attention to the following requirements. They are simple but necessary for your success.

1. The solution SHOULD come in a form of a code bundle (`*.tgz` or `*.zip`).
1. The name of the bundle should be `imaginarystan-covid-<your full name>-v<version number>`. The version number starts from
   `1`. We accept multiple versions of the assignment. The final grade will be calculated for the latest version of your
   assignment.
1. You SHOULD not present this solution publicly. This will cause an immediate and inexcusable failure (:
1. There should be an OBVIOUS way to run the project described in the `README.md` provided in the root of the
   bundle. All command line steps should be described as if you are talking to a person without programming skills.
1. If project has prerequisites there should be a how-to manual for installing them.
1. We want you to use Python 3.6+.


Welcome to Imaginarystan
---------------------

Imaginarystan is a small country, that has single hospital, which records all COVID-19 cases in single Excel file.

Here is the [link](https://drive.google.com/file/d/1EGBny-NJGcr3_CT-oAsMDkwOmEPVGybU/view?usp=sharing) to that file.

Be careful, this Excel was filled by humans, so for sure it contains mistakes and some data inconsistency.
And that is why we need you and your data engineering skills.

Step 1. COVID-19 Statistics
---------------------------

Create an app, that will store the data about the COVID-19 in Imaginarystan.

Your app should have an endpoint, that will accept Excel file, in the format provided by the link
and upload COVID-19 cases from the file.
This endpoint should be secured, so only hospital personal could use it.
The upload should work incrementally, so if Excel file is uploaded second time, it should update info
about existing COVID-19 cases and add info about new COVID-19 cases.


An app should have another public endpoint, that will return info about COVID-19 cases.
In the response there should be data about:
1. Count of confirmed cases;
1. Count of recoveries;
1. Count of deaths.

The endpoint should have an optional `date` parameter, which if passed should filter COVID-19 cases by date,
otherwise return lifetime data.
There is no data about date of death in Excel file, so if date param is passed, count of deaths should not be returned.

Please, provide a documentation, on how to authorize in order to be able to upload COVID-19 data and
how to use endpoint that returns data about COVID-19 cases.

### Completion Checklist

- [ ] Data storage for COVID-19 Cases.
- [ ] Secured data upload endpoint.
- [ ] Public statistics endpoint.
- [ ] Instructions about how to use your app, provided in `README.md`.

Step 2. Another data source (optional)
---------------------------

As you noticed in the previous exercise, with the Excel file data structure it is not possible to show the amount of
deaths per date.

In order to do this, you need to connect to Imaginarystan government database. You should receive connection string
to the DB in advance.

Please look into `death` table in the database, it contains information you need.

Extend the endpoint, that returns death statistics, so it will use Government DB data in order to get amount of deaths per day.

DB connection seems to be slow, so it will be good to have some caching inside the app, where you could save
amount of death per date, so your app will not need to query Government DB every time.

### Completion Checklist

- [ ] Connect to Government DB;
- [ ] Extend the API endpoint logic with daily deaths;
- [ ] Cache solution for Government DB.


Step 3. Fun API instead of boring Excels parsing (optional)
---------------------------

Excels parsing can be tricky, humans can change column name, numbers format, and your Excel parser is broken.
Instead of that how about creating an endpoint, that receive a report in the format of sentence, like:
`John Doe has a COVID`, `Donald Trump has been recovered`, `Laura Kelley has been dead`. 
The app should parse the sentence and record information in the DB.

An endpoint should support 3 types of reports:
1) New COVID-19 case;
2) COVID-19 recovery;
3) Death.

Create an endpoint and provide a documentation on how to use it.

### Completion Checklist

- [ ] Create a parser for sentences;
- [ ] Create an API endpoint that accepts sentence and records information into DB;
- [ ] Create a documentation about usage of created endpoint.

Conclusion
----------

Hope you will find this assignment interesting.

We put so much stuff here because we want you to focus on exercise you find most exciting to you.

And no matter how far you will decide to go through the assignment, we would love to hear feedback from you.

Thank you and good luck!
