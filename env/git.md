# Git clone to local
```git clone https://csil-git1.cs.surrey.sfu.ca/big-data-squad/capital-bikeshare-system-analysis.git```

type in your userid

type in your password

(If you don't want to enter username and password every time, please set up your ssh keys here: https://csil-git1.cs.surrey.sfu.ca/profile/keys)

You will see the repository in your local directory. 


#  Gitlab Version Control Commands
To learn more about all Git commands, see: https://dzone.com/articles/top-20-git-commands-with-examples
## pull most updated version from gitlab

In your local directory, run:

```git pull```

This command fetches and merges changes on the remote server to your working directory.


## push your modified version to gitlab

Once you have edited or modified some files or code on your local directory, and you want to update these to gitlab:

Step1: ```git add xxxx.ipynb```   (add this file to your local git database)

Step2: ```git commit -m "some messages here"```  (write a message indicating what you are doing)

Step3: ```git push```   (REALLY add the updated file to Gitlab, sends the committed changes of local to Gitlab remote repository.)

Step4: ```git status``` (see your current git status)

Step5: ```git checkout``` (tell git you have finished doing something, most of the time you should see "Your branch is up to date with 'origin/master'.")"


Command line instructions
You can also upload existing files from your computer using the instructions below.


Git global setup
git config --global user.name "chowkec"
git config --global user.email "jack_chow@sfu.ca"

Create a new repository
git clone git@csil-git1.cs.surrey.sfu.ca:chowkec/test.git
cd test
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master

Push an existing folder
cd existing_folder
git init
git remote add origin git@csil-git1.cs.surrey.sfu.ca:chowkec/test.git
git add .
git commit -m "Initial commit"
git push -u origin master

Push an existing Git repository
cd existing_repo
git remote rename origin old-origin
git remote add origin git@csil-git1.cs.surrey.sfu.ca:chowkec/test.git
git push -u origin --all
git push -u origin --tags