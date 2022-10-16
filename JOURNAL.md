# Developer's Journal

## October 15, 2022 - Philip Posgate

Ok, it's been a long time since I last created a project on GitHub.  This will be another example of SpringBoot API, but this time with Docker and Kubernetes.  I am doing this with the recent experience I've gained as an engineer at SunLife, but with the standard practice that is described by the article at https://spring.io/guides/gs/spring-boot-kubernetes/.

My local workstation is Windows 11, with JDK11 and WSL and Docker Deskop installed.  Docker Desktop has Kubernetes enabled, and I can run both **docker** and **kubectl** command-line tools.  Executing the ```kubectl config current-context``` command reveals I am using my local **docker-desktop** cluster.  For command line, I switch between using Windows cmd and GitBash...but I generally prefer using GitBash for that "linuxy feel".  I'm using Visual Studio Code as my IDE.

I generated a Spring Boot project at https://start.spring.io/ with just **web** and **actuator** dependencies.  I download this to my local, do the usual ```git init``` and ```git remote add origin ...``` stuff, and push it up to https://github.com/philipposgate/springbootk8sdemo.

Then I added this **JOURNAL.md** file to the project.  I intend to make journal entries as I go.

Ok, first thing I do is make sure I can build and test the project.  So I make sure ```./gradlew clean build``` and ```./gradlew clean test``` work, and they do.  After running the build command you can see the Java jar-file at ```build/libs/springbootk8sdemo-0.0.1-SNAPSHOT.jar```.  This is self-executing jar that starts up a Tomcat instance.  So when I execute ```java -jar build/libs/springbootk8sdemo-0.0.1-SNAPSHOT.jar``` I can see SpringBoot start up in the standard output, and it opens port 8080.  With this I can hit ```http://localhost:8080/actuator``` in my browser and get a response from the API - woohoo!

