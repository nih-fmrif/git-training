# Session 3
In this session we'll be covering the following topics: 
- Collaboration 
- Branching 
- Merging 
- Pull requests 
- Merge conflict resolution 

While Dustin goes over the slides, please share your `GitHub Usernames` and corresponding `Email address` on this document: 
[Session3-usernames](https://docs.google.com/document/d/1C9TMQAC1u81uOt8hZ8Z_lPlvL7f3o2tvtch0bw3IyiE/edit?usp=sharing)

## Branching Demo 


## Merge Conflicts Walkthrough 
For this walkthrough, we'll pair up into teams and work through the example together. Dustin and I (Arsh) will be teaming up for this example. 


All of this will be on the RStudio terminal. 

**NOTE:** Here we've created an organization called [NIMH-DSST-git-training](https://github.com/NIMH-DSST-git-training) and the repositories that y'all create in teams will be within this organization GitHub account. 

**Key Difference:** You'll create your local repository just like in previous sessions. The only difference here is that, on GitHub, you'll create a remote repository from the *organization GitHub account* [NIMH-DSST-git-training](https://github.com/NIMH-DSST-git-training) rather than your *personal GitHub account*.

**Note about unique repo names**

Also, the commands that Dustin will execute will appear under **Dustin:** and commands that I'll execute on my copy of the account will be appear under **Arsh:**. Commands that we'll both execute will appear under **Dustin and Arsh: ** 

Y'all can divide up the same chunks amongst yourselves.

**Dustin and Arsh: **  

```shell
# create a local repository
mkdir session3-merge-conflicts-team-A 

cd session3-merge-conflicts

# make it a git repo 
git init 
```
**Remember to set your working directory in RStudio to your local repository**

Create a repo with the same name on the org account, where you've been added as a collaborator. 

```shell 

git remote add origin <repo URL> 
```

On of the team member will now create a README.md and add exactly 2 lines of text. 
Add and commit the initial changes. 
Push the changes to the remote repository. 

Team member 2 who has been added on the repository as a collaborator will pull the changes. 

Now, both members of the team have the exact same content in the files of their working directory. 

Both collaborators will now add a line of text on `line 5` of the README.md 

Both of you add and commit those changes. 

Now, team member 1 will push her changes to the remote repo. 

Once, team member 1 is done pushing her changes. Team member 2 can then proceed to push his changes to the remote. 

At this point, team member 2 will run into a merge conflict because 2 people edited the same line of the same file. 
Now, team member 2 would have to go into the README and manually choose which changes to keep. His changes, 
or that of his team members, or change it completely. 

Make a decision. Add and commit. And that commit will be recorded as merge conflict resolved. 



