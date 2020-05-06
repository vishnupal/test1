![Image of Yaktocat](https://alln-extcloud-storage.cisco.com/ciscoblogs/5d37d7284e6e8.png)

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

l. Docker httpd Image
l. Jenkins
l. Github Plugin
l. Git and Hooks
l. Github and Github Webhooks
l. ngrok
