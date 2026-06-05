# CI/CD Pipeline with GitHub Actions + Docker

Automated CI/CD pipeline that builds and pushes a Docker image to Docker Hub on every push to the main branch — zero manual steps.

## What it does

Every time code is pushed to the `main` branch:
1. GitHub Actions spins up a fresh Ubuntu machine
2. Checks out the latest code
3. Builds a Docker image of the Flask app
4. Pushes the image to Docker Hub automatically

## Tech Stack

- **Python / Flask** — simple web application
- **Docker** — containerization
- **GitHub Actions** — CI/CD pipeline automation
- **Docker Hub** — container image registry

## Project Structure

```
ci-cd-pipeline/
├── .github/
│   └── workflows/
│       └── main.yml      # GitHub Actions pipeline
├── app.py                # Flask web app
├── Dockerfile            # Docker image instructions
├── requirements.txt      # Python dependencies
└── README.md
```

## Pipeline Flow

```
git push → GitHub Actions triggers → Ubuntu machine spins up
       → code checked out → Docker image built → pushed to Docker Hub
```

## How to run locally

```bash
# Clone the repo
git clone https://github.com/naseeff-7/ci-cd-pipeline
cd ci-cd-pipeline

# Build the Docker image
docker build -t ci-cd-demo .

# Run the container
docker run -p 5000:5000 ci-cd-demo
```

Open `http://localhost:5000` in your browser.

## Docker Hub

Image is publicly available at:
```
docker pull naseef20055/ci-cd-demo:latest
```

## GitHub Secrets used

| Secret | Purpose |
|--------|---------|
| `DOCKER_USERNAME` | Docker Hub username |
| `DOCKER_PASSWORD` | Docker Hub password |

Credentials are stored as GitHub Secrets — never hardcoded in the codebase.

## Key concepts demonstrated

- CI/CD pipeline automation using GitHub Actions
- Docker containerization of a Python web app
- Secure credential management with GitHub Secrets
- Automated image build and push to Docker Hub

---

Built by [Naseef](https://github.com/naseeff-7) — BCA Cloud Computing & DevOps
