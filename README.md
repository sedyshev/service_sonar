# Example for SonarQube with Go

Example on static analysis of Go code using SonarQube for the blog post [Go for SonarQube](https://medium.com/@remast/go-for-sonarqube-ffff5b74f33a).
This example uses Go Modules so you need to set `GO_MODULES="on"`.

## Start SonarQube

    docker run -d --name sonarqube -p 9000:9000 sonarqube


## Run SonarQube analysis

    docker run --rm --network host --mount type=volume,src="$(pwd)",dst=/opt/app,type=bind -w=/opt/app red6/docker-sonar-scanner:latest sonar-scanner -Dsonar.login=**SECRET**