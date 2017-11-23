# Jenkins
Jenkins folder containes jenkins-related material

## Requirements
- Github account
- Run Jenkins via docker
    - Via Vagrant
    ```sh
    $ vagrant up
    ```
    - Natively
    ```sh
    $ docker run \
        --rm \
        -u root \
        -p 8080:8080 \
        -v jenkins-data:/var/jenkins_home \
        -v /var/run/docker.sock:/var/run/docker.sock \
        -v "$HOME":/home \
        jenkinsci/blueocean
    ```  
- Run Jenkins [standalone](http://mirrors.seville-jam.es/jenkins/war-stable/2.73.3/jenkins.war)
   ```sh
    $ java -jar jenkins.war
    ``` 
### Considerations

- note the admin password dumped on log
- open a browser on http://localhost:8080
- run the initial setup wizard. Choose "recommended plugins"

## Creating your first Pipeline

- Create Pipeline job: Jenkins >> New Item >> pipeline-example-one >> Pipeline job >> Ok >> Pipeline script >> Try example "Hello World"

## Running a pipeline example as pipeline project

- Create Pipeline job: Jenkins >> New Item >> pipeline-example-two >> Pipeline job >> Ok >> Pipeline script >> Try example "Github+Maven"
- fix error M3 and re-run
- Setup Maven: Manage Jenkins >> Global Tool Configuration >> Add Maven >> maven(M3) >>  Install automatically >> Save

## Running a pipeline example as pipeline project with real code

- Create Pipeline job: Jenkins >> New Item >> pipeline-example-three >> Pipeline job >> Ok >> Pipeline script >> Copy and paste [Jenkinsfile provided](https://github.com/atSistemas/devops-training-material/blob/master/jenkins/Jenkinsfile)

## Running a pipeline example as CI/CD pipeline project

- Create Pipeline job: Jenkins >> New Item >> pipeline-example-ci-cd>> Pipeline job >> Ok >> Pipeline script >> Copy and paste [Jenkinsfile provided](https://github.com/atSistemas/devops-training-material/blob/master/jenkins/Jenkinsfile.complete.pipeline)

## Creating your first Multibranch Pipeline project

- [What is a Jenkins Pipeline?](https://jenkins.io/doc/pipeline/tour/hello-world/)
- Setup Github token: Create token [here](https://github.com/settings/tokens) with these scopes: repo:status and public_repo and copy the access token generated.
- Select devops-training-material

## Run previous examples using Blue Ocean UI

- [Getting Started with Blue Ocean](https://jenkins.io/doc/book/blueocean/getting-started/)

### References
- [Installing Jenkins](https://jenkins.io/doc/book/installing/)
- [Using a Jenkinsfile](https://jenkins.io/doc/book/pipeline/jenkinsfile/#using-a-jenkinsfile) 
- [Getting Started with Pipeline](https://jenkins.io/doc/book/pipeline/getting-started/#getting-started-with-pipeline) 
- [Pipeline Examples](https://jenkins.io/doc/pipeline/examples/#pipeline-examples) 
- [Blue Ocean Pipeline Editor](https://github.com/jenkinsci/blueocean-plugin/tree/master/blueocean-pipeline-editor)