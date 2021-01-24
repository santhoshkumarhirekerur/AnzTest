Deployment steps with docker. Use commands marked in below image.


 **Docke pull image to local**
  ```
  docker pull santhoshhirekerur/anztest:0.0.56-SNAPSHOT
  ```
 
  **run docker**
  ```
  docker run -d -p 8080:8080 docker.io/santhoshhirekerur/anztest:0.0.56-SNAPSHOT
  ```
 
  **check result**
  ```
  curl http://localhost:8080/version
  ```

 

![GitHub Logo](/images/docker_exe.JPG)

Executing this project with kubernaties. use **anztest-kubernetes.yml** for deployment. Use commands marked in below image.

 
  **Deploy to K8s to namespace technical-test**
 ```
 kubectl apply -f anztest-kubernetes.yml
 ```
 
  **check pod and services in namespace technical-test**
 
```
kubectl get all --namespace=technical-test
```

 **check result**
 ```
 curl http://localhost:8080/version
 ```
 
![GitHub Logo](/images/k8s_exe.JPG)


PRODJECT DETAILS
------------
This is maven java spring boot project.

I starts with explaining main plugins that are used in this project to automate maven build and CI pipelie. 

**pl.project13.maven(git-commit-id-plugin)** : This plugin is help to capture all git updated infomration. when program starts it dynamically creates git properties file in target/src/main/resources folder. 

Git file includes below information. In program we caputre git inforion 'git.commit.id' ('lastcommitsha')  from this property file. 
 
   ```
 git.tags=${git.tags}
 git.branch=${git.branch}
 git.dirty=${git.dirty}
git.remote.origin.url=${git.remote.origin.url}
git.commit.id=${git.commit.id}
git.commit.id.abbrev=${git.commit.id.abbrev}
git.commit.id.describe=${git.commit.id.describe}
git.commit.id.describe-short=${git.commit.id.describe-short}
git.commit.user.name=${git.commit.user.name}
git.commit.user.email=${git.commit.user.email}
git.commit.message.full=${git.commit.message.full}
git.commit.message.short=${git.commit.message.short}
git.commit.time=${git.commit.time}
git.closest.tag.name=${git.closest.tag.name}
git.closest.tag.commit.count=${git.closest.tag.commit.count}
git.build.user.name=${git.build.user.name}
git.build.user.email=${git.build.user.email}
git.build.time=${git.build.time}
git.build.host=${git.build.host}
git.build.version=${git.build.version}

```
**org.springframework.boot** : This is spring boot plugin used to build spring project
  
**maven-assembly-plugin** :This plugin used to create flat jar file
   
**dockerfile-maven-plugin** :This is the main maven plugin to automate complete build process. or used mainly to achive CI pipeline. mvn deploy command executes the complete life cycle of maven. This build the docker image and push image to docker hub.
    
*[More info on plugin is here:] https://github.com/spotify/dockerfile-maven

*[Docker repo:]    https://hub.docker.com/repository/docker/santhoshhirekerur/anztest
  

1. If we do any changes in file of develop branch and push changes to it, **git action** triggers the workflow and execute below steps. After sucessfull workflow execution  we will see the updated image in the docker hub.

![GitHub Logo](/images/build_success_dev.JPG)
 
