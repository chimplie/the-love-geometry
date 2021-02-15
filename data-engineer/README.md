Home Assignment: Imaginarystan health API.
===========================

Before working on the assignment we suggest you read [why do we think](../WHY-TA-DEFENCE.md) this home assignment
and its defence is, in our opinion, the best way for you to prove your worth. 

Also, please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

In the middle of nowhere there is a small country called Imaginarystan. 

![Imaginarystan](https://images.pexels.com/photos/994605/pexels-photo-994605.jpeg?cs=srgb&dl=pexels-fabian-wiktor-994605.jpg&fm=jpg "Imaginarystan")
This is a picture of Imaginarystan's shore :)

A newly elected Government is planning a complete revamp of the healthcare system. Before doing so, lawmakers would like to understand the current state of things. 

Below you will find a list of exercises where you will be asked to build a data processing system. This will help the new government properly assess
Imaginarystan's helthcare system. 

[Step 1](#step-1-health-statistics) is the only mandatory exercise. Everything else is optional.

Each exercise of this home assignment will test you for specific skills. The required skills are tested in the first exercise alone, so it's ok if you
do not end up solving the remaining exercises.

Should your solution for the first exercise come off as below par, you will not be deemed fit for the vacancy. 

Technical Requirements
----------------------

Pay attention to the following. They are necessary if you want to succeed at this home assignment.

1. The solution SHOULD come in the form of a code bundle (`*.tgz` or `*.zip`).
2. The name of the bundle should be `imaginarystan-health-<your full name>-v<version number>`. The version number starts from
   `1`. You are allowed to submit multiple versions of the assignment. You will be graded only on the latest version of your
   assignment.
3. You SHOULD NOT share or post your solution anywhere. Failure to comply with this policy will result in immediate disqualification.
4. There should be an OBVIOUS way to run the project described in the `README.md` provided in the root of the
   bundle. All command line steps should be described as if you are talking to a person without any programming skills.
5. If the project has prerequisites, you should also provide a how-to manual instructing how to install them. 
6. We want you to use Python 3.6+.


Welcome to Imaginarystan
---------------------

Imaginarystan is a small country with has a single hospital that records all new hospitalizations in a single Excel file.

Here is the [link](https://docs.google.com/spreadsheets/d/1J5xRxRXT4if17rAeo70Xt-WKZ3n9nmv1) to that file.

Be careful, the file was poopulated by humans, so you will definitely stumble upon mistakes and data inconsistencies.
That is where we need you and your data engineering skills.

Step 1. Health Statistics
---------------------------

Create an app that will store all the data regarding new hospitalizations in Imaginarystan.

Your app should have an endpoint that accepts Excel files in the format provided by the link
and uploads new hospitalizations from the file.
This endpoint should be secured. Only hospital personnel can have access to it. 
The upload should work incrementally. If the Excel file is uploaded a second time, it should update the existing data and add all the new data. 


The app should have another public endpoint returning information on the new hospitalizations. 
The app response should include the following information:
1) Count of hospitalizations
2) Count of recoveries
3) Count of deaths

The endpoint should have an optional `date` parameter which, if passed, should filter hospitalized people by date,
otherwise return lifetime data.
There is no information on the date of death in the Excel file, so if the `date` parameter is passed, count of deaths should not be returned.

Please, draft the appropriate documentation regarding the data upload authorization process. Here you will also explain how to use the endpoint that returns all the new hospitalizations

### Completion Checklist

- [ ] Data storage for people
- [ ] Secured data upload endpoint
- [ ] Public statistics endpoint
- [ ] Instructions on how to use your app, provided in the `README.md`

Step 2. Another data source (optional)
---------------------------

As you might have noticed in the previous exercise, with the Excel file data structure it is not possible to show the amount of
deaths by date.

In order to do so, you will need to connect to the Imaginarystan government database. You should have already received a connection string
to the DB.

Please look for the `death` table in the database. It contains the information you need.

Extend the endpoint that returns death statistics. The endpoint should also tap into Government DB data to get the number of deaths per day.

The DB connection seems to be slow, so it might be wise to add some caching to the app. This way you will be able to save the
amount of deaths per date, instead of having to query the Government DB every time.

### Completion Checklist

- [ ] Connect to the Government DB
- [ ] Extend the API endpoint logic with daily deaths
- [ ] Cache solution for the Government DB


Step 3. Fun API instead of boring Excels parsing (optional)
---------------------------

Excels parsing can be tricky: the moment you change a column name, or a number format, your Excel parser breaks.
How about creating instead an endpoint that receives a report in a sentece format such as 
`Beyonce has been hospitalised`, `Harry Styles recovered`, or `Robin Williams died`. 
The app should parse the sentence and record the information in the DB.

The endpoint should support 3 types of reports:
1) New hospitalisation
2) Recovery
3) Death

Create this endpoint and provide a documentation on how to use it.

### Completion Checklist

- [ ] Create a parser for sentences
- [ ] Create an API endpoint that accepts sentences and records the information on the DB
- [ ] Create a documentation explaning the usage of the new endpoint

Conclusion
----------

We hope you will find this assignment interesting and, no matter how far you will decide to go with the assignment, we would love to hear your feedback!

Thank you and good luck!
