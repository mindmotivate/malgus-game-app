## 1. Create a GitHub Repository

### Sign In to GitHub

- Log in to your GitHub account. If you don’t have one, you’ll need to create it.

### Create a New Repository

1. Go to GitHub and click the “+” icon in the upper-right corner, then select “New repository.”
2. **Repository Name**: Enter a name for your repository (e.g., `malgus-game-app`).
3. **Description**: Optionally, provide a description of your repository.
4. **Public or Private**: Choose whether you want the repository to be public or private. 

   *Note: For GitHub Pages, it must be public.*

5. **Initialize with a README**: You can choose to add a README file, which is optional but recommended.

6. Click “Create repository.”

### If Necessary, Copy and Paste the Provided Instructions into a Notepad

```sh
echo "# malgus-game-app" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/mindmotivate/malgus-game-app.git
git push -u origin main
```


## GitHub YAML Deployment

### Prerequisites

#### GitHub Repository

- Ensure your app's source code is in a GitHub repository.

#### Build Artifacts

- Your app should be built into static files (e.g., using `npm run build` for React apps) that can be served as a static site.

#### GitHub Pages

- GitHub Pages allows you to host static websites directly from your GitHub repository.

### Push Your Local Project to GitHub

#### Initialize Git in Your Local Project

1. Open your terminal or command prompt and navigate to your project directory.
2. Initialize a git repository if you haven’t already:

    ```bash
    git init
    ```

#### Add and Commit Your Code

1. Add your project files to the staging area:

    ```bash
    git add .
    ```

2. Commit the changes:

    ```bash
    git commit -m "Initial commit"
    ```

#### Add Remote Repository

1. Add the GitHub repository as a remote:

    ```bash
    git remote add origin https://github.com/<username>/<repository>.git
    ```

   Replace `<username>` with your GitHub username and `<repository>` with the repository name you created.

#### Push to GitHub

1. Push your local code to GitHub:

    ```bash
    git push -u origin main
    ```

   If you used a different default branch name (e.g., `master`), use that name instead of `main`.

### GitHub Actions Workflow

- The following commands and actions are automatically included in your GitHub Actions workflow defined in your `.github/workflows/deploy.yml` file:

    ```yaml
    # Workflow for building and deploying the Malgus Game App to GitHub Pages
    name: Deploy Malgus Game App

    on:
      push:
        branches:
          - main

    permissions:
      contents: write
      pages: write
      id-token: write

    concurrency:
      group: "pages"
      cancel-in-progress: false

    jobs:
      build-and-deploy:
        runs-on: ubuntu-latest
        steps:
          - name: Checkout Code
            uses: actions/checkout@v3

          - name: Set up Node.js
            uses: actions/setup-node@v3
            with:
              node-version: '16'

          - name: Install Dependencies
            run: npm install

          - name: Build the Application
            run: npm run build

          - name: Deploy to GitHub Pages
            uses: JamesIves/github-pages-deploy-action@v4
            with:
              branch: gh-pages
              folder: build
            env:
              ACCESS_TOKEN: ${{ secrets.ACTIONS_DEPLOY_ACCESS_TOKEN }}
    ```

- This workflow handles the building and deployment of your app to GitHub Pages whenever you push changes to the `main` branch.
