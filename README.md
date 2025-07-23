# Joomla-Docker-Init

Easily spin up a local Joomla development environment using Docker and Docker Compose. This setup enables you to test, develop, or evaluate Joomla sites quickly on your local machine.

## Prerequisites

Before you begin, ensure the following are installed and set up:

- **Docker**
  - [Get Docker](https://docs.docker.com/get-docker/) for Windows, macOS, or Linux.
  - Make sure Docker is running before attempting to start this project.
- **Windows Users:**  
  - **WSL2 (Windows Subsystem for Linux) must be enabled and installed**.  
    Docker Desktop uses WSL2 as its backend.  
    [Install/Update WSL2 – Microsoft Guide](https://learn.microsoft.com/en-us/windows/wsl/install)
  - **Docker Desktop** must be configured to use the WSL2 backend:  
    [Install Docker Desktop on Windows](https://docs.docker.com/desktop/install/windows-install/)
- **Git** (recommended) to clone the repository.

> **Note:** WSL is required only for Windows users. On macOS and Linux, Docker works natively.

## Getting Started

Follow these steps to launch your local Joomla site:

### 1. Clone the Repository

```bash
git clone https://github.com/vinay-th/Joomla-Docker-Init.git
cd Joomla-Docker-Init
```

### 2. (Optional) Adjust Configuration

- Review the `docker-compose.yml` to:
  - Change database passwords, port mappings, or Joomla version if required.

### 3. Start the Environment

```bash
docker-compose up -d
```

- This downloads and runs Joomla and the database containers in the background.

### 4. Access Your Joomla Site

- Open your browser and visit: [http://localhost:8080](http://localhost:8080)
- If you've changed the port in `docker-compose.yml`, use your custom port.

### 5. Stopping and Cleaning Up

To stop the containers:

```bash
docker-compose down
```

- This stops the environment but keeps your changes in the `data` volumes.

## Data Persistence

- Website and database files are stored in Docker volumes or local folders as defined in `docker-compose.yml`.
- Your site data will persist across container restarts, unless you explicitly remove the containers and volumes.

## Customizing Joomla

- To use your own Joomla code, place your files in the appropriate directory as specified in `docker-compose.yml` (commonly `./code` or `./www`).
- To change Joomla or database versions, edit the image versions in `docker-compose.yml`.

## Troubleshooting

- **Docker Not Running:**  
  Ensure Docker Desktop is started before running `docker-compose up`.
- **Port Conflicts:**  
  Change the port mappings in `docker-compose.yml` if `8080` or other ports are in use.
- **Permission Issues (Windows):**  
  Ensure your user has access permissions to the folders used for volumes.
- **Logs:**  
  View logs with:
  ```bash
  docker-compose logs
  ```
- **Accessing Containers:**
  ```bash
  docker exec -it  bash
  ```

## Resources

- [Joomla Documentation](https://docs.joomla.org/)
- [Official Docker Documentation](https://docs.docker.com/)
- [Install Docker Desktop on Windows](https://docs.docker.com/desktop/install/windows-install/)
- [Install WSL2](https://learn.microsoft.com/en-us/windows/wsl/install)

## License

This project is provided as-is. See the repository’s [LICENSE](LICENSE) file for terms.

**Happy developing with Joomla and Docker!**
