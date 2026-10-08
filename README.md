# Samaggi Git Training

Practice Git by making a small frontend update: change an event's details, commit your changes, and open a pull request.

## What you need

- Git installed. Run `git --version` in your terminal to check.
- A GitHub account, a code editor, and a web browser.

## 1. Fork and clone the repository

On GitHub, click **Fork** to create your own copy of this repository. In your fork, click **Code** and copy the HTTPS URL.

Replace `YOUR_USERNAME` with your GitHub username, then run these commands one at a time:

```sh
git clone https://github.com/YOUR_USERNAME/training.git
cd training
```

- `git clone` downloads the repository and its Git history into a new folder called `training`.
- `cd training` moves your terminal into that folder. Run the remaining commands there.

If you have not configured Git before, replace the example name and email with yours:

```sh
git config user.name "Your Name"
git config user.email "YOUR_EMAIL"
```

These set the author name and email recorded in your commits for this repository. You can use your GitHub noreply email from your GitHub email settings.

## 2. Create your branch

Use `<your-name>` as your branch name placeholder. Replace it with your name, using lowercase letters and hyphens, such as `alex-smith`. Do not type the angle brackets.

```sh
git checkout -b <your-name>
```

`git checkout -b` creates a new branch and switches to it. A branch lets you work on your changes separately from `main`.

For example:

```sh
git checkout -b alex-smith
```

## 3. Make a simple frontend update

Open `index.html` in your editor and change the event's:

- Title inside `<h1>`.
- Date and time under **When**.
- Location under **Where**.

Save the file, then open `index.html` in your browser. Refresh the page after any further edits and check that your new details appear. No installation or server is needed. The **Join event** button is unfinished; this exercise only needs the text changes above.

## 4. Review and commit your changes

Run these commands one at a time:

```sh
git status
git diff
git add -A
git diff --staged
git commit -m "Update event details"
```

- `git status` shows your current branch and which files have changed.
- `git diff` shows the edits that have not been staged yet. Check that they match what you intended.
- `git add -A` stages all new, modified, and deleted files in the repository. Staging prepares changes for your next commit; it does not save a commit or upload anything. Check `git status` first so you know what you are including.
- `git diff --staged` shows the changes prepared for the commit. Review them before continuing.
- `git commit -m "Update event details"` saves the staged changes as a commit on your branch. The `-m` option supplies a short message describing the change.

Check your saved work:

```sh
git log --oneline -1
git status
```

`git log --oneline -1` shows your latest commit's short ID and message. `git status` should report a clean working tree, meaning there are no remaining uncommitted changes.

## 5. Push and open a pull request

Replace `<your-name>` with the same branch name you created earlier:

```sh
git push -u origin <your-name>
```

`git push` uploads your commits to GitHub. `origin` is the name Git gives your cloned repository's remote (your fork). `<your-name>` selects the branch to upload. `-u` connects your local branch to the remote branch, so future uploads from this branch only need `git push`.

On GitHub, open your fork and click **Compare & pull request**. Choose the original training repository and `main` as the destination, with your fork and your named branch as the source.

Give the pull request a title such as **Update event details** and briefly describe what you changed. Click **Create pull request** to submit your work for review.

If you need to make another change, edit and save the file, then run:

```sh
git diff
git add -A
git diff --staged
git commit -m "Adjust event details"
git push
```

The new commit will appear in the same pull request automatically.
