# BobApp

Clone project:

> git clone XXXXX

## Front-end 

Go inside folder the front folder:

> cd front

Install dependencies:

> npm install

Launch Front-end:

> npm run start;

### Configuration Sonar analyse

We have two type of Sonar analyse, on PR and on Main.
For Pull Request Sonar analyse only the new modifications.
For Push on main we analyse the wole code and new modifications, he have two tab on SonarCloud.


The SonarCLoud projects are configured on a workflow Github Actions and on your github Secrets.

Go at sonar cloud "https://sonarcloud.io/" and create an account and a project.
Go on ".github/workflows/CI-CD-Pipe-Main.yml" and modify two args for the run command on "Maven build and Sonar analyze back-end" task, for you're own space/account.
-Dsonar.projectName=""
-Dsonar.projectKey=

You can find this informations on "information" in your project on SonarCloud
Don't forget to update your Quality gate used on information, for your own quality gate.


For add secrets, go in your github, settings, Secrets and variables, Action.
Modify the value of SONAR_TOKEN for your token, generate on SonarCLoud, my account, security.


Then for exclude files of analyses or for include tests files for coverage, you can find another configuration in ./front/sonar-project.properties 

### Docker Front-end

The dockerHub repository is configured on a workflow Github Actions and on your github Secrets.
Go on ".github/workflows/CI-CD-Pipe-Main.yml" and modify "" for you're own space/account

OPEN Docker desktop and search for your images 
Then run it.

## Back-end

Go inside folder the back folder:

> cd back

Install dependencies:

> mvn clean install

Launch Back-end:

>  mvn spring-boot:run

Tests automaticaly played:

On github Actions choose test workflow, download and open the artifacts with a browser.


### Docker Back-end

The container are configured on a workflow Github Actions.
Go on it and modify "" for you're own space/account

OPEN Docker desktop and search for your images 
Then run it.

## Configuration

SonarCloud 2 spaces creation et config + keys + sonar quality gate 
modification on github secrets + change names of project cloud in workflow

Same for DockerHub, for push in your spaces, create name and change project name. 
