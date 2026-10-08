# Samaggi Git Training

A small frontend exercise for practicing Git: edit an event card, save your work in commits, and submit a pull request. Allow about 30–45 minutes. Basic HTML, CSS, and JavaScript knowledge helps.

## What you need

- Git installed (`git --version` should show a version).
- A code editor and a web browser.
- A GitHub account if you want to submit a pull request.

## 1. Get your own copy

On GitHub, click **Fork** on this repository. In your fork, click **Code** and copy the HTTPS URL. Replace `YOUR_USERNAME` below with your GitHub username:

```sh
git clone https://github.com/YOUR_USERNAME/samaggi-training.git
cd samaggi-training
```

If the repository has a different name, use the URL from **Code** and enter the folder Git creates.

Configure your name and email if you have not done so before. These commands apply to this repository only; use an email you are comfortable including in commits (GitHub provides a private noreply address in your email settings).

```sh
git config user.name "Your Name"
git config user.email "YOUR_EMAIL"
```

Create a branch for your work:

```sh
git switch -c feature/my-event-card
```

A branch keeps your changes separate from the starting version.

## 2. Open the page

Open `index.html` in your browser. No packages, server, or build step are needed. After editing a file, save it and refresh the browser.

| File | Purpose |
| --- | --- |
| `index.html` | Event content and page structure |
| `styles.css` | Colors, spacing, and button styles |
| `script.js` | RSVP button behavior |

The **Join event** button intentionally does nothing yet. Finishing it is part of the exercise.

## 3. Complete the frontend task

Make an event card for an event you would like to attend:

1. **Content:** In `index.html`, update the event title, date, and location.
2. **Style:** In `styles.css`, choose a new button background color and add a `button:hover:not(:disabled)` rule. Keep the text easy to read.
3. **Behavior:** Finish the click handler in `script.js`. On click, show **You're on the list! See you there.**, change the button label to **Joined**, and disable it.

Hints for task 3: use `rsvpMessage.textContent`, `rsvpButton.textContent`, and `rsvpButton.disabled`. This is a browser-only demo; refreshing the page resets the RSVP.

Save each task in its own commit. After the content task, for example:

```sh
git status
git diff
git add index.html
git diff --staged
git commit -m "Update event details"
```

`status` lists changed files. `diff` shows edits. `add` stages the changes you want to save. `diff --staged` lets you review that selection. `commit` records it in your branch history.

Repeat for the other two tasks:

```sh
git add styles.css
git commit -m "Style event button and hover state"
git add script.js
git commit -m "Add RSVP confirmation"
```

## 4. Check your work

- Your event title, date, and location appear correctly.
- The button has your new color and changes appearance on hover.
- Clicking it displays the exact confirmation message, changes its label, and disables it.
- Refreshing resets the button.
- The card fits a narrow browser window without horizontal scrolling.
- You can reach the button with Tab and activate it with Enter or Space.

Review your three commits and confirm there are no unsaved Git changes:

```sh
git log --oneline -3
git status
```

## 5. Share your work

Push the branch to your fork:

```sh
git push -u origin feature/my-event-card
```

On GitHub, open your fork and click **Compare & pull request**. Set the base repository to the original training repository and the base branch to `main`. Submit a pull request titled **Complete event card exercise**. Include a short description of your changes and the checks you completed. A screenshot is optional.

If a reviewer asks for changes, edit the files on the same branch, commit them, and run `git push`. The pull request updates automatically.

## Useful Git commands

| Command | What it does |
| --- | --- |
| `git status` | Check your branch and changed files |
| `git diff` | Review unstaged edits |
| `git diff --staged` | Review changes ready to commit |
| `git log --oneline` | View commit history |
| `git restore --staged styles.css` | Unstage a file while keeping your edits |
| `git switch main` | Return to the starting branch after committing your work |

## For the workshop organizer

Publish this starter repository to GitHub before sharing it. Create an empty GitHub repository named `samaggi-training` without adding a README, license, or `.gitignore`. From this folder, replace `OWNER` and run:

```sh
git add README.md index.html styles.css script.js .gitignore
git commit -m "Add Git workshop starter"
git remote add origin https://github.com/OWNER/samaggi-training.git
git push -u origin main
```

Share the repository link and ask learners to fork it. Keep `main` as the starter exercise; learners submit their completed versions as pull requests. The event details are sample content.
