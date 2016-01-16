# Kommit

While we were looking at this [lovely project][01], we have seen
some ehmmm downsides of it. Why not? let’s keep save the source code
and collect all the information somewhere else?

## Idea

* Commit often, Commit more!
* A mini shell tool for storing message `kommit "Fixes a bug in XXX function"`
* Store your commit information in to a hidden file `.git/kommit-message`
* Append the `.git/kommit-message` to the original commit message in 
`prepare-commit-msg` hook and delete `.git/kommit-message` file after commit.

## Install: Kommit

@wip

## Install: Git Hook

@wip

## Usage

@wip

### Environment Variables

Kommit checks `$KOMMIT_BULLET` and `$KOMMIT_WRAP_AT` variables. Default 
bullet style for message is `-` You can change this via;

```bash
KOMMIT_BULLET="*" kommit -m "Hello World"   # or, 

export KOMMIT_BULLET="*"                    # define it in your .bashrc
```

: Default value is **-**

: Default value is **70**


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