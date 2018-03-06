# gitStarterProject

1. The first step to working on a GitHub project is to create your own fork in GitHub
   1. https://help.github.com/articles/fork-a-repo/
2. The second step is to clone your fork to your local machine
   1. When you clone, use ssh, not https
   2. Use this link for instructions on how to set up your ssh keys with GitHub: https://help.github.com/articles/connecting-to-github-with-ssh/
3. Create a new file in your local copy of the repo called YourTest.py
   1. git log
     * this command shows you the commit history of the repository. It will show you important tags (branch names) such as where you currently are, called HEAD, and what your current branch is called (eg: HEAD -> master)
   2. git checkout -b add-file
     * this created a new branch for your work called "add-file"
   3. git log
     * notice that the output has changed, instead of HEAD -> master, you now should see HEAD -> add-file.  you should also see "master" on the same line, because you have not made any changes, master and add-files refer to the same place in your repository's change timeline
   4. git branch
     * this command will show you all of the branches in your repository, your currently active branch will have a *
   5. create a file called YourTest.py
   6. In this file define a class called YourClass
   7. Using the git command line tools, add this new file to your repository
     * git status
      - this will show you that your new file is currently *untracked*, or not in the repository
     * git add YourClass.py
     * git status
      - this will show you that your file is now *staged*
     * git commit -m "YOUR COMMIT MESSAGE"
      - this will finish your change locally
4. Send your change up to your GitHub fork
   1. git remote -v
     1. this will show you the name that git knows about for your fork on GitHub, it is probably origin
   2. git push origin add-file
   3. git remote add upstream git@github.com:flyin1600/gitStarterProject.git
     1. this command let's your local git know about my repository (the overall project's main repo), and allows you to talk to it, when you talk to my repository, you will refer to it as "upstream"
5. Send a Pull Request (PR) of your change to the main project repository
   1. go to your fork on GitHub
   2. If you do this fast enough, GitHub will probably show you a link with the name of your branch, asking if you want to create a Pull Request.  If not, on the left, near the top, there will be a drop down called "Branch: master", if you click on it, you can find your branch "add-file" and then click the button next to it "New pull request"
   3. In the next window select "Create Pull Request"
