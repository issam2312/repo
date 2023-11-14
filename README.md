# Git workflow

This document describes the git workflow that should be used when contributing
to Tosca Za project. It assumes a very basic understanding of
git (commits, branches, etc.) using the command line.

## Cloning the repository

1. **Clone the repository.** Click the green "<font color="green">Clone or download</font>" button <font color="blue">①</font>,
   and copy the url <font color="blue">②</font> and type

   <code>git clone <i>clone-url</i></code>

   at the terminal. Replace *`clone-url`* with the url that has been copied to
   your clipboard. For sympy/sympy, it will be
   `git@github.com:sympy/sympy.git`. If you have not set up your ssh keys with
   GitHub, use the https url by first clicking the `https` button <font
   color="blue">③</font>.

   ![clone.png](clone.png)

## Making changes

Before you make any changes, you should make a branch. Remember to **never
commit to master**. The command `git status` will tell you what branch you are
on. I recommend putting the git branch in your command prompt, so that you
will always know what branch you are on. See
[this guide](http://stackoverflow.com/a/24716445/161801) on how to do this.

It is important that you never commit to master because master will be the
branch that you pull upstream changes from (e.g., changes from
sympy/sympy).

1. **Update master.** Before you make any changes, first checkout master

   ```
   git checkout master
   ```

   and pull in the latest changes

   ```
   git pull
   ```

   This will make it so that your changes are against the very latest master,
   which will reduce the likelihood of merge conflicts due to your changes
   conflicting with changes made by someone else.

2. **Create a branch.** Once you have done this, create a new branch. You
   should make a branch name that is short, descriptive, and unique. Some
   examples of good branch names are `fix-install`, `docs-cleanup`, and
   `add-travis-ci`. Some examples of bad branch names are `feature`, `fix`,
   and `patch`. The branch name choice is not too important, so don't stress
   over it, but it is what people will use to reference your changes if they
   want to pull them down on their own computers to test them, so a good name
   will make it easier for others to understand what your branch does. In this
   example, the branch name is `fix-install`.

   To create the branch, run

   <code>
   git checkout -b <i>branch-name</i>
   </code>

   (replace *`branch-name`* with the branch name you chose). This will create a
   new branch and check it out. You can verify this with `git status`.

3. **Make your changes and commit them.** Once you have created your branch,
   make your changes and commit them. Remember to keep your commits atomic,
   that is, each commit should represent a single unit of change. Also,
   remember to write helpful commit messages, so that someone can understand
   what the commit does just from reading the message without having to read
   the diff.

   For example, at the command line, this might look like

   <pre><code>git add <i>filename [filename ...]</i>
   git commit
   </code></pre>

   This will open an editor where you can write your commit message.

4. **Push up your changes.**  Push your changes to your fork. Do this by
   running

   <code>
   git push <i>your-github-username</i> <i>branch-name</i>
   </code>

   (replace *`your-github-username`* with your GitHub username and
   *`branch-name`* with the name of the branch).

5. **Make a pull request.** 


## Important points

The important things to remember from this document are

1. You only need to clone and fork once per repository.

2. Always clone from the main repository and add your fork as a remote.

3. Never commit to master. Create a branch and commit to it.

4. Use `git status` often to check what branch you are on and see if you have
   any uncommitted changes.

5. Be descriptive in your branch names, commit messages, and pull request
   title and descriptions.

6. Once you have a pull request for a branch, you can push additional changes
   to the same branch and they will be added to the pull request
   automatically. You should never create a new pull request for the same
   branch.

7. Comment on the pull request when you want people to know that you have
   pushed new changes. Although GitHub does notify people of commit pushes,
   people are more likely notice your changes if you leave a comment.
