# GitHub

> Platform for code hosting, version control, and collaboration

## [Work flow](https://docs.github.com/en/get-started/quickstart/github-flow)

![Example](https://docs.github.com/assets/cb-23923/mw-1440/images/help/repository/branching.webp 'Example of a branch "branching" off of main')

## [Repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories)

> Organizes a project and its state

Purpose is to store:

- folders and files for project
- README.md file for project's
  - Name
  - Description
  - How to get started contributing
  - Links to other relevant documentation, such as architecture overview
- LICENSE file

### Private Repository

- Uses [GitHub Actions](https://docs.github.com/en/actions)
- GitHub Actions done by GitHub-hosted runners are [free](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions) for public repositories, not private
- Each account includes storage and minutes for use with GitHub-hosted runners

### Create Local Repository

*Warning:* Support for password authentication with HTTPS was removed on August 13, 2021.

1) [Generate ssh key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#adding-your-ssh-key-to-the-ssh-agent) (if none exists)
  `ssh-keygen -t ed25519 -C "your_email@example.com"`
  or for rsa / legacy system
  `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
   1) Add [passphrase](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases) (recommended)
2) Start the ssh-agent
   1) `eval "$(ssh-agent -s)"`
      [May need to use different command](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=linux#adding-your-ssh-key-to-the-ssh-agent)
3) Add ssh key to ssh-agent
  `ssh-add ~/.ssh/id_ed25519`
  or whatever the name of your ssh key is
4) Copy ssh key
  Linux: `clip < ~/.ssh/id_ed25519.pub`
  WSL: `cat ~/.ssh/id_ed25519.pub | clip.exe`
5) [Add ssh key to SSH and GPG keys under "Access" in profile settings](https://github.com/settings/profile)
   1) Paste in ssh key
   2) Add SSH key

### Simple clone with no link

`git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY`

#### Authenticating with GitHub from Git

- Connecting over HTTPS
  - cache GitHub credentials in Git using a credential helper
- Connecting over [SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
  - ssh keys

## [Branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)

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

i.e. [Merge](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request) a branch into a branch

Creation:

- Title of pull request (Release v1.0)
- Description of the changes made
- Reference to an issue the pull request addresses
- @mentions of the person or team responsible for reviewing proposed changes

Shows:

- Conversation
- Commits that differ from base branch
- Checks
- File differences of both branches
  - ONLY THE DIFFS AT THE CREATION OF THE PULL REQUEST

Tips:

- Can create pull request templates

## Forks

> personal copy of another's repository

- Sync fork -> upstream
  - make a pull request on upstream
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

## Releases

- Tag should be semantic versioned.
- Title should state what version is being released
- Notes should state what was changed.
  - Just click `Generate Release Notes`

### Semantic Versioning

MAJOR.MINOR.PATCH

1) MAJOR = incompatible API changes
2) MINOR = functionality added in a backward compatible manner
3) PATCH = backward compatible bug fixes

<https://semver.org/>

| Code status                     | Stage         | Rule                                                                   | Example version |
| ------------------------------- | ------------- | ---------------------------------------------------------------------- | --------------- |
| First release                   | New product   | Start with 1.0.0                                                       | 1.0.0           |
| Backward compatible fix         | Patch release | Increment the third digit                                              | 1.0.1           |
| Backward compatible new feature | Minor release | Increment the middle digit and reset the last digit to zero            | 1.1.0           |
| Breaking updates                | Major release | Increment the first digit and reset the middle and last digits to zero | 2.0.0           |

## License

<https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository>

- Choose the right license
  <https://choosealicense.com>
  - Good **default choice** is the **MIT** license
- Explanation of licenses
  <https://opensource.guide/legal/#which-open-source-license-is-appropriate-for-my-project>
- Figure out what license a project has
  <https://github.com/licensee/licensee>

### Add license to repository

1) Create a new file
2) Change name to "LICENSE"
3) Click `Choose a license template`
4) Click the `Review and submit` green button (on right)
5) Click `Commit changes...`
6) Click `Commit changes`

## Markdown Tips

- Link to issues and pull requests within a repository with hashtag before their number
  - ```#123```
  - This will create a two-way reference
- Automatically generates table of contents

---

## First Project

<https://docs.github.com/en/get-started/quickstart/hello-world>

## Profile Setup

### Create a profile README

1. Create a repository named the same as your username, public, with a README.md file.
2. Put whatever you want, some suggestions
   - "About me" section describing work and interests
   - Contributions you're proud of with context
   - Guidance for getting help in communities where you're involved
3. May need to go to repository and click the green button for "Share to profile"

## Further Reading

- [Creating and Managing Repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories)
- [Managing a Remote Repository](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories)
- [Adding Local Code to GitHub](https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github)
- [Deleting and Restoring Branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/deleting-and-restoring-branches-in-a-pull-request)
- [Create your own GitHub Skills Actions-Powered Courses ](https://skills.github.com/quickstart)
- [Code with GitHub Copilot Project](https://github.com/skills/copilot-codespaces-vscode)
