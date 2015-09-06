## Quick setup locally

Install `redis`, e.g. via `apt-get`:
```
$ sudo apt-get install redis-server
```

Install Python requirements. A virtualenv is recommended.
```
$ pip install -r requirements.txt
```

Use settings template and adjust as needed:
```
$ cp jeeves/settings.py.template jeeves/settings.py
```

Setup the database and create a superuser:
```
$ ./manage.py migrate
$ ./manage.py createsuperusier
```

## Run Jeeves locally
Run the main Jeeves server:
```
$ ./manage.py runserver
```
In another terminal run the swampdragon server for the websocket:
```
$ ./manage.py runsd
```
In yet another terminal run a celery worker:
```
$ celery worker -A jeeves
```

## First Project
You can add your first project and set a dummy build command, for instance `./build.py`,
which just prints a few lines, sleeps a bit, prints a few more lines.

## Schedule a test build
```
$ ./manage.py schedule_build <project slug>
```
