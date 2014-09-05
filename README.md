squash
======

Repo for experimenting with squashing commits before merging a pull request

## How To Flatten a Pull Request

1. Make any desires changes on a feature branch. Push to GitHub whenever you feel like it. Make a pull request to master on GitHub at any point along the way.
1. Make sure your local `master` branch is up to date:
 - `git pull origin master`
1. While still on the feature branch, squash the commits: `git rebase -i master`
 - Keep the first commit as `pick`, all others should be `squash`.
 - Vim regex find/replace for this: `%s/pick/squash/g`. Make sure to reset the first one to `pick`.
1. Edit the commit message so it's referring to the one squashed commit, rather than the individual commits being squashed.
1. Force push the feature branch: `git push origin feature/4 --force`
1. Merge with master from command line:
 - `git checkout master`
 - `git merge feature/3 --no-ff --no-commit`
1. Push master: `git push origin master`
