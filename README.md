# OpenShift Deployment Testing

Simple FastAPI application used to test deployment to OpenShift from a local development environment.

## Features

- FastAPI backend
- Simple HTML user interface
- Button displays:
  
  > Hello World! Welcome to my simple app

- Containerized using a Containerfile
- CI validation through GitHub Actions

## Tech Stack

- Python
- FastAPI
- Jinja2
- Podman
- OpenShift
- GitHub Actions

## Running Locally

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the application:

```bash
uvicorn app:app --reload
```

Open:

```text
http://localhost:8000
```

## Container Build

Build the container image:

```bash
podman build -t hello-world-app .
```

Run the container:

```bash
podman run -p 8080:8080 hello-world-app
```

Open:

```text
http://localhost:8080
```

## CI Pipeline

The GitHub Actions workflow performs the following checks:

- Installs Python dependencies
- Verifies the FastAPI application loads successfully
- Builds the container image

## Deployment Goal

Validate the complete deployment workflow:

```text
Local Development
        ↓
      GitHub
        ↓
 GitHub Actions
        ↓
    OpenShift
```

## Future Enhancements

- Deploy to OpenShift Dev environment
- Add automated testing
- Add deployment automation
- Introduce Dev → Test → Prod promotion workflow