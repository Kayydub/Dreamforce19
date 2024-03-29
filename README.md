## Set Up the Salesforce DX Project

Our first goal is to set up a developer project which we'll use to modify our application. It starts by cloning the repository. Use the command ...

    git clone https://github.com/Kayydub/Dreamforce.git

## Need Help?
sfdx --help // lists all top-level topics
sfdx force --help // lists all the topics under force
sfdx force:org --help // lists all the commands in the topic force:org
sfdx force:org:open --help // detailed info about the force:org:open command
    
## Steps

Authorize to your Developer Hub (Dev Hub) org.      Sfdx force:auth:web:login -d -a "DevHub"
If you already have an authorized DevHub, set it as the default:   sfdx force:config:set defaultdevhubusername=<username|alias>

Create a scratch org.
    sfdx force:org:create -s -f config/project-scratch-def.json -a DF19

If you want to use an existing scratch org, set it as the default:
    sfdx force:config:set defaultusername=<username|alias>

Push your source.
    sfdx force:source:push -f

Open the scratch org.
    sfdx force:org:open 

Make some changes and then Pull your source.

    sfdx force:source:pull -f

Git commands:
    Create a new branch: git checkout -b branchname
    pull source: git pull
    Delete a branch: git branch -d branchname


Git Commands to push your branch to the cloud:

    git status
    git add -A
    git commit -m "Comments"
    git push origin branchname

    














## Description of Files and Directories  

* **sfdx-project.json**: Required by Salesforce DX. Configures your project.  Use this file to specify the parameters that affect your Salesforce development project.
* **config/project-scratch-def.json**: Sample file that shows how to define the shape of a scratch org.  You reference this file when you create your scratch org with the force:org:create command.   
* **force-app**: Directory that contains the source for the sample Force.com app and tests.   
* **.project**:  Required by the Eclipse IDE.  Describes the Eclipse project. 
* **.gitignore**:  Optional Git file. Specifies intentionally untracked files that you want Git (or in this case GitHub) to ignore.

## Issues

Please log issues related to this repository [here](https://github.com/forcedotcom/sfdx-simple/issues).

