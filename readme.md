# Malgus Tetris

**Malgus Tetris** is a React-based Tetris game project. This repository contains two main components:

## 1. Dockerized Application

**Standalone Docker Container**: This component allows you to run the game as a self-contained Docker container. The Docker setup ensures that the game can be easily deployed and tested in any environment.

## 2. Public GitHub Pages Site

**Publicly Available Website**: The game is also hosted as a public website through GitHub Pages. This provides a live, accessible version of Malgus Tetris that can be viewed and played directly from a web browser.

For detailed setup instructions and usage, please refer to the accompanying documentation files.

![Malgus Tetris](src/images/malgustetris.jpg)

## Important

When setting up your cloned repository, please make the following updates:

1. **Update Project Name**:
   - Change `"name": "malgus-game-app"` in `package.json` to your own project name.

2. **Update Homepage URL**:
   - Modify `"homepage": "http://mindmotivate.github.io/malgus-game-app"` in `package.json` to reflect your project's GitHub Pages URL (e.g., `"http://<your-username>.github.io/<your-repo-name>"`).

3. **Create GitHub Secret Token**:
   - Go to your repository's settings on GitHub.
   - Navigate to "Secrets and variables" > "Actions."
   - Click "New repository secret" and create a secret named `ACTIONS_DEPLOY_ACCESS_TOKEN` with your GitHub token as the value.

These steps are essential for ensuring your project is correctly configured and securely deployed.
