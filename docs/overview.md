# Overview

Use this page to document project goals, data sources, and scope.


Link to open the Jupyter Book
https://aishwaryasalvi777.github.io/Early_Stage_Chronic_Disease_Detection/intro.html

# How to Build the book after every change in .md file:

** Use this exact workflow every time you edit a markdown page. **

1) Open Terminal in your project root folder
Path should be your repo folder, not inside archive.

2) Build locally:
/opt/homebrew/bin/jupyter-book build docs

3) Publish to GitHub Pages:
/opt/homebrew/bin/ghp-import -n -p -f docs/_build/html