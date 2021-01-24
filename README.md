This is maven java spring boot project.

I start with explaining main Plugins that are used in this project to automate maven build and CI pipelie. 

org.springframework.boot : This is spring boot plugin used to build spring project
  
maven-assembly-plugin :This plugin used to create flat jar file
   
dockerfile-maven-plugin :This is the main maven plugin to automate complete build process. or used mainly to achive CI pipeline. mvn deploy command executes the complete life cycle of maven. This build the docker image and push image to docker hub.
    
    More info on plugin is here: https://github.com/spotify/dockerfile-maven
  
  Docker repo: https://hub.docker.com/repository/docker/santhoshhirekerur/anztest
  
    Git
 
