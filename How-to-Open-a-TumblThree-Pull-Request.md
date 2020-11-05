The following commands are used to set up a fork of TumblThree's Git repository on GitHub, create a new branch and create a GitHub pull request ("PR") of the changes in that branch.

This guide shows which [git](https://git-scm.com/)\* commands you have to use on the windows command line. Another solution would be to use a GUI tool like [TortoiseGit](https://tortoisegit.org/)\* or [the like](https://git-scm.com/download/gui/windows)\*.

*\* external link*

## Set up your own fork of the TumblThree repository

1. Click the "Fork" button at the top right on our [repository](https://github.com/TumblThreeApp/TumblThree) page
    * This creates your own copy ("fork") of the TumblThree repository that you can write to ("push"). This is needed because only TumblThree maintainers have write access to the main repository.
2. Open a command prompt (terminal).
3. Create a directory where you want to get a copy of the TumblThree code:
    ```
    $ mkdir TumblThree-copy
    $ cd TumblThree-copy
    ```
4. Get a local copy of the code:
    ```
    git clone https://github.com/<your_username>/TumblThree.git .
    ```
    * where `<your_username>` is your GitHub username
5. Add the TumblThree repository as a remote repository:
    ```
    git remote add TumblThreeApp https://github.com/TumblThreeApp/TumblThree.git
    ```

## Create a new branch and make your changes

1. Check out the *master* branch:
    ```
    git checkout master
    ```
2. Create a new branch:
    ```
    git checkout -b <your_branch_name> origin/master
    ```
    * where `<your_branch_name>` is your desired branch name (e.g. "123-new-feature-name")

3. Add new files with
    ```
    git add <filename>
    ```
    * where `<filename>` specifies the file to add (repeat the command for every file) or to add all new files, even in subdirectories, at once:
    ```
    git add .
    ```
4. Commit all your changes with `git commit`.
5. Transfer these changes to your GitHub repository with `git push`.
    * You have now all your changes in your own repository on GitHub.

## Create a pull request from your new branch

To submit your new branch for review, create a GitHub pull request with the following steps:

1. Go to your repository page and create a pull request by clicking on `Compare & pull request` to request review and merging of the commits in your pushed branch. Fill in a *Title* and explain in the *Description* why the change is needed and, if fixing a bug, how to reproduce the bug. Make sure you have done each step in the checklist that appears in your new PR.
2. After you have filled in all the details press `Create pull request`.
3. Await feedback or a merge from TumblThree's maintainers. We typically respond to all PRs within a couple days, but it may take up a bit longer, depending on the maintainers' workload.

Thank you!

## Following up

To respond well to feedback:

1. Ask for clarification of anything you don't understand and for help with anything you don't know how to do.
2. Post a comment on your pull request if you've provided all the requested changes/information and it hasn't been merged after a week. Post a comment on your pull request if you're stuck and need help.
    * A `question` label on a PR means that the TumblThree maintainers need you to respond to previous comments.
3. Keep discussion in the pull request unless requested otherwise (i.e. do not email maintainers privately).
4. Do not continue discussion in closed pull requests.

To make changes based on feedback:

1. Check out your branch again:
    ```
    git checkout <your_branch_name>
    ```
2. Make any requested changes and commit them with `git add` and `git commit`.
3. Push to your branch and the pull request will be updated automatically:
    ```
    git push
    ```

Once all feedback has been addressed, then we'll add your commit to TumblThree.

Well done, you are now a TumblThree contributor!
