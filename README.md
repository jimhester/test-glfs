# Example of Git LFS on GitHub, with a GitLab LFS backend

## Setup git lfs globally

Follow the directions at https://git-lfs.github.com/, should simply be running
`git lfs install` after installing the command line extension.

## New repository setup

1. Add regular files, git lfs tracked files as usual.
1. Add an `.lsconfig` entry for the gitlab lfs url. Replace `user` and `repo` with your values respectively.
   `git config -f .lfsconfig lfs.url https://gitlab.com/user/repo/info/lfs`
1. Create a new [GitLab project](https://gitlab.com/projects/new)
1. Add the GitLab project as a gitlab remote
   `git remote add gitlab git@gitlab.com:user/repo.git`
1. Push to the gitlab remote first, to setup git lfs there.
   `git push gitlab master`
1. Create a new [GitHub project](https://github.com/new).
1. add it as `origin` remote.
   `git remote add origin git@gitlab.com:user/repo.git`
1. STOP, before pushing to GitHub you need to do one of two things. If your
   GitLab account is authenticated by a simple password you should be prepared
   to enter that. Otherwise you need to create a [personal access
   token](https://gitlab.com/profile/personal_access_tokens) with api
   (read/write) access to use as a password for the upcoming step.
1. Push to the GitHub remote, this will then prompt you for a username and password. This is your **GitLab** username and password / PAT generated in the last step.
   `git push gitlab master`
   Username: user
   Password: xyz1234
1. Interact with GitHub normally from here on out! You can optionally set the
   GitLab to mirror the GitHub project from this point at
   https://gitlab.com/jimhester/test-glfs/settings/repository.

## Existing GitHub repository setup
1. Track the files with git lfs tracked files you want to use.
1. Add an `.lsconfig` entry for the gitlab lfs url. Replace `user` and `repo` with your values respectively.
   `git config -f .lfsconfig lfs.url https://gitlab.com/user/repo/info/lfs`
1. [Import your GitHub project to GitLab](https://gitlab.com/projects/new#import-project-pane), (do not set up mirroring initially).
1. Add the GitLab project as a gitlab remote
   `git remote add gitlab git@gitlab.com:user/repo.git`
1. Push to the gitlab remote, to setup git lfs there.
   `git push gitlab master`
1. STOP, before pushing to GitHub you need to do one of two things. If your
   GitLab account is authenticated by a simple password you should be prepared
   to enter that. Otherwise you need to create a [personal access
   token](https://gitlab.com/profile/personal_access_tokens) with api
   (read/write) access to use as a password for the upcoming step.
1. Push to the GitHub remote, this will then prompt you for a username and password. This is your **GitLab** username and password / PAT generated in the last step.
   `git push gitlab master`
   Username: user
   Password: xyz1234
1. Interact with GitHub normally from here on out! You can optionally set the
   GitLab to mirror the GitHub project from this point at
   https://gitlab.com/jimhester/test-glfs/settings/repository.
