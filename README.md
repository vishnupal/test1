![Image of Devops](https://alln-extcloud-storage.cisco.com/ciscoblogs/5d37d7284e6e8.png)

# Setup three three teams/environemnts
### 1.Poduction
### 2.Testing
### 3.Quality Assurance

 ## PROBLEM STATEMENT :

## JOB#1

### If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

## JOB#2

### If Developer push to master branch then Jenkins will fetch from master and deploy on master-docker environment.both dev-docker and master-docker environment are on different docker containers.

## JOB#3

### jenkins will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2
# Requirements

1. Docker httpd Image
1. Jenkins
1. Github Plugin
1. Git and Hooks
1. Github and Github Webhooks
1. ngrok
## EXPLANATION:

#### JOB 1 :

#### Created a job named job1 and test_env for this ,the developer when commits it pushes to github automatically using git post-commit hook and github webhook triggered job job1 where the code is copied and after successful copy the next job which is chained it with gets initiated and the docker is launched with the configurations same as that of production environment and when QAT team certified it is merged using remote trigger through jenkins

## Add repo in the jenkins . This is luanch a Test env when the Developer commit . And deploy test file on the test_env
![Image of Test_env](Ss/job1.jpg)

## It trigger only when github-webhook 
![Test_env](Ss/jobI1.jpg)

## Below scriptis run when jenkins trigger
![Script_job1](Ss/jobZ1.jpg)

#### JOB 2:

#### Created a job named job2 and prod_env for this ,the developer when commits it pushes to github automatically using git post-commit hook and github webhook triggered job job2 where the code is copied and after successful copy, the next job which is chained it with gets initiated and the docker is launched with the configurations as done and is again triggered when QAT team certified the test branch code.

## Add repo in the jenkins . This is luanch a Production env when the Developer commit . And deploy Master file on the test_env
![Image of Test_env](Ss/job2.jpg)

## It trigger only when github-webhook 
![Test_env](Ss/jobI2.jpg)

## Below scriptis run when jenkins trigger
![Script_job1](Ss/jobZ2.jpg)

#### JOB 3:
### All the configurations are done in Jenkins with job named Job3 and it is triggered by remote trigger by the QAT team and it also initiates the JOb2 and merges the test branch with the master branch; by first building the test branch code files and then merge it to the origin/master branch and then pushed to github and 2nd job is triggered again and deployed to production environment.

## Add repo in the jenkins . This is luanch a Production env when the Developer commit . And deploy Master file on the test_env
![Image of Test_env](Ss/jobZ1.jpg)

## It trigger only when github-webhook 
![Test_env](Ss/jobI1.jpg)

## Below scriptis run when jenkins trigger
![Script_job1](Ss/job1.jpg)

