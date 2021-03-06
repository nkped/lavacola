## How to publish Create-React-App on Github Pages ##

**There are two ways of deploying to GHPages.
First option requires install of gh-pages (dependency) and deployment from designated gh-branch. The second option only requires a folder on main branch named "docs" as publishing source.**

**Let's go with option 2..**


***Note!** *The guide below has one #issue that I will address soon, but works with a minor work-around.***
***Note!** *At the bottom of this guide, you find suggested/nescesary features not yet installed.*** 

***#issue:** GH Pages requires you create and push docs-folder to repo to activate. However creating docs-folder before running build in VS Code complicates the mv-command (rename) of build into docs. Remember, build has to be named docs, since docs is publishing source.*

***#Solution:** Either improve rename-method or activate GH Pages without docs or run build before active og GHPages.*

***Also:*** 
- You might need to initially create EMPTY repo WITHOUT README.md 
- CRA is born with git - do not `git init`

## So, first GHPages site is online. Here is what I did:

- Install CRA

- In package.json write key: "homepage" with value "https://username.github.io/project"

- Create folder on main branch named docs

- `git add .`

- `git commit -a -m "Add docs/"`

- `npm run build`

**NB! Next, delete (empty) docs-folder temporarily. Otherwise, when you attemt to rename build-folder to "docs" using mv-command, build will end up nesting in docs (because docs already exists) - and that will break deployment.**

- `rm -rf docs`

- `mv build docs`

**Done! Page should now be deployed (give it a couple minutes).**

*Original ressourse* https://betterprogramming.pub/publish-create-react-app-to-github-pages-the-easy-way-542e864da589
