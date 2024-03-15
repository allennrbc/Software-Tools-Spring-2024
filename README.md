# Software-Tools-Spring-2024
# README
The purpose of this README document is to provide users a resource to reference in case of any questions. Feel free to add anything you deem would have a net value add to others' understanding of our project.

## Resources for Writing
Writing in markdown can be a bit intimidating to users coming from more complex word processing software. To lessen this burden, check out this [GitHub markdown cheatsheet](https://github.com/tchapi/markdown-cheatsheet/blob/master/README.md).

# GitHub Cheat Sheet
## Getting Started
If running on a Windows Machine, make sure you have some sort of bash console. Luckily, GitHub provides a free (and easy to setup and use) version:
Link to GitHub bash: https://gitforwindows.org

After confirming you have a bash instance, you can go ahead and confirm where you would like to store your version of the final project class code. I have seen people keep it under a directory like `C:Users/[Username]/Documents/Repository`.

### Cloning
1. Once you are satisfied with your selection, navigate using Git Bash to the directory. Alternatively, you should be able to pull up the Windows File Explorer, navigate there, right click anywhere there is no files, and select the start Git Bash here option.
2. Now you need to clone the existing repository from the remote server. To do this, you have to run the following command: `git clone https://github.com/veliche-bc-edu/Fall2021_ADEC732002.git`
3. You may be prompted to log into GitHub. Select whichever option makes sense for authenticating.
4. You should see files start downloading from the remote repository. If you have any errors, please feel free to post in our Canvas discussion board.

## Making Changes
### Fetching Changes from Remote
Before making ANY changes, it is strongly recommended that you pull all the changes that others have been making (and pushed to the remote server). To do this, you run `git fetch`. After running this, run a `git pull` to retrieve all the files from the remote server in the current branch.

### Checking Out Branches
To prevent affecting others' work, you will want to track your changes using your own branch. `git checkout -b [new_branch_name]` would allow you to do precisely just that. However, note that your `[new_branch_name]` must not only be descriptive so that the rest of your colleagues can understand, but must also be one single word. This can be done using the following nomenclature too: `[NewBranchName]` (... underscores work too). 

-> To swap back to any other branch, all you have to do is run `git checkout [existing_branch_name]`

### Commits
After completing some work, you will want to save your changes. However, just saving the file won't suffice, you should ideally seek to get a `commit` done locally to ensure you can revert your changes easily. To do this: 
1. Save your changes in your IDE (RStudio in this instance)
2. With your Bash instance in the repo folder, stage the files you would like to commit. This is done using `git add [filename]` 
    * Note: There is another command that would allow you to add the entirety of the changed files, however note that this add ALL of the new/modified files, so use it carefully: `git add .`
3. Once all your files have been staged, you can proceed to commit your changes. To do this, you must add a message that summarizes your changes. The command to run would be `git commit -m '[message]'`
    * Note: You may have to set up your `user.name` and `user.email` to be able to commit successfully. To do this you need to do the commands below and set your account's default identity. Omit `--global` to set the identity only in this repository. The email address should be the same that you used to set up your GitHub account and your name the same as your GitHub username.
    
        `git config --global user.email "you@example.com"`
    
        `git config --global user.name "Your Name"`
    * Also Note: You should include the issue number that you are looking to close out in your commit message. This would enable the automation in GitHub to take over and associate the code with the issue(s) you are resolving. Including a message such as `closes #xxx` would suffice, but you can get fancy using [the following guide.](https://stackoverflow.com/questions/1687262/link-to-the-issue-number-on-github-within-a-commit-message)

### Pushing Changes to Remote
To allow for further collaboration, you need to provide the remote directory with the files that you have been changing. Luckily for you, you have been committing all your changes along the way! To push these changes (commits), all you need to run is `git pull`. 

# Future Work 
Here we plan on outlining all of the idea we had but didn't have the time to implement. 
* Wide to long data transformations 
