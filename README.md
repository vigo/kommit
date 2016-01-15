# Kommit

While we were looking at this [lovely project][01], we have seen
some ehmmm downsides of it. Why not? let’s keep save the source code
and collect all the information somewhere else?

## Idea

* Commit often, Commit more!
* A mini shell tool for storing message `kommit "Fixes a bug in XXX function"`
* Store your commit information in to a hidden file `.commit-message` (?)
* Append the `.commit-message` to the original commit message in 
`prepare-commit-msg` hook.
* Delete `.commit-message` file after successfull commit on `post-commit` hook.

## Install

@wip

## Change Log

**2016-01-15**

* Initial commit!

## Contribute

Feel free to send your PR’s!

1. `fork` (https://github.com/bilgi-webteam/kommit/fork)
2. Create your `branch` (`git checkout -b my-features`)
3. `commit` yours (`git commit -am 'added killer options'`)
4. `push` your `branch` (`git push origin my-features`)
5. Than create a new **Pull Request**!

[01]: https://github.com/thebearjew/commit-comments