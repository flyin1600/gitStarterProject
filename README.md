# gitStarterProject

A). The first step to working on a GitHub project is to create your own fork in GitHub
   1. https://help.github.com/articles/fork-a-repo/

B). The second step is to clone your fork to your local machine
   1. Before, you need to set up git https://help.github.com/articles/set-up-git/ (only do it once)
   2. Authenticating with GitHub from Git . Use this link for instructions on how to set up your ssh keys with GitHub: https://help.github.com/articles/connecting-to-github-with-ssh/
   (only do it once)
   3. When you clone, use ssh, not https :
      3.1. click Clone or download. Select ssh, click the icon to copy the clone URL for the repository( from your fork)
      3.2. `git clone [pasteTheURL]`
   4. `git remote -v`  : this will show you the name that git knows about for your fork on GitHub, it is probably origin. 
   5. `git remote add upstream git@github.com:flyin1600/gitStarterProject.git`   : this command let's your local git know about my repository (the overall project's main repo), and allows you to talk to it, when you talk to my repository, you will refer to it as "upstream"  (only do it once, to configure git to sync your fork with the original repository that you did a fork from )
   6 `git remote -v`  : this will show you the name of your origin and the upstream. 


C). Steps to Create a new file in your local copy of the repo called YourTest.py
   1. `git log`
      this command shows you the commit history of the repository. It will show you important tags (branch names) such as where you currently are, called HEAD, and what your current branch is called (eg: HEAD -> master)
   2. `git checkout -b add-file`   ( `git checkout -b name-of-your-branch`)
      this created a new branch for your work called "add-file"
   3. `git log`
      notice that the output has changed, instead of HEAD -> master, you now should see HEAD -> add-file.  you should also see "master" on the same line, because you have not made any changes, master and add-files refer to the same place in your repository's change timeline
   4. `git branch`
      this command will show you all of the branches in your repository, your currently active branch will have a *
   5. create a file called YourTest.py. In this file define a class called YourClass
   6. Add this new file to your repository using the git command line tools:
     i. `git status`   :this will show you that your new file is currently *untracked*, or not in the repository
     ii. `git add YourClass.py` : this add the file to the staged
     iii. `git status` : this will show you that your file is now *staged*
     iv. `git commit -m "YOUR COMMIT MESSAGE"`  : this will finish your change locally

D). Send your change up to your GitHub fork
   1. `git push origin add-file`  ( `git push origin name-of-your-branch`)
   

E). Send a Pull Request (PR) of your change to the main project repository: 
   1. go to your fork on GitHub
   2. If you do this fast enough, GitHub will probably show you a link with the name of your branch, asking if you want to create a Pull Request.  If not, on the left, near the top, there will be a drop down called "Branch: master", if you click on it, you can find your branch "add-file" and then click the button next to it "New pull request"
   3. In the next window select "Create Pull Request"

F). Once your PR is approved(wait for the merge), update your repository to be in sync with the project:
   1. Update your local copy
     i.  `git checkout master`   (you move the head form add-file branch to master)
     ii. `git fetch upstream`  (download changes from upstream)
     iii.`git merge upstream/master`  (move your master to upstream master , that is update to all new changes in upstream)
     this series of commands makes you are on your local master branch, gets all changes from the main project (upstream) and then merges the changes from upstream's master into your master
   2. Update your fork on GitHub to be in sync with your local copy
     i. `git push origin`
     this sends all changes from your local master, to your GitHub's master
