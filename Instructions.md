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

https://github.com/mindmotivate/malgus-game-app/blob/main/Dockerfile




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

## *Optional: Stop the Docker Container and clean up your shit

If you need to stop the running container, first find the container ID or name by running:

```sh
docker ps
```

Stop the container using the container ID or name:

```sh
docker stop <container_id_or_name>
```

## *Optional: Remove the Docker Container and Image

To remove the stopped container:

```sh
docker rm <container_id_or_name>
```

To remove the Docker image:

```sh
docker rmi malgus-game-app:v1
```





## *Optional: Push the Docker Image to Dockerhub:


```sh
docker push your-dockerhub-username/your-image-name:tag
```
Example Usage:
```sh
docker tag malgus-game-app:v1 motivatedmind336/malgus-game:latest

```

```sh
docker login
```

```sh
docker push motivatedmind336/malgus-game:latest
```

```sh
docker pull motivatedmind336/malgus-game
```






## Important Note on Naming Conventions

When running and playing the React-based game with Docker, make sure to customize the following elements to fit your project:

1. **Docker Image Name**:
   - Ensure the Docker image name in commands matches your project's name. For example, if the image name is `motivatedmind336/malgus-game`, replace `motivatedmind336/malgus-game` with your own Docker Hub repository name.

2. **Repository and Project Naming**:
   - Update any references to your project's repository and directory names to reflect your actual project names.

Customizing these details is crucial to align the setup with your specific project and avoid conflicts. Be sure to verify all names and paths before running Docker commands.
