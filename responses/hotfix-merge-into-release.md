Nice job! That should fix it.

## Avoiding deployed bugs

Avoiding bugs is difficult to do without a dedicated testing environment. With GitHub Pages, for example, code will only deploy from a master branch. We're only able to find bugs, then, if we see them live on the website, when they have the potential to affect countless users.

Depending on your set-up, this might be the same for your website, app, or software as well. Testing your code once it reaches master is a poor practice, and you should try to avoid it.

At GitHub, we specifically set up special [Deploy environments](https://githubengineering.com/deploying-branches-to-github-com/#deploy-environments) from unique branches, which allow us to test in production-esque environments without merging.

Additionally, you might set up [continuous integration](https://github.com/marketplace/category/continuous-integration), so that a series of standardized checks will run on every commit that you push to an open pull request. This should help you identify your bugs and errors before they even make it to a staging environment.

## Step 13: Merging into the release branch

Let's apply our new fix to our release branch, and then set our users and future development up for success.

### :keyboard: Activity: Update the release branch

1. Click **Merge pull request**

<hr>
<h3 align="center">I'll respond below with your next step</h3>
