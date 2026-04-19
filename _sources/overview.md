# Overview

Use this page to document project goals, data sources, and scope.


Link to open the Jupyter Book
https://aishwaryasalvi777.github.io/Early_Stage_Chronic_Disease_Detection/intro.html

# How to Build the book after every change in .md file:

Use this exact workflow every time you edit a markdown page.

Open Terminal in your project root folder
Path should be your repo folder, not inside archive.

Build the book
Run:
/opt/homebrew/bin/jupyter-book build docs

Open the updated local site
Open:
index.html

Refresh browser after each build
Use normal refresh, or hard refresh if changes do not appear.

Publish to GitHub Pages (only if you want the online site updated)
Run:
/opt/homebrew/bin/ghp-import -n -p -f docs/_build/html

Check live site
Open:
https://aishwaryasalvi777.github.io/Early_Stage_Chronic_Disease_Detection/

Quick repeat routine:
Edit .md file -> Build -> Check local HTML -> Publish (optional) -> Check live URL

