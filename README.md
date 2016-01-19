# Kommit

### Create more detailed commit messages without committing!

[![asciicast](https://asciinema.org/a/34075.png)](https://asciinema.org/a/34075)

While we were looking at this [lovely project][01], we have seen
some, ehmmm, downsides of it. Why not? let’s keep safe the **source code**
and collect all the information somewhere else?


## Idea

* Commit often, Commit more!
* A mini shell tool for storing messages: `kommit "Fixes a bug in XXX function"`
* Store your commit-extra information in to a hidden file `.git/kommit-message`
* Append the `.git/kommit-message` to the original commit message in 
`prepare-commit-msg` hook and delete `.git/kommit-message` file after commit.


## Usage

    usage: kommit [-m <msg> | -c | -s | -i | -r | -h]

        -m <msg>        append message
        -c              check if hook installed ?
        -s              show current message(s)
        -i              install kommit hook to .git/hooks/prepare-commit-msg
        -r              remove kommit hook, delete .git/hooks/prepare-commit-msg
        -h              print this message


## Sample Output

        # Your commit title
        
        - Your note...
        - Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
        eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut 
        enim ad minim veniam, quis nostrud exercitation ullamco laboris 
        nisi ut aliquip ex ea commodo consequat.


## Install: Kommit

You can download or get it via `curl`. Go to your desired `bin/` folder or
go somewhere which is in the `$PATH`:

```bash
cd ~/bin/          # example bin/ folder
curl -O https://raw.githubusercontent.com/bilgi-webteam/kommit/master/kommit
chmod +x kommit
```


## Install & Remove or Check: Git Hook

Super easy;

* `kommit -i` installs hook,
* `kommit -r` removes hook,
* `kommit -c` checks if the hook is installed to your repo!


### Environment Variables

Kommit checks `$KOMMIT_BULLET` and `$KOMMIT_WRAP_AT` variables. Default 
bullet style for message is `-` You can change this via;

```bash
KOMMIT_BULLET="*" kommit -m "Hello World"   # or, 

export KOMMIT_BULLET="*"                    # define it in your .bashrc
```

Also, default value for wrap text is: **72** you can change it via;

```bash
KOMMIT_WRAP_AT=60 kommit -m "Hello World"   # or, 

export KOMMIT_WRAP_AT=60                    # define it in your .bashrc
```


## Change Log

**2016-01-16**

* Release v0.1.0

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