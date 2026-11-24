# ACEest Fitness & Gym

A Flask fitness-management app adapted from selected features in the supplied ACEest versions 2.2.4 and 3.2.4. The original Tkinter screens were replaced with Flask routes.

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

Open [http://localhost:5000/](http://localhost:5000/) or check the health endpoint at [http://localhost:5000/health](http://localhost:5000/health).

## Run tests

Run the test suite with:

```bash
python -m pytest -q
```

The test suite contains 8 tests.

## Docker

Build the image:

```bash
docker build -t aceest-fitness:1.0 .
```

Run the container:

```bash
docker run --rm -p 5000:5000 aceest-fitness:1.0
```

The image is also available on Docker Hub as [`hemantsudan/aceest-fitness:1.0`](https://hub.docker.com/r/hemantsudan/aceest-fitness).

## Jenkins and SonarQube

The Jenkins pipeline checks out the `main` branch, installs the Python requirements, runs pytest, and submits a SonarQube analysis. The latest recorded build succeeded, with all 8 tests passing.

SonarQube reported a passed quality gate and 2 critical code smells.

## Evidence screenshots

Assignment 2 screenshots are available in the [`screenshots`](./screenshots) folder.

## Additional lab practice: Jenkins, Maven and SonarQube

In a separate lab exercise, I practiced configuring a Jenkins Maven job and integrating it with SonarQube.

- Configured Jenkins build steps for a Maven project.
- Set up the SonarQube Scanner and Quality Gates integration in Jenkins.
- Configured a SonarQube project key and ran code analysis.
- Reviewed the analysis results, code smells and quality gate status.
- Corrected a Jenkins shell command and recorded a successful build.

This lab used the `sonar-maven-demo` project and is separate from the ACEest Fitness application.
