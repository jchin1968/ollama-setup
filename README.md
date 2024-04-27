# About
Create docker containers to run main ollama service and the web ui

# Setup
```
docker volume create ollama      # Create external volumes so we don't accidentally delete downloaded LLMs
docker volume create ollama-web  # and user data when cleaning up docker files 
docker network create ollama     # Create an external network so other docker containers can connect to ollama service
```

Create an .env file and set the default docker-compose file
```
COMPOSE_FILE=docker-compose-ai-lab.yml  # AI Lab - GPU enabled, auto restart 
COMPOSE_FILE=docker-compose-rpi.yml     # Raspberry PI - no GPU, no restart 
```

# Running
```
docker compose up -d             # Start container using default docker-compose.yml file or as defined in .env
docker compose -f ai-lab up -d   # Start for AI Lab 
docker compose -f rpi up -d      # Start for Raspberry PI
docker exec -it ollama bash      # Use ollama from the command line
http://localhost:8080            # Use ollama from a web ui
```

