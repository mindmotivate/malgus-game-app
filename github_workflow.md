## 1. Create a GitHub Repository
Sign In to GitHub:

Log in to your GitHub account. If you don’t have one, you’ll need to create it.
Create a New Repository:

Go to GitHub and click the “+” icon in the upper-right corner, then select “New repository.”
Repository Name: Enter a name for your repository (e.g., malgus-game-app).
Description: Optionally, provide a description of your repository.
Public or Private: Choose whether you want the repository to be public or private. 

*Note: For GitHub Pages, it must be public.
Initialize with a README: You can choose to add a README file, which is optional but recommended.

Click “Create repository”

If necessary copy an paste the provided instructions into a notepad:

echo "# malgus-game-app" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/mindmotivate/malgus-game-app.git
git push -u origin main