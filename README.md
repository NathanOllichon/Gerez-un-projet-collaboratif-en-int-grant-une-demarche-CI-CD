# BobApp

Clone project:

> git clone https://github.com/NathanOllichon/Gerez-un-projet-collaboratif-en-int-grant-une-demarche-CI-CD.git

## Configuration Sonar analyse

We have two type of Sonar analyse, on PR and on Main.
For Pull Request Sonar analyse only the new modifications.
For Push on main we analyse the wole code and new modifications, he have two tab on SonarCloud.


The SonarCLoud projects are configured on a workflow Github Actions and on your github Secrets.

Go at sonar cloud "https://sonarcloud.io/" and create an account and a project.
Go on ".github/workflows/CI-CD-Pipe-Main.yml" and modify two args for the run command on "Maven build and Sonar analyze back-end" task, for you're own space/account.
-Dsonar.projectName=""
-Dsonar.projectKey=

Same on think on ".github/workflows/CI-CD-Pipe-PR.yml".

You can find this informations on "information" in your project on SonarCloud
Don't forget to update your Quality gate used on information, for your own quality gate.


For add secrets, go in your github, settings, Secrets and variables, Action.
Modify the value of SONAR_TOKEN for your token, generate on SonarCLoud, my account, security.


Then for exclude files of analyses or for include tests files for coverage, you can find another configuration in ./front/sonar-project.properties 

On github Actions choose the workflow, download and open the open artifacts with a browser.

### Configuration Docker

Go at sonar cloud "https://hub.docker.com/" and create a repository.

The dockerHub repository is configured on a workflow Github Actions and on your github Secrets.
Go on ".github/workflows/CI-CD-Pipe-Main.yml" and modify the two task "Build and push" and after the secret on "tags:" choice the tags names you want for docker images front and back. 

For add secrets, go in your github, settings, Secrets and variables, Action.
Modify the value of DOCKERHUB_USERNAME, add your username on DockerHub.
Modify the value of DOCKERHUB_TOKEN, generate on DockerHub, in my account, security.

## Front-end 

Go inside folder the front folder:

> cd front

Install dependencies:

> npm install

Launch Front-end:

> npm run start;

## Back-end

Go inside folder the back folder:

> cd back

Install dependencies:

> mvn clean install

Launch Back-end:

>  mvn spring-boot:run

## Docker Launch

OPEN Docker desktop and search for your images (Back and Front)
Then run it.
