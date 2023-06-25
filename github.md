# GitHub

> Platform for code hosting, version control, and collaboration

## Work [flow](https://docs.github.com/en/get-started/quickstart/github-flow)

![Example](https://docs.github.com/assets/cb-23923/mw-1440/images/help/repository/branching.webp 'Example of a branch "branching" off of main')

## Repository

> Organizes a project and its state

Purpose is to store:

- folders and files for project
- README file
  - Summarizes and gives useful info on the project
  - Stored as markdown file (md)
- license file

## Branches

> Versions of the repository

Main / Master Branch
: used as the root of the project

Branch
: a copy / snapshot of another branch at that moment in time

- **Changes** recommended not made on main
- A branch is **behind from main** if other changes were made on main that weren't added to the branch
  - Common when multiple people contributing to project
  - **Merge conflicts** arise when branches are merged together that made changes to the same parts of code

## Commits

> Saved changes to a branch

Shows:

- a commit message (explaining changes)
- log of changes
- author
- commit date
- id

## Pull Requests

> Propose changes to a repository

i.e. Merge a branch into a branch

Shows:

- differences of both branches
  - ONLY AT THE CREATION OF THE PULL REQUEST
- commits on branch being merged in
- files changed
- checks
- conversation

## Forks

> personal copy of another's repository

- Sync fork -> upstream ### Close issues from pull request message

Keywords: close closes closed fix fixes fixed resolve resolves resolved

- **Issue in the same repository**
  KEYWORD #ISSUE-NUMBER
  ```Closes #10```
- **Issue in a different repository**
  KEYWORD OWNER/REPOSITORY#ISSUE-NUMBER
  ```Fixes octo-org/octo-repo#100```
- **Multiple issues**
  ```Resolves #10, closes #123, fixes octo-org/octo-repo#100```
  - by making a pull request
- Sync upstream -> fork
  - Terminal: ```git fetch upstream```
    - Creates ```upstream/main``` branch
  - GitHub: Sync fork button

## Issues

Description:

- "What is the current behavior?"
- "What changes are you suggesting?"

### Close issues from pull request message

Keywords: close closes closed fix fixes fixed resolve resolves resolved

- **Issue in the same repository**
  KEYWORD #ISSUE-NUMBER
  ```Closes #10```
- **Issue in a different repository**
  KEYWORD OWNER/REPOSITORY#ISSUE-NUMBER
  ```Fixes octo-org/octo-repo#100```
- **Multiple issues**
  ```Resolves #10, closes #123, fixes octo-org/octo-repo#100```

## Collaborative Development Methods

i.e. How pull-requests are used

### Fork and Pull Method

Good for open source and independent work without coordination

- Anyone can fork
- Pull requests propose changes from fork -> upstream
- Changes approved by project maintainer
- You can allow anyone with push access to the upstream repository to make changes to your pull request

### Shared repository model

Good for small teams and organizations collaborating on private projects

- Collaborators granted push access to a single shared repository
- Branches created for topics and changes that need to be made
- Allows for code reviews and discussion about pull requests before merged into main

## .gitignore

> File telling Git what not to track in commits

- GitHub maintains list (in github/gitignore) of recommended files to include in gitignore for
  - OS
  - environments
  - languages
- Auto generate file
  - <https://gitignore.io>
- Boilerplate
  - <https://gist.github.com/octocat/9257657>

## Authenticating with GitHub from Git

- Connecting over HTTPS (recommended)
  - cache GitHub credentials in Git using a credential helper
- Connecting over [SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
  - ssh keys

## Semantic Versioning

MAJOR.MINOR.PATCH

1) MAJOR = incompatible API changes
2) MINOR = functionality added in a backward compatible manner
3) PATCH = backward compatible bug fixes

<https://semver.org/>

## License

<https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository>

- Choose the right license
  <https://choosealicense.com>
  - Good **default choice** is the **MIT** license
- Explanation of licenses
  <https://opensource.guide/legal/#which-open-source-license-is-appropriate-for-my-project>
- Figure out what license a project has
  <https://github.com/licensee/licensee>

---

## First Project

<https://docs.github.com/en/get-started/quickstart/hello-world>

## Further Reading

- [Creating and Managing Repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories)
- [Managing a Remote Repository](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories)
- [Adding Local Code to GitHub](https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github)
- [Deleting and Restoring Branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/deleting-and-restoring-branches-in-a-pull-request)
