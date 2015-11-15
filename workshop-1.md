# Workshop 1

## Play around with the basic git commands:

- `git init`
- `git status`
- `git add file.txt`
- `git add .` add everything
- `git commit -m "Do stuff"`
- `git log`
- `git log --oneline`

## Fixing warnings

The first time you commit, git will ask you to set your email address, do this with:

    git config --global user.email example@mail.com

This will now be set for all repositories you commit to using this computer.

## Setting up your editor

Add some change and run `git commit` without the message.
This will open a text editor, probably Vim, which is extremely unfriendly.
**Find out how to set this up with your preferred editor.**

Tip: You can quit Vim and discard the commit like this:
- Press escape
- Type `:q!`
- Press enter

## Writing pretty commit messages

Use your own editor to write a longer commit message,
follow [these instructions](http://chris.beams.io/posts/git-commit/) about how to format the text.
