# ACEest Fitness & Gym

A Flask fitness-management app adapted from selected features in the supplied
ACEest versions 2.2.4 and 3.2.4. The original Tkinter screens were replaced
with Flask routes.

## Features

- Client profiles and calorie estimates
- Weekly adherence tracking
- Workouts and exercises
- Body metrics and BMI
- Membership details
- Fitness program generation

## Local setup

Create and activate a virtual environment, then install the dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Start the application:

```bash
python app.py
```

Open <http://localhost:5000/> or check <http://localhost:5000/health>.

## Run tests

```bash
python -m pytest -q
```

The current test suite has 8 tests.

## Docker

Build and run the app:

```bash
docker build -t aceest-fitness:1.0 .
docker run --rm -p 5000:5000 aceest-fitness:1.0
```

The image was also pushed to Docker Hub as `hemantsudan/aceest-fitness:1.0`.

## Jenkins

The Jenkins pipeline checks out the `main` branch, installs the Python
requirements, runs pytest, and submits a SonarQube analysis. The latest
recorded build succeeded, with all 8 tests passing. SonarQube reported a
passed quality gate and 2 critical code smells.

## Kubernetes

Kubernetes deployment and the deployment strategy demonstrations have not
been completed yet.
