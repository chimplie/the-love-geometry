Home Assignment: Project Frankenstein
=====================================

Before working on the assignment we suggest you to read [why do we think](../WHY-TA-DEFENCE.md) that test assignment
and it's defence is better way for you to express your skills and craftsmanship.

Also please take a look at the document [describing the whole process](../PROCESS.md) to understand how the defence is
held and what to expect from it.

Intro
-----

We prepared for you a simple application called [Chimplie Debug App](https://github.com/chimplie/debug-app/tree/0.0.2).
We want you to create an infrastructure for this application in AWS and deploy the application to the cloud. There are
several steps in this assignment which allow you to gradually express your mastership.

Note that [Step 1](#step-1-homunculus-optional) is optional and should be implemented only if you have poor skills with
Terraform.

By completing each step of this home assignment you proof that you have some valuable feature. So, it's ok to not to
complete all of them.

But note that poor implementation of necessary steps won't give you enough grade. Which means that working on some
optional stuff may be a wise decision. 

You also may jump over some exercises but since later stages depends on their predecessors you should do it in a smart
way. What does it mean? That you should somehow mock the incomplete functionality: either by some infrastructure stubs
or by the bold design solution. Feel free to embrace your imagination.

> ### Note
>
> We suggest you to use AWS free tier and spot instances whenever it's possible. Wee can perfectly tolerate poor
> performance or reasonable downtime. Instead, we really don't want to put you into a situation where you required to
> spend your money to run the application in the cloud. 

Technical Requirements
----------------------

Pay attention to the following requirements. They are simple but necessary for your success.

1. The solution SHOULD come in a form of a code bundle (`*.tgz` or `*.zip`).
1. The name of the bundle should be `project-frankenstein-<your full name>-v<version number>`. The version number starts from
   `1`. We accept multiple versions of the assignment. The final grade will be calculated for the latest version of your
   assignment.
1. You SHOULD not present this solution publicly. This will cause an immediate and inexcusable failure (:
1. There should be an OBVIOUS way to run the project described in the `README.md` provided in the root of the
   bundle. All command line steps should be described as if you are talking to a person without programming skills.
1. If project has prerequisites there should be a how-to manual for installing them.
1. The infrastructure should be as secure as possible check [security requirements](#security-requirements) for details.

Get Ready for Debug
-------------------

Everything you need to run and build debug application is described in its [documentation](https://github.com/chimplie/debug-app/blob/0.0.2/README.md).

Note that you have to use version [`0.0.2`](https://github.com/chimplie/debug-app/releases/tag/0.0.2). Do not use master
or other versions of the application since they may be not properly tested or may have different behaviour.

Security Requirements
---------------------

1. All resources should be under the project VPC.
1. No unnecessary egress traffic should be allowed.
1. No unnecessary ports should be allowed.
1. Never expose RDS or Redis to the public.

Step 1. Homunculus (Optional)
-----------------------------

This step is optional and should be implemented if you have poor skills with Terraform or never adopted
[infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_code) approach. 

Deploy the Debug Application to AWS ECS cluster and setup RDS Postgres cluster and Redis to test connection between
application and data sources. You can do all these steps manually but you have to create a diagram of your
infrastructure.

### Requirements for Homunculus

1. All possible resources should be deployed under VPC.
1. There should be no access to any unnecessary open ports on EC2 instances.
1. Keep egress rules as tight as possible.
1. Create a Postgres database using RDS under your VPC.
1. Create a Redis instance using AWS ElasticCache under your VPC.
1. Create a ECS cluster and deploy application to it.
1. There should be two instances of the application in the cluster, call it `main` and `worker`.
1. There should be a proxy route defined in `main` application to `worker` from `/worker/status` to `/status`. Check
   Debug App [documentation](https://github.com/chimplie/debug-app/blob/0.0.2/README.md) for details.
1. Worker should check Postgres database and Redis statuses.
1. The master service should be scaled to two tasks and be accessible via (application) load balancer.
1. Assign elastic IP to the load balancer.
1. All logs from each service should go to Cloud Watch.

### Presenting Homunculus

Since this step implies that you manually create infrastructure we want you create a comprehensive diagram of your
infrastructure, describe all its entities, connections between them and security rules.

Step 2. Golem
-------------

This step shows that you master infrastructure as code approach. We want you to describe
[Debug App](https://github.com/chimplie/debug-app/blob/0.0.2/README.md) as a [Terraform](https://www.terraform.io/)
declaration and deploy it to AWS.

### Requirements for Golem

Please note that to pass this step you should complete about 70-80% of these requirements. Chose your restrictions
wisely. If you think that some requirements are too boring to implement and they do not contribute to your professional
appearance you can drop them. But in this case you should explain why these restrictions were neglected.  

1. All resources except Terraform backend should be deployed via Terraform.
1. All possible resources should be deployed under VPC.
1. There should be no access to any unnecessary open ports on EC2 instances.
1. Keep egress rules as tight as possible.
1. We need RDS Postgres and Redis ElasticCache in the same VPC as application.
1. Both DB and Redis should not be accessible from outside. 
1. There should be two instances of the application in the cluster, call it `main` and `worker`.
1. It is up to you whether put everything into one multi-container service or use different services.  
1. There should be a proxy route defined in `main` application to `worker` from `/worker/status` to `/status`. Check
   Debug App [documentation](https://github.com/chimplie/debug-app/blob/0.0.2/README.md) for details.
1. Worker should check Postgres database and Redis statuses.
1. The `main` service should be scaled to two tasks and be accessible via (application) load balancer.
1. Assign elastic IP to the load balancer or attach to Route 53.
1. All logs from each service should go to Cloud Watch.

### Presenting Golem

You have to submit your documented solution as [described](#technical-requirements) above. During the presentation you
will be asked to deploy your Terraform plan to the fresh infrastructure without errors and then destroy it.

Step 3. Frankenstein
--------------------

This is a final step that extends [Step 2.](#step-2-golem) and should express your craftsmanship and architectural
skills. 

### Requirements for Frankenstein

1. Take all the [requirements](#requirements-for-golem) from the [Golem](#step-2-golem).
1. Decompose your Terraform project into `infrastructure` and `application` levels: that means that `infrastructure`
should define necessary resources like VPC or RDS and `application` should take care about things like ECS tasks
definitions and services.
1. Each layer should be a separate Terraform project with separated state backend.
1. We assume that `application` layer can be run only when `infrastructure` level is deployed.
1. It is up to you how to connect these two apps. We prefer to load data from remote backends. But you can store some
data in parameter store as well. 
1. Try to put as much things as possible into Terraform modules.

#### For real experts

1. Make sure that database is restored from the latest snapshot when infrastructure is created except the first run
(this should bw skipped). This behaviour is not fully supported by Terraform, so you need to improvise. Therefore this
requirement is considered as optional for intermediate Terraform practitioners (but not for those who consider
themselves masters of this tool).
1. The debug app can run custom shell commands (check the [docs](https://github.com/chimplie/debug-app/blob/0.0.2/README.md)).
Try to find a way to imitate high CPU and RAM consumption and setup ECS tasks auto-scaling for master based on the
metric you think is most appropriate.
1. Add EC2 instances auto-scaling in addition to tasks count scaling.

### Presenting Frankenstein

The technical part is similar to the [Golem presentation](#presenting-golem).
   