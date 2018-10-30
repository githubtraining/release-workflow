## Create a released based workflow

### User Registration

On registration, create an empty repository called `released-based-workflow`

### Before

Bot opens the first issue using the text from `responses/01_welcome.md` with the title "Understanding the GitHub flow"

### Step 1: Tag the current codebase

title: Tag the current codebase
description: <replace-me-with-description>
activity: 
  - user: adds a tag to the current codebase
  - bot: responds to the tag the user added with: `responses/01_tags-and-releases.md`
  - bot: crafts a release based on the tag
  - bot: closes first issue, opens new issue with: `responses/close-issue-next-issue.md`
    - new issue body: `responses/02_bug-fix.md`

### Step 2: Open a pull request to fix the issue <replace-with-better-title>

With the next issue just created from the bot, the user is prompted to solve the bug by opening a PR. Bot requests changes to the PR, explains that this hot fix only applies to the existing release. Bot explains to the user the need for a long living release branch.

title: 
description:
activity:
  - user: creates a pull request with the instructed changes in `responses/02_bug-fix.md`
  - bot: responds to the pull request with more requested changes and to create a long living release branch with: `responses/02_create-release-branch.md`

### Step 3: Create a release branch

title:
description:
activity:
  - user: creates a release branch
  - bot: closes the PR
  - bot: responds by validating the creation of the release branch and asks the user to open a new PR against the release branch and not master with: `responses/03_PR-release-branch.md`

### Step 4: Open a pull request on your release branch

title:
description:
activity:
  - user: opens a new PR against the release branch with the previous instructed changes
  - bot: validates that the PR was opened against the release branch with: `responses/04_pr-branch-success.md` or `responses/04_pr-branch-error.md`
  
### Step 5: Merge your pull request

title:
description:
activity:
  - user: merges the pull request
  - bot: validates merge with: `responses/05_merge-success.md`
  - bot: responds with new issue

### Step 6: Introduction to project management

title: 
description:
activity:
  - user: moves a project card to the "in progress" column
  - bot: validates the move with: `responses/06_project-move-success.md` or `responses/06_project-move-error.md`
  - bot: closes the issue and opens a new PR against master for the new feature

### Step 7: Approve the pull request

title:
description:
activity:
  - user: approves the pull request
  - bot: merges the new feature pull request into master
  - bot: prompts the user to create another release branch to prep for another release with: `responses/07_release-branch-request.md`

### Step 8: Create another release branch

title:
description:
activity:
  - user: creates another release branch
  - bot: responds with asking the user to introduce a changelog by installing a Probot app with: `responses/08_changelog.md`

### Step 9: Install the <replace-me> Probot app

title:
description:
activity:
  - user: install the <replace-me> Probot app
  - user: craft the changelog using the Probot app
  - bot: validates the changelog with: `responses/09_changelog-success.md` or `responses/09_changelog-error.md`
  - bot: prompts the user to open a pull request with: `responses/09_changelog-success.md`

### Step 10: Open a pull request for the changelog

title:
description:
activity:
  - user: open a PR for the changelog against the release branch 
  - bot: validates response with: `responses/10_success.md` or `responses/10_error.md`

---

| Step | App actions                                                               | User actions                                            | Related event       |
|------|---------------------------------------------------------------------------|---------------------------------------------------------|---------------------|
| 0    | App creates repo.                                                         |                                                         |                     |
| 1    | App creates an issue, asks user to add a tag to the codebase              | User creates a tag                                      | release             |
| 2    | App edits the release, asks user to ???                                   | User performs an action                                 | ???                 |
| 3    | App closes first issue, opens new issue with bug report and asks for a PR | User opens a PR                                         | pull_request        |
| 4    | App requests changes, asks for a long living release branch               | User creates a new release branch                       | create              |
| 5    | App closes PR, asks for a new PR with release as base                     | User creates a PR                                       | pull_request        |
| 6    | App requests merge                                                        | User merges                                             | pull_request.closed |
| 7    | App opens new issue, prompts project board card movement                  | User moves card to "In Progress"                        | project_card        |
| 8    | App closes issue and opens PR against master for a new feature            | User approves PR                                        | pull_request_review |
| 9    | App merges feature and asks user to create new release branch             | User creates another release branch                     | create              |
| 10   | App creates issue, asks user to install Probot app for changelogs         | User installs changelog Probot app and crafts changelog | issues (guessing)   |
| 11   | App validates changelog, prompts user to open a PR                        | User opens a PR for the changelog                       | pull_request        |
