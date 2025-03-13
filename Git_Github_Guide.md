Git & GitHub Collaboration Guide for Beginners

Introduction

Welcome to this beginner-friendly guide to Git and GitHub! This guide is designed for two-person collaboration—perfect for learning Git while working together on coding projects. We'll use Snow White and the Seven Dwarfs as our project example throughout this guide.

1️⃣ Understanding Git: The Basics

Git is a tool that helps you save, track, and manage changes in your code. Think of it as a time machine for your project! 🚀

Key Git Concepts:

Repository (Repo): A folder that Git tracks.

Commit: A snapshot of your project at a specific point.

Branch: A separate line of development.

Merge: Combining changes from one branch into another.

Push & Pull: Sending and receiving updates from GitHub.

2️⃣ Setting Up Git & GitHub

Install Git (If You Haven’t Already)

Windows: Download and install from git-scm.com

Mac: Install using Homebrew: brew install git

Linux: Use your package manager: sudo apt install git

Configure Git (Do this only once per computer)

# Set your name (will be attached to commits)
git config --global user.name "Your Name"

# Set your email (use the one linked to GitHub)
git config --global user.email "your.email@example.com"

Create a New GitHub Repository

Go to GitHub and create a free account.

Click New Repository → Name it snow-white-project → Click Create Repository.

Copy the provided repository URL.

Clone the Repository (Download It to Your Computer)

git clone https://github.com/your-username/snow-white-project.git
cd snow-white-project  # Move into the project folder

3️⃣ Your First Git Workflow

This is the simple cycle you'll follow while coding together on the Snow White and the Seven Dwarfs project.

Step 1: Create a New File & Track It

touch story.txt  # Create a new file to write the story
git add story.txt  # Track the new file

Step 2: Save Your Work (Commit)

git commit -m "Added initial Snow White story draft"

Step 3: Send Your Work to GitHub (Push)

git push origin main

Step 4: Get Updates from GitHub (Pull)

If your partner adds something new, you need to pull it before making your own changes.

git pull origin main

4️⃣ Working in Branches (Avoiding Conflicts!)

A branch is a safe space to experiment with changes without affecting the main project.

Creating a Branch

Let's say one of you wants to work on the dwarfs' names while the other works on Snow White's backstory.

git checkout -b add-dwarfs  # Creates and switches to a new branch

Switching Between Branches

git checkout main  # Switch back to the main branch

Merging Your Changes

Once you're happy with your changes, you can merge them into main.

git checkout main  # Switch to main branch
git merge add-dwarfs  # Merge your changes
git push origin main  # Push merged changes to GitHub

5️⃣ Handling Merge Conflicts (Real-World Example)

A merge conflict happens when two people change the same part of a file. Here’s how to fix it.

Example Conflict Scenario:

Person A changes the story's introduction and commits it.

Person B also changes the introduction and commits it.

When Person B tries to push, Git says: “Merge conflict!”

Fixing the Merge Conflict:

Git marks the conflict inside story.txt:

<<<<<<< HEAD
Once upon a time, there was a princess named Snow White.  # Person A's version
=======
Snow White was the fairest of them all, living in a grand castle.  # Person B's version
>>>>>>> add-intro

Edit the file manually, keeping the correct version.

Stage & commit the fixed file:

git add story.txt
git commit -m "Resolved merge conflict in story introduction"
git push origin main

6️⃣ Best Practices for Git Collaboration

✅ Always pull before pushing (git pull origin main). ✅ Use meaningful commit messages (git commit -m "Added Snow White's backstory"). ✅ Keep branches small (One feature per branch). ✅ Resolve merge conflicts together if you're unsure.

7️⃣ Advanced: Introduction to Automated Testing

Why Testing? Before merging code, we want to make sure nothing is broken!

Example: A Simple Python Test with Pytest

Let's say we have a script that counts the dwarfs.

# dwarfs.py
def count_dwarfs():
    return 7

def test_count_dwarfs():
    assert count_dwarfs() == 7

Running the Test

pytest dwarfs.py  # Run the test

Automating Tests with GitHub Actions (Optional)

GitHub can run tests automatically whenever you push changes.

Create a .github/workflows/test.yml file.

Add this code:

name: Run Tests
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Install Python
        uses: actions/setup-python@v3
        with:
          python-version: '3.x'
      - name: Install dependencies
        run: pip install pytest
      - name: Run tests
        run: pytest

Now, GitHub will automatically test your code when you push changes!

Final Thoughts 🎉

Git is a powerful tool for coding together! Start small, practice often, and soon you'll be collaborating like a pro. 🚀

👩‍💻👨‍💻 Next Steps:

Create your snow-white-project repository and start pushing changes.

Try using branches and pull requests.

Experiment with fixing a merge conflict!

🔹 Happy coding! 😊

