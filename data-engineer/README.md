Home Assignment: Imaginarystan health API.
===========================

Before working on the assignment we suggest you read [why do we think](../WHY-TA-DEFENCE.md) this home assignment
and defending your work is a better way for you to express your skills.

Also please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

In the middle of nowhere there is a small country called Imaginarystan. Nobody really cared about this country before a recent virus outbreak. 


![Imaginarystan](https://images.pexels.com/photos/994605/pexels-photo-994605.jpeg?cs=srgb&dl=pexels-fabian-wiktor-994605.jpg&fm=jpg "Imaginarystan")
Photo of Imaginarystan beach :)

Below you will find a list of exercises asking you to build a data processing system that will help the World Health Organization
keep track of the health situation in Imaginarystan.

The first exercise is a requirement: 
[Step 1](#step-1-health-statistics). Everything else is optional.

Each exercise of this home assignment will test you for specific skills. The required skills are tested in the first exercise alone, so it's ok if you
do not solve every exercise.

Should your solution for the first exercise come off as poor or below par, you will not be deemed fit for the vacancy. 

Technical Requirements
----------------------

Pay attention to the following requirements. They are simple but necessary for your success.

1. The solution SHOULD come in  form of a code bundle (`*.tgz` or `*.zip`).
1. The name of the bundle should be `imaginarystan-health-<your full name>-v<version number>`. The version number starts from
   `1`. We accept multiple versions of the assignment. The final grade will be related to only the latest version of your
   assignment.
1. You SHOULD not present this solution publicly. This will cause an immediate and inexcusable failure (:
1. There should be an OBVIOUS way to run the project described in the `README.md` provided in the root of the
   bundle. All command line steps should be described as if you are talking to a person without programming skills.
1. If the project has prerequisites there should be a how-to manual for installing them.
1. We want you to use Python 3.6+.


Welcome to Imaginarystan
---------------------

Imaginarystan is a small country that has a single hospital which records all new virus cases in a single Excel file.

Here is the [link](https://drive.google.com/file/d/1EGBny-NJGcr3_CT-oAsMDkwOmEPVGybU/view?usp=sharing) to that file.

Be careful, this Excel was filled by humans, so you will definitely stumble upon mistakes and data inconsistency.
That is where we need you and your data engineering skills.

Step 1. Health Statistics
---------------------------

Create an app that will store all the data regarding new virus cases in Imaginarystan.

Your app should have an endpoint that accepts Excel files in the format provided by the link
and uploads new virus cases from the file.
This endpoint should be secured, so that only hospital personal is able use it.
The upload should work incrementally, so if the Excel file is uploaded a second time, it will update the data concerning
the existing peple and add the data on new people. 


The app should have another public endpoint returning information conrerning new visus cases.
The app response should include the following information:
1. Count of confirmed cases
1. Count of recoveries
1. Count of deaths

The endpoint should have an optional `date` parameter which, if passed, should filter cases by date,
otherwise return lifetime data.
There is no information on the date of death in the Excel file, so if the `date` parameter is passed, count of deaths should not be returned.

Please, provide a documentation on how to authorize data upload and how to use the endpoint that returns data on new virus cases.

### Completion Checklist

- [ ] Data storage for people.
- [ ] Secured data upload endpoint.
- [ ] Public statistics endpoint.
- [ ] Instructions on how to use your app, provided in `README.md`.

Step 2. Another data source (optional)
---------------------------

As you noticed in the previous exercise, with the Excel file data structure it is not possible to show the amount of
deaths by date.

In order to do this you need to connect to the Imaginarystan government database. You should have received already a connection string
to the DB.

Please look into the `death` table in the database. It contains information you need.

Extend the endpoint that returns death statistics so that it will use the Government DB data in order to get the amount of deaths per day.

The DB connection seems to be slow, so it will be good to have some caching inside the app. This will save the
amount of deaths per date, so that your app will not have to query the Government DB every time.

### Completion Checklist

- [ ] Connect to the Government DB;
- [ ] Extend the API endpoint logic with daily deaths;
- [ ] Cache solution for the Government DB.


Step 3. Fun API instead of boring Excels parsing (optional)
---------------------------

Excels parsing can be tricky: the moment you change a column name, or a number format, your Excel parser is broken.
How about creating instead an endpoint that receives a report in a sentece format such as 
`John Doe has the virus`, `Donald Trump has recovered`, or `Laura Kelley died`. 
The app should parse the sentence and record the information in the DB.

The endpoint should support 3 types of reports:
1) New case
2) Recovery
3) Death

Create this endpoint and provide a documentation on how to use it.

### Completion Checklist

- [ ] Create a parser for sentences;
- [ ] Create an API endpoint that accepts sentences and records the information into DB;
- [ ] Create a documentation about usage of created endpoint.

Conclusion
----------

We hope you will find this assignment interesting.

We know, there's a lot on here. That is only because we want you to be able to chose only exercises most exciting for you.

And no matter how far you will decide to go with the assignment, we would love to hear your feedback on how your experience was.

Thank you and good luck!
