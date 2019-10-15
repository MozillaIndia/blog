# Contribute

You can help by finding out problems on the website (QA), sending suggestions, and/or coding.

## Reporting problems or suggestions

Go through [the issues](https://github.com/MozillaIndia/blog/issues) and create a new issue if yours is not already added.

## Adding code

### Setting up developer tools

The blog is built using [Jekyll](https://jekyllrb.com/). To set up a local workspace, here is what you should do.

1. Fork and clone the repo as described in git workflow below.
2. For OS specific instructions on how to install Jekyll, refer the official Jekyll [Docs](https://jekyllrb.com/docs/installation/).
3. Run the blog on a localhost server using the following command at the root of the repo

```
bundle exec jekyll serve
```

(To know more about how Jekyll works, refer the official Jekyll [Step by Step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/).)

4. By default the server runs at `localhost:4000`. For any changes to [_config.yml](_config.yml), the server must be restarted.


### Git workflow

- Fork this repo using the button at the top.
- Clone your forked repo locally.

```
$ git clone https://github.com/yourname/blog.git
```

- Don't modify or work on the master branch, we'll use it to always be in sync with the upstream.

```
$ git remote add upstream https://github.com/MozillaIndia/blog.git
$ git fetch upstream
```

- If you're working on something that doesn't have an issue related to it, create an issue.
- Comment on the related issue that you're working on it.
- Once you're clear to go, go to your local copy and create a new branch to work on it. Use a descriptive name for it, include the issue number for reference.

`$ git checkout -b add-contribution-guidelines-68`

- Do your coding and push it to your fork.
  - Use spacing and code style that is consistent with the rest of the file.
  - Include as few commits as possible (one should be enough) and a good description. ([Read this about writing good commit messages](http://365git.tumblr.com/post/3308646748/writing-git-commit-messages)). Include a reference to the issue with "Fix #number".

```
$ git commit -m "Add contribution guidelines. Fix #68"
$ git push origin add-contribution-guidelines-68
```

- Do a new pull request from your "add-contribution-guidelines-68" branch to MozillaIndia/mozillaindia.github.io "master".

#### How to implement changes suggested on a pull request

Sometimes when you submit a PR, you will be asked to correct some code. You can make the changes on your work branch and commit normally and the PR will be automatically updated.

`$ git commit -am "Ops, fixing typo"`

Once everything is OK, you will be asked to merge all commit messages into one to keep history clean.

`$ git rebase -i master`

Edit the file and mark as fixup (f) all commits you want to merge with the first one:

```
pick 0343e07 Add contribution guidelines. Fix #68
f b435a67 Ops, fixing typo
```

Once rebased you can force a push to your fork branch and the PR will be automatically updated.

`$ git push origin add-contribution-guidelines-68 --force`

#### How to keep your local branches updated

To keep your local master branch updated with upstream, regularly do:

```
$ git fetch upstream
$ git checkout master
$ git pull --rebase upstream master
```

To update the branch you are coding in:

```
$ git checkout add-contribution-guidelines-68
$ git rebase master
```

## Adding Posts

To add a new post to the blog, here's what you should do.

1. Fill your author details in [_config.yml](_config.yml) if not already done so.
2. Add a new file in [_posts](_posts) directory in the format `yyyy-mm-dd-name-of-post.md`.
3. Fill in the [front matter](https://jekyllrb.com/docs/front-matter/) at the top of the file, similar to other posts.
4. Test your changes using `bundle exec jekyll serve`.
5. When everything works well, add a commit and send a PR as described in the Git workflow above.

#### Attribution

This file is derived from work by @zhukov [here](https://github.com/zhukov/webogram/blob/master/CONTRIBUTING.md).
