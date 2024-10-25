# Docker & Docker Compose - Complete Beginner-Friendly Guide 🐳

## Table of Contents
- [What is Docker?](#what-is-docker)
- [Installation Checks](#installation-checks)
- [Essential Commands](#essential-commands)
- [Container Management](#container-management)
- [Image Management](#image-management)
- [Networking](#networking)
- [Storage & Volumes](#storage--volumes)
- [Docker Compose](#docker-compose)
- [Dockerfile Guide](#dockerfile-guide)
- [Real-World Examples](#real-world-examples)
- [Monitoring & Logs](#monitoring--logs)
- [Security Best Practices](#security-best-practices)
- [Troubleshooting](#troubleshooting)

## What is Docker? 🤔
Think of Docker as a shipping container for your software. Just like shipping containers can carry different items and be moved easily between ships, trucks, and trains, Docker containers can carry your application and run it anywhere!

## Installation Checks
```bash
# Check Docker version
docker --version                # Basic version info
docker version                 # Detailed version info
docker info                   # System-wide information

# Check Docker service status
sudo systemctl status docker    # Check if Docker is running
sudo systemctl start docker    # Start Docker
sudo systemctl stop docker     # Stop Docker
sudo systemctl restart docker  # Restart Docker
```

## Essential Commands
```bash
# Help commands
docker --help                  # General help
docker COMMAND --help          # Help for specific command
docker info                    # System-wide information

# Login to Docker Hub
docker login                   # Login to push/pull images
docker logout                  # Logout from Docker Hub
```

## Container Management
Think of containers like running apps on your phone 📱

```bash
# Running Containers
docker run [OPTIONS] IMAGE [COMMAND]
docker run -d nginx                    # Run in background
docker run -it ubuntu bash             # Interactive mode
docker run -p 8080:80 nginx           # Port mapping
docker run --name my-container nginx   # Named container
docker run --rm nginx                  # Auto-remove after stop
docker run -e MY_VAR=value nginx      # Set environment variable

# Container Operations
docker ps                             # List running containers
docker ps -a                          # List all containers
docker start container_name           # Start container
docker stop container_name            # Stop container
docker restart container_name         # Restart container
docker pause container_name           # Pause container
docker unpause container_name         # Unpause container
docker rm container_name              # Remove container
docker rm -f container_name           # Force remove running container
docker rename old_name new_name       # Rename container

# Container Interaction
docker exec -it container_name bash   # Enter container
docker attach container_name          # Attach to container
docker port container_name            # Show port mappings
docker top container_name            # Show running processes
docker stats                         # Show container resource usage
docker diff container_name           # Show changed files
docker inspect container_name        # Container details
docker logs container_name          # View logs
docker logs -f container_name       # Follow logs
docker logs --tail 100 container_name # Last 100 log lines
```

## Image Management
Think of images like app installers 💿

```bash
# Image Operations
docker images                        # List images
docker pull image_name              # Pull image
docker pull image_name:tag          # Pull specific version
docker push image_name             # Push to registry
docker tag source_image target_image # Tag image
docker build -t name:tag .          # Build image
docker history image_name          # Show image history
docker inspect image_name         # Image details
docker rmi image_name            # Remove image
docker save image > image.tar    # Save image to tar
docker load < image.tar         # Load image from tar

# Image Cleaning
docker image prune               # Remove unused images
docker image prune -a           # Remove all unused images
docker builder prune           # Clean build cache
```

## Networking
Think of networks like different rooms where containers can talk to each other 🏠

```bash
# Network Operations
docker network ls                   # List networks
docker network create network_name  # Create network
docker network rm network_name      # Remove network
docker network inspect network_name # Network details
docker network prune               # Remove unused networks

# Container Networking
docker network connect network_name container_name    # Connect to network
docker network disconnect network_name container_name # Disconnect from network

# Advanced Network Creation
docker network create --driver bridge network_name   # Bridge network
docker network create --driver overlay network_name  # Overlay network
docker network create --subnet=192.168.0.0/16 network_name  # Custom subnet
```

## Storage & Volumes
Think of volumes like external hard drives for your containers 💾

```bash
# Volume Operations
docker volume ls                    # List volumes
docker volume create volume_name    # Create volume
docker volume rm volume_name        # Remove volume
docker volume inspect volume_name   # Volume details
docker volume prune                # Remove unused volumes

# Mount Options
docker run -v volume_name:/path image_name           # Named volume
docker run -v $(pwd):/path image_name               # Bind mount
docker run --mount type=bind,source=$(pwd),target=/path image_name  # Mount
```

## Docker Compose
Think of Docker Compose like a recipe book for running multiple containers 📖

```bash
# Basic Commands
docker-compose up                 # Start services
docker-compose up -d             # Start in background
docker-compose down              # Stop services
docker-compose ps                # List services
docker-compose logs              # View logs
docker-compose logs -f           # Follow logs

# Service Management
docker-compose start             # Start services
docker-compose stop              # Stop services
docker-compose restart           # Restart services
docker-compose pause            # Pause services
docker-compose unpause          # Unpause services
docker-compose rm               # Remove containers

# Build & Pull
docker-compose build            # Build services
docker-compose pull            # Pull images
docker-compose push           # Push images

# Scale Services
docker-compose up -d --scale service=3  # Scale service to 3 replicas
```

## Dockerfile Guide
Think of this like writing a recipe for your application 👩‍🍳

```dockerfile
# Common Instructions
FROM image_name             # Base image
WORKDIR /path              # Set working directory
COPY source dest           # Copy files
ADD source dest            # Copy with extra features
RUN command               # Run command
ENV key=value            # Set environment variable
EXPOSE port              # Expose port
CMD ["executable"]       # Default command
ENTRYPOINT ["executable"] # Container entry point
VOLUME /path             # Create volume mount point
USER username           # Set user
LABEL key=value         # Add metadata
ARG name=default_value  # Build argument
```

## Real-World Examples

### Web Application Stack
```yaml
version: '3'
services:
  # Frontend
  frontend:
    build: ./frontend
    ports:
      - "80:80"
    depends_on:
      - backend
    environment:
      - API_URL=http://backend:3000

  # Backend API
  backend:
    build: ./backend
    ports:
      - "3000:3000"
    depends_on:
      - database
    environment:
      - DB_HOST=database
      - DB_USER=root
      - DB_PASS=secret

  # Database
  database:
    image: mysql:8
    volumes:
      - db_data:/var/lib/mysql
    environment:
      - MYSQL_ROOT_PASSWORD=secret
      - MYSQL_DATABASE=myapp

volumes:
  db_data:
```

### Development Environment
```yaml
version: '3'
services:
  dev:
    build: 
      context: .
      dockerfile: Dockerfile.dev
    volumes:
      - .:/app
      - /app/node_modules
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=development
```

## Monitoring & Logs 📊

```bash
# Resource Usage
docker stats                    # Live resource usage
docker stats container_name    # Specific container stats
docker top container_name     # Running processes

# Logs
docker logs [OPTIONS] container_name
  --details        # Extra details
  --follow, -f     # Follow log output
  --since time    # Show logs since timestamp
  --tail number   # Number of lines to show
  --timestamps    # Show timestamps
  --until time    # Show logs before timestamp
```

## Security Best Practices 🔐

1. Use Official Images
```bash
docker pull official-image:specific-tag   # Always use specific tags
```

2. Scan Images
```bash
docker scan image_name    # Scan for vulnerabilities
```

3. Limit Resources
```bash
docker run --memory="512m" --cpus="1.0" image_name  # Limit resources
```

## Troubleshooting 🔧

```bash
# Common Debugging Commands
docker inspect container_name   # Container details
docker events                  # Real-time events
docker wait container_name     # Block until container stops

# Clean Up Commands
docker system df              # Show docker disk usage
docker system prune          # Remove unused data
docker system prune -a       # Remove all unused data
docker container prune       # Remove stopped containers
docker image prune          # Remove unused images
docker volume prune         # Remove unused volumes
docker network prune        # Remove unused networks
```

## Tips for Success 🌟

1. **Use Meaningful Names**: Name your containers and volumes clearly
```bash
docker run --name prod-web nginx    # Clear, meaningful name
```

2. **Resource Management**: Monitor and limit resources
```bash
docker stats --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}"
```

3. **Regular Maintenance**: Clean up regularly
```bash
# Weekly cleanup script
docker system prune -af --volumes
```

## Common Error Solutions 🚨

1. **Port Already In Use**
```bash
docker container ls      # Check which container is using the port
docker container stop container_name  # Stop the container
```

2. **Container Not Starting**
```bash
docker logs container_name    # Check logs for errors
docker inspect container_name # Check container configuration
```

3. **No Space Left**
```bash
docker system df        # Check space usage
docker system prune    # Clean up unused resources
```

---

💡 **Pro Tips:**
- Always use version control for your Dockerfiles and compose files
- Document your container configurations
- Use multi-stage builds for smaller images
- Implement health checks for production containers
- Regularly update base images for security patches

Remember: The best way to learn Docker is by practicing! Start with simple containers and gradually move to more complex setups. 🚀