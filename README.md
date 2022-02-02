# Booli Targets
Template app for testing devops skills. The apps is trying to test the following.

- Building docker and basic Linux
- Making and deploying kubernetes manifest
- Resolve kubernetes issues
- Improvments of the setup


Booli target are an app where you can add and remove targets. The app has 2 parts one is a python app and then other is a mysql database.
Today the app is in dev and are working when running docker-compose build and up.


```
docker-compose build
```


```
docker-compose up
```


![firstpage!](/assets/1.png)

![3!](/assets/2.png)

![1!](/assets/3.png)


## The task
Move boolis targets into a productions hosting in a kubernetest cluster.



## Req

- Docker and docker-compose
- Docker repo to push images
- Code editor
- Minikube 

## Tasks


### 0 Pre
Start by building and starting the app to verify we have a working app.


### 1. Better builds
The docker images us now run as root with is a bad security practis. Its also is not using a base image and the images has some security issues.

- Change so the docker run with the user booli
- Setup so the image are using a base image
- Clean the image of unused packages ("This is extra task")

### 2. Automated builds
When we push now code into the repo we want a new image to be build and then push to a docker registry.
In the folder pipeline there is a file called deploy.sh.
Add bash script that build a docker image and also push the image to your docker registry.



### 3. Kubernetes
Prepar the booli targets to run in a kubernetes cluster. Make a working manifest and deploy to a kubernetes cluster. 
In the folder manifest there are a template that can be used as a base.


- Also to make the app ready for production move the secrets into a kubernetes secrets.

- Expose the app with a service there is no need for a ingress controller




## Result

When the app is running you shoule be able to run 


```
minikube service booli-targets -n booli-targets
```
(If you change some name on service ore namespace then update the command)

And it should display the same content as running the app with docker-compose

When complete zip your repo and email to contact.
