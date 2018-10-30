### Before
Bot opens welcome issue describing the motivation for GitHub Flow as a simple workflow. Bot identifies the need for a release, explains how it can be achieved with tags. Requests that the user tags the current codebase.

### 1
User adds a release.
Bot responds to the tag, explains how this can be used.

### 2
User closes issue.
Bot comments in old issue, and Bot opens a new bug issue, asks user to solve.

### 3
User opens a PR to solve issue.
Bot requests changes to the PR, explains this hot fix only applies to existing release. Explains to the user the need for a long living release branch.

### 4
User creates a release branch.
Bot validates release branch, closes PR. Asks user to open a new PR against the release branch.

### 5
User creates new PR against release branch.
Bot approves.

### 6
User merges.
Bot introduces some project management for planning of next release.

### 7
User moves a project card to in progress.
Bot opens a new PR against master for the new feature.

### 8
User approves.
Bot merges. Asks user to introduce a changelog.

### 9
User installs Probot App (?) to craft the changelog.

----

Should user add the pull request/issue as step 3, for the bug issue created in step 2 ? Change name of project to Release 1.0?

Project board doesn't have columns.

Have bot delete branch after merge in step 8.

User shouldn't close issue in step 2. Bot should do that for them, and the comment should only point them to the next issue. All important info should be in first OP or in a comment that's posted in "before" step.

Maybe set branch protections again before bot opens its own PR so user doesn't just merge

"managing releases" issue should be closed at some point, maybe when release is merged 
