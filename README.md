# Kommit

### Create more detailed commit messages without committing!

[![asciicast](https://asciinema.org/a/34075.png)](https://asciinema.org/a/34075)

While we were looking at this [lovely project][01], we have seen
some, ehmmm, downsides of it. Why not? let’s keep safe the **source code**
and collect all the information somewhere else?


## Idea

* Commit often, Commit more!
* A mini shell tool for storing messages: `kommit -m "Fixes a bug in XXX function"`
* Store your commit-extra information in to a hidden file `.git/kommit-message`
* Append the `.git/kommit-message` to the original commit message in
`prepare-commit-msg` hook and delete `.git/kommit-message` file after commit.


## Usage

    usage: kommit [-m <msg> | -t <msg> | -c | -e | -s | -i | -r | -h]

        -m <msg>        append message
        -t <msg>        append message with timestamp
        -c              check if hook installed ?
        -e              edit messages
        -s              show current message(s)
        -i              install kommit hook to .git/hooks/prepare-commit-msg
        -r              remove kommit hook, delete .git/hooks/prepare-commit-msg
        -h              print this message

Basic usage is shown below:

* `kommit -m "Message"` : Append new message.
* `kommit -t "Message"` : Append new message with timestamp.
* `kommit -s` : Show current messages
* `kommit -e` : Edit messages. This uses `$EDITOR` environment variable.


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
curl -O https://raw.githubusercontent.com/bilgi-webteam/kommit/master/bin/kommit
chmod +x kommit
```


## Git Hook: Install & Remove or Check

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

## IDE Integrations

* [TextMate1][textmate1-bundle]
* TextMate2
* Atom
* Sublime
* Vim
* Emcas


## Change Log

**2016-01-20**

* MIT license added.
* Contributers list added.
* IDE integration packages list added.

**2016-01-19**

* New feature; edit messages! `kommit -e`
* New feature; check hook `kommit -c`

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


## Contributers

* [Uğur "vigo" Özyılmazel][02] - Creator, maintainer
* [Ekin Ertaç][03] - Contributer, maintainer

Other contributers can be found [here][04].

## License

This project licensed under MIT.


[01]: https://github.com/thebearjew/commit-comments
[02]: https://github.com/vigo
[03]: https://github.com/ekinertac
[04]: https://github.com/bilgi-webteam/kommit/graphs/contributors

[textmate1-bundle]: https://github.com/vigo/textmate1-kommit
