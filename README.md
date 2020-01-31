# django-docker-kubernetes-shortcuts
with docker terminal commands can get really long :). this is a collection of the most important shortcuts and commands 
for a django setup with docker for daily use.

## docker

* building all containers with ``docker-compose.yml``: <br>
````docker-compose build .````

* building single container (service) with ``docker-compose.yml``: <br>
````docker-compose build <servicename>````

* starting application cluster with ``docker-compose.yml``: <br>
````docker-compose up````

* starting single application with ``docker-compose.yml``: <br>
````docker-compose up <servicename>````

## django 

* running the shell: <br>
````docker-compose run --rm app sh -c "python manage.py shell"````

* running the shell with ipython (requires additional configuration): <br>
````docker-compose run --rm app sh -c "python manage.py shell_plus --ipython"````

* create superuser: <br>
````docker-compose run --rm app sh -c "python manage.py createsuperuser"````


## database

* makemigrations: <br>
```docker-compose run --rm app sh -c "python manage.py makemigrations```

* migrate: <br>
```docker-compose run --rm app sh -c "python manage.py migrate```

## pip-compile 

* creating ``requirements.txt`` from `requirements.in`: <br>
````pip-compile -o requirements.txt````

## code-styling with pre-commit

* installing (tool requires a ```.pre-commit-config.yaml```): <br>
`````pre-commit install`````

* check code locally (e.g. flake8) use ```-a``` to include all files: <br>
``pre-commit run flake8``

## deployment (gcloud)

* authenticate: <br>
```gcloud auth configure-docker```

* get available contexts: <br>
```kubectl config get-contexts```

* switch context: <br>
```kubectl config use-context CONTEXT_NAME```

* authenticate project: <br>
```gcloud container clusters get-credentials --zone [zone] --project [project]```

* get current pods: <br> 
```kubectl get pods```

* get logs of a pod: <br> 
```kubectl logs <podname>```
