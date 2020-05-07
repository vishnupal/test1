![Devops](https://alln-extcloud-storage.cisco.com/ciscoblogs/5d37d7284e6e8.png)


## JOB#1

### If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

## JOB#2

### If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.both dev-docker and master-docker environment are on different docker containers.

## JOB#3

### Jenkins will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2



# EXPLANATION:

## JOB 1 :

### Created a job named test_storage and test_env for this ,the developer when commits it pushes to github automatically using git post-commit hook and github webhook triggered job test_storage where the code is copied and after successful copy the next job which is chained it with gets initiated and the docker is launched with the configurations same as that of production environment and when QAT team certified it is merged using remote trigger through jenkins
[


## JOB 2:

### Created a job named prod_storage and prod_env for this ,the developer when commits it pushes to github automatically using git post-commit hook and github webhook triggered job test_storage where the code is copied and after successful copy, the next job which is chained it with gets initiated and the docker is launched with the configurations as done and is again triggered when QAT team certified the test branch code.
No alt text provided for this image
No alt text provided for this image
No alt text provided for this image

## JOB 3 :

### All the configurations are done in Jenkins with job named QAT_MERGE and it is triggered by remote trigger by the QAT team and it also initiates the JOb2 and merges the test branch with the master branch; by first building the test branch code files and then merge it to the origin/master branch and then pushed to github and 2nd job is triggered again and deployed to production environment.
No alt text provided for this image
