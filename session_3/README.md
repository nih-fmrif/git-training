# Session 3
In this session we'll be covering the following topics: 
- Collaboration 
- Branching 
- Merging 
- Pull requests 
- Merge conflict resolution 

## Branching Demo 


## Walkthrough 
```shell
mkdir session3-merge-conflicts

cd session3-merge-conflicts

# make it a git repo 
git init 

```

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



