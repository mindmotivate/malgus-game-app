# Running and Playing a React-based Game with Docker

This tutorial guides you through building, running, and playing a React-based game using Docker. It includes all necessary steps from ensuring Docker is properly set up to cleaning up after you're done.

## Preliminary Steps

### 1. Ensure Docker Desktop is Installed and Running

1. **Download Docker Desktop**: If you haven’t already, download Docker Desktop from [Docker’s official website](https://www.docker.com/products/docker-desktop).
2. **Install Docker Desktop**: Follow the installation instructions for your operating system.
3. **Start Docker Desktop**: Open Docker Desktop to ensure it is running. You should see the Docker icon in your system tray or menu bar.

### 2. Log in to Docker CLI

1. **Open Terminal or Command Prompt**: Open a terminal (Linux/macOS) or Command Prompt (Windows).
2. **Log in to Docker CLI**: Use the following command to log in:

   ```sh
   docker login
   ```

   You will be prompted to enter your Docker Hub username and password. This step is necessary if you plan to push images to Docker Hub or pull images from private repositories.

## 1. Prepare Dockerfile

Ensure your Dockerfile is set up for your React-based game. It should look like this:





## 2. Build the Docker Image

1. Open your terminal or command prompt.
2. Navigate to the directory containing your Dockerfile using the `cd` command.
3. Build the Docker image using the following command:

```sh
docker build -t malgus-game-app:v1 .
```

This command builds the Docker image and tags it as `malgus-game-app`.

## 3. Run the Docker Container

After building the image, you need to run a container from it. Use the following command:

```sh
docker run -p 3000:3000 malgus-game-app:v1
```

This command does the following:
- `-p 3000:3000` maps port 3000 on your local machine to port 3000 in the Docker container.
- `malgus-game-app` is the name of the Docker image you built.

The container will start, and your React app (game) will be running inside it.

## 4. Access the Game

1. Open a web browser.
2. Go to [http://localhost:3000](http://localhost:3000).

   You should see your game running in the browser. You can now start playing the game!

## 5. Optional: Stop the Docker Container and clean up your shit

If you need to stop the running container, first find the container ID or name by running:

```sh
docker ps
```

Stop the container using the container ID or name:

```sh
docker stop <container_id_or_name>
```

## 6. Optional: Remove the Docker Container and Image

To remove the stopped container:

```sh
docker rm <container_id_or_name>
```

To remove the Docker image:

```sh
docker rmi malgus-game-app:v1
```

## Summary

- **Prepare Dockerfile**: Ensure the Dockerfile is set up for your React-based game.
- **Build Image**: Use `docker build -t malgus-game-app .` to create the Docker image.
- **Run Container**: Start the container with `docker run -p 3000:3000 malgus-game-app`.
- **Access Game**: Visit [http://localhost:3000]



***. Extras: Push the Docker Image to Dockerhub?


docker push your-dockerhub-username/your-image-name:tag


***. Extras: Github Dockerhub?
