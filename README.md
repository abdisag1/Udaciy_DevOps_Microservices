[![<abdisag1>](https://circleci.com/gh/abdisag1/Udaciy_DevOps_Microservices.svg?style=svg)](https://circleci.com/gh/abdisag1/Udaciy_DevOps_Microservices)
## Project Overview

This project showcases the skills acquired in the Udacity Cloud DevOps Nanodegree program to operationalize a Machine Learning Microservice API.

The project uses a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. More information about the data, which was initially taken from Kaggle, can be found on [the data source site](https://www.kaggle.com/c/boston-housing). This project could be also extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

The project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. It covers the following topics:

* Test the project code using linting
* Complete a Dockerfile to containerize this application
* Deploy a containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that the code has been tested

More details on the project rubric can be found [here](https://review.udacity.com/#!/rubrics/2576/view).

---

## File Navigator

* `app.py`: a Python flask app that serves out predictions (inference) about housing prices through API calls.
* `Dockerfile`: a set of instructions for docker to automatically build an image.
* `make_prediction.sh`: a script file that sends input data to a trained machine learning model and gets the predicted value for the house price.
* `Makefile`: a handy way to run commands in the environment
* `requirements.txt`: list of all dependencies that are required to run the project.
* `run_docker.sh`: a script file to build an image from Dockerfile and run a docker container.
* `run_kubernetes:sh`: a script file to run a Kubernetes pod that has a container running inside, the container will run the python application
* `upload_docker.sh`: a script file to tag a local docker image and push it to docker hub.

---

## Setup the Environment

* Create a virtual environment with `make setup`
* Activate a vertual environment with `source ~/.devops/bin/activate`
* Install the necessary dependencies with `make install`

### Running `app.py`

* Standalone:  `python app.py`
* Run in Docker:  `./run_docker.sh`
* Run in Kubernetes:  `./run_kubernetes.sh`
###  Run a Container & Make a Prediction

-   Build the docker image from the Dockerfile; it is recommended that you use an optional --tag parameter as described in the build documentation.
-   List the created docker images (for logging purposes).
-   Run the containerized Flask app; publish the container’s port (`80`) to a host port (`8000`).

Run the container using the `run_docker.sh` script created before following the steps above:

```sh
$ . ./run_docker.sh # Check the `Workarounds` section if you want to get more information about this.
```

After running the container (docker app) we can able to run the prediction using the `make_prediction.sh` script:

```sh
$ . ./make_prediction.sh # Don't forget run the container before
```

### Make Prediction

* Having the application running in container, in a separate terminal run `./make_prediction.sh`
    
### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
### Configure Kubernetes to Run Locally

-   [Install Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux)
-   [Install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

> **Note:** Check the `Workarounds` section for common issues.


