#!/bin/bash

REPO_NAME="auto-repo"
USERNAME="your-username"

# Create repo
gh repo create "$USERNAME/$REPO_NAME" --public --confirm

# Init local repo and push
mkdir "$REPO_NAME" && cd "$REPO_NAME" || exit
git init
echo "# $REPO_NAME" > README.md
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin "https://github.com/$USERNAME/$REPO_NAME.git"
git push -u origin main
