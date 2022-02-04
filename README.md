# Booli Targets

Template app for testing devops skills. The apps is trying to test the following.

- Building docker and basic Linux
- Making and deploying kubernetes manifest
- Resolve kubernetes issues
- Improvements of the setup


Booli target is an app where you can add and remove targets. The app has 2 parts one is a python app and the other is a MySQL database.
Today the app is in dev and is working when running docker-compose build and up.


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
Move booli targets into a productions hosting in a kubernetes cluster.


## Requirements

You will need to have the following available to work with:

- Docker and docker-compose
- Docker repo to push images
- Code editor
- Minikube


## Tasks

### 0 Pre

Start by building and starting the app to verify that we have a working app.


### 1. Better builds

The docker images us now run as root which is a bad security practice. It's also not using a base image and the images have some security issues.

- Change so the docker images run with the user `booli`
- Change so the images use a base image
- Clean the image of unused packages (This is an extra task for bonus)


### 2. Automated builds

When we push now code into the repo we want a new image to be built and then push to a docker registry.
In the folder pipeline there is a file called `deploy.sh`.
Add bash script that builds a docker image and also pushes the image to your docker registry.



### 3. Kubernetes

Prepare the booli targets to run in a kubernetes cluster. Make a working manifest and deploy to a kubernetes cluster.
In the folder `manifest` there are a template that can be used as a base.

- Also to make the app ready for production move the secrets into kubernetes secrets.

- Expose the app with a service, there is no need for an ingress controller


## Result

When the app is running you shoule be able to run:


```
minikube service booli-targets -n booli-targets
```

(If you change some name on the service or namespace then update the command)

And it should display the same content as running the app with docker-compose

When complete zip your repo and email it to your contact at Booli.

