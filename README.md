This is maven java spring boot project.

I start with explaining main Plugins that are used in this project to automate maven build and CI pipelie. 

**pl.project13.maven(git-commit-id-plugin)** : This plugin is help to capture all git updated infomration. every git changes its dynalically cretes "git.property" file.  On program start, dynamically created file adding to resoruse folder.

git information includes below information. In program I have used 'git.commit.id' to capture 'lastcommitsha' informaton 
 
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
    
     More info on plugin is here: https://github.com/spotify/dockerfile-maven
  
  Docker repo: https://hub.docker.com/repository/docker/santhoshhirekerur/anztest
  


![GitHub Logo](images/build_success.JPG.png)
 
