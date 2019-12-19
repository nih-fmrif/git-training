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

## Pull Request Demo 


## Merge Conflicts Walkthrough 
For this walkthrough, we'll pair up into teams and work through the example together. Dustin and I (Arsh) will be teaming up for this example. 


All of this will be on the RStudio terminal. 

**NOTE:** Here we've created an organization called [NIMH-DSST-git-training](https://github.com/NIMH-DSST-git-training) and the repositories that y'all create in teams will be within this organization GitHub account. It's important that each team picks a unique name for their team repo on GitHub (or remote) 

**Key Difference:** You'll create your local repository just like in previous sessions. The only difference here is that, on GitHub, you'll create a remote repository from the *organization GitHub account* [NIMH-DSST-git-training](https://github.com/NIMH-DSST-git-training) rather than your *personal GitHub account*.

Also, the commands that Dustin will execute will appear under **Team Member 1:** and commands that I'll execute on my copy of the account will be appear under **Team Member 2:**. Commands that we'll both execute will appear under **Both:** 


**Team Member 1:**  

```shell
# create a local repository
mkdir session3-merge-conflicts-team-A 

cd session3-merge-conflicts

# make it a git repo 
git init 
```

- Create a new repository [NIMH-DSST-git-training](https://github.com/NIMH-DSST-git-training) with name `session3-merge-conflicts-team-A`
- Within `session3-merge-conflicts-team-A` repository, go to `Settings > Collaborators & teams > Add Collaborator` and add your team mate (using their GitHub username) as a collaborator
- Now, copy the repo URL to the clipboard

On the local copy of the repository: 

```shell 
# connect the remote repo with the existing local repo
git remote add origin <repo URL> 

# create a README file 
touch README.md
```
Open the README.md in the RStudio text editor. Copy and paste the markdown script below in README.md

```markdown
# Session 3 Markdown Notes 
Practicing markdown syntax with random lines of text

## Hobbies 
- Writing unordered lists in markdown?? 
- attending git-training sessions? No? Okay. 
- Politics (?!) Beats Game of Thrones! 

*This is just weird.* 
```
Save the file. 

```shell
git status 

git add -A 

git commit -m "adding a README"

git push origin master
```

================================================================================

Y'all can now see the changes on the GitHub repository. 

================================================================================

**Team Member 2:**

- Go to [NIMH-DSST-git-training](https://github.com/NIMH-DSST-git-training) and click on your team repository
- Clone the repository to your local machine

```shell
git clone <repository URL> 
```
================================================================================

Now both teammates have the most updated version of the repository. 

We are now going to create a scenario where 2 people will edit the same line of the same file and when one of them tries to pushes these changes to remote, they'll be notified of a **merge conflict** 

================================================================================

**Both:** 

Both teammates will open up the README on their local machine and list two new (hopefully, weird enough) hobbies under the existing ones. 

Save. 

Add and commit. 

**Team Member 1:** 

Pushes his changes first to the remote repository

**Team Member 2:**

Pushes her changes (after Dustin) to the remote repository. 

I recieve the following error: 
```shell
! [rejected]        master -> master (fetch first)
```

What it means is that the remote repository was updated after the last time I pulled the changes (or commits) from remote. So before I push any new changes or commits, I need to update my local copy to match that of the remote copy. 

Fix: 
```shell
git pull origin master 
```

Now, I get the following message: 
```shell
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

git is telling me that:
1. it pulled the changes from remote

2. found that the same file (i.e. `README.md`) had been modified by two (or more) people  

3. Tried to merge the changes itself  `Auto-merging README.md`

4. Figured that *same lines* have been changed by both team member and therefore, it can't figure out which changes to keep and which to discard. 

5. It's basically asking us to help out by fixing the conflict manually and commiting those changes. 

So lets do that. My README.md now looks like this.

```markdown
# Session 3 Markdown Notes 
Practicing markdown syntax with random lines of text

## Hobbies 
- Writing unordered lists in markdown?? 
- attending git-training sessions? No? Okay. 
- Politics (?!) Beats Game of Thrones! 
<<<<<<< HEAD
- Tennis 
=======
- Cooking
>>>>>>> d5805cf94a672f23ae1b5f17aca92fd9465bd533
- Reading

*This is just weird.* 
```
I've discussed the conflict with Dustin and we've both decided to keep the changes I made. So I'm going to delete his changes.
Below is how my README should look like after deleting Dustin's changes. 

```markdown
# Session 3 Markdown Notes 
Practicing markdown syntax with random lines of text

## Hobbies 
- Writing unordered lists in markdown?? 
- attending git-training sessions? No? Okay. 
- Politics (?!) Beats Game of Thrones! 
- Tennis 
- Reading

*This is just weird.* 
```

Save. 

```shell
git status

git add -A 

git commit -m "merge conflict resolution" 
```

This is the commit that resolves the conflict. 

```shell
git push origin master 
```

Now, I can push my changes to remote repository. 

Verify by going back to remote repository. 


