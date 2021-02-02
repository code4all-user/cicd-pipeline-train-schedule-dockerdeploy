# cicd-pipeline-train-schedule-dockerdeploy

This is a simple train schedule app written using nodejs. It is intended to be used as a sample application for a series of hands-on learning activities.

## Prerequisite in jenkins  

- sshpass commandline tool   
        #apt install sshpass  
- Docker Pipeline Plugin in Jenkins  

- Add docker credential  
        Kind: Username with password  
        Username: <docker hub username>  
        Password: <password>  
        ID: docker_hub_login  
        Description: Docker Hub Login  
- Add Github credential  
        Generate Token in your Github.   
        Profile > Settings > Developer Settings > Personal Access Tokens > Generate New Token.  
        Token Description: Jenkins  
        Permissions: admin-repo_hook  
        Create credential in jenkins:  
        Kind: Username with password  
        Scope: Global  
        Username: <your github user_id>  
        Password: <Access Token>  
        ID: github_key  
        Description: Github Key  
    
- Add Web Server credentila (where jenkins will deploy docker image) // This user should have permission to deploy docker image on production server.  
        Kind: Username with password  
        Scope: Global  
        Username: <user_name>  
        Password: <password>  
        ID: webserver_login  
        Description: Webserver Login  
- Set Web Server IP   
        Manage Jenkins > Configure System  
        Name: prod_ip  
        Value: <Web Server IP Address>  

### Running the app

You need a Java JDK 7 or later to run the build. You can run the build like this:

    ./gradlew build

You can run the app with:

    ./gradlew npm_start

Once it is running, you can access it in a browser at http://localhost:8080
