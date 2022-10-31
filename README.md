# springbootk8sdemo

This project is **CHAPTER 1** of a **Demo Spring Boot API with Docker containerization and Kubernetes deployment**.  

* See the developer's [JOURNAL](JOURNAL.md) for this project.

## BASIC USAGE

Build the app with the following commands...

```
./gradlew clean build
./gradlew bootBuildImage
```

...then deploy it in kubernetes with:
```
kubectl apply -f kubernetes/deployment.yaml
```

...then create a "port-forward":

```
kubectl port-forward svc/springbootk8sdemo 8080:8080
```

...and THEN you can hit at: http://localhost:8080/actuator
