# dotfiles (jstrauss)

## Installation

**Warning:** These are my preferred settings. Use at your own risk!

### Using git and the bootstrap script

You can clone the repository; the bootstrapper script will pull in the latest version and copy the files to your home folder.

```bash
git clone https://github.com/jstrauss/dotfiles.git && cd dotfiles && source bootstrap.sh
```

To update, `cd` into your local `dotfiles` repository and then:

```bash
source bootstrap.sh [--force]
```

### Git-free install

To install these dotfiles without git:

```bash
cd; curl -#L https://github.com/jstrauss/dotfiles/tarball/master | tar -xzv --strip-components 1 --exclude={README.md,bootstrap.sh,.osx,LICENSE-MIT.txt}
```

To update later on, just run that command again.

### Add custom commands without creating a new fork of this repo

If you create a file `~/.extra`, it will be sourced along with the other
dotfiles when bash loads up. You can use this to add custom commands
without forking this repository and without the need to worry about
committing any private commands to a public repository.

My `~/.extra` file looks something like this:

```bash
# Git credentials
# Not in repo to avoid others from accidentally committing under my name
GIT_AUTHOR_NAME="Jeff Strauss"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="jeff@aranasoft.com"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

### Sensible macOS defaults

When setting up a new Mac, you may want to use a script to set a variety
of sensible macOS default functionality. This repo contains a `.macos`,
which may be sourced:

```bash
source ~/.macos
```

If you choose to use this file, make sure that you locate the the
`General UI/UX` section and update the four commented lines that set the
ComputerName, HostName, LocalHostName, and NetBIOSName to provide your
own desired system name:

```bash
# Set computer name (as done via System Preferences → Sharing)
# sudo scutil --set ComputerName "<preferred_name>"
# sudo scutil --set HostName "<preferred_name>"
# sudo scutil --set LocalHostName "<preferred_name>"
# sudo defaults write /Library/Preferences/SystemConfiguration/com.apple.smb.server NetBIOSName -string "<preferred_name>"
```

## Feedback

Suggestions/improvements are
[welcome and encouraged](https://github.com/jstrauss/dotfiles/issues)!

## Authors

| [![twitter/jeffreystrauss](http://gravatar.com/avatar/b06d474fb0c5bb9d62fee08782c75d14?s=70)](http://twitter.com/jeffreystrauss "Follow @jeffreystrauss on Twitter") | [![twitter/jayharris](http://gravatar.com/avatar/1318668b99b2d5a3900f3f7758763a69?s=70)](http://twitter.com/jayharris "Follow @jayharris on Twitter") |
|---|---|
| [Jeff Strauss](http://twitter.com/jeffreystrauss/) | [Jay Harris](http://twitter.com/jayharris/)

## Thanks to…

* [dotfiles](http://mths.be/dotfiles) repository by [Mathias Bynens](http://mathiasbynens.be/)
