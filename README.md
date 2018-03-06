# gitStarterProject

1. The first step to working on a GitHub project is to create your own fork in GitHub
  1. https://help.github.com/articles/fork-a-repo/
2. The second step is to clone your fork to your local machine
  1. When you clone, use ssh, not https
  2. Use this link for instructions on how to set up your ssh keys with GitHub: https://help.github.com/articles/connecting-to-github-with-ssh/
3. Create a new file in your local copy of the repo called YourTest.py
  1. git checkout -b add-file
    1. this created a new branch for your work called "add-file"
  2. In this file define a class called YourClass
  3. Using the git command line tools, add this new file to your repository
    1. git status
      1. this will show you that your new file is currently *untracked*, or not in the repository
    2. git add YourClass.py
    3. git status
      1. this will show you that your file is now *staged*
    4. git commit -m "YOUR COMMIT MESSAGE"
      1. this will finish your change locally
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