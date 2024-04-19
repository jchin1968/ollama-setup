# About
Create docker containers to run main ollama service and the web ui

# Setup
```
docker volume create ollama      # Create external volumes so we don't accidentally delete downloaded LLMs
docker volume create ollama-web  # and user data when cleaning up docker files 
docker network create ollama     # Create an external network so other docker containers can connect to ollama service
```

# Running
```
docker compose up -d
docker exec -it ollama bash      # Use ollama from the command line
http://localhost:8080            # Use ollama from a web ui
```

