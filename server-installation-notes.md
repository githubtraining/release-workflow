✅ | This course is fully compatible GHES version 2.17.4 or higher.
--- | ---

*Supported versions of GHES are visible by using the drop-down in the [official documentation](https://help.github.com/enterprise/).*

### Course dependencies

The following are dependencies of the course. The course may continue to work without these dependencies, but learners won't experience the course as designed.

| Dependency | Required? | Reason  | Alternative  |
|-------------------- | ------------------------|--------------|------------ |
| GHES v2.17.4 | No | This course makes use of [suggested changes](https://github.blog/changelog/2018-10-16-suggested-changes/) which were released in v2.17.4 | **The course will still work**, but suggested changes will appear as pull request comments |
| GHES must be able to reach githubusercontent.com  | Yes | Images used throughout the course are served from this domain. Learners will find broken images required to take the course without this access. | Manually download the images referenced in the `responses/` folder, upload them to an accessible domain, and replace the images in the `responses/` folder. |
| Learner must be able to reach github.com and outside web  | No  | Links are provided to resources that live on the outside web. | Without access to resources on the outside web, learners will reach blocked resources. You can change the links to these resources in the `responses/` folder, and in the template repository. |
| The [Release Drafter GitHub App](https://github.com/toolmantim/release-drafter) must be installed or approved for installation. | No   | Used in a course step to teach learners how to create automatic releases. | If the app won't be installed or pre-approved, remove the Release Drafter step in `config.yml`, the step that follows it, and any references to the GitHub App in the `responses/` folder. |
