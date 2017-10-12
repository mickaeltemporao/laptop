# Mickael’s laptop install script

laptop is a script to set up a macOS laptop for ...

## Install

Download and install the script:

```sh
curl --remote-name https://raw.githubusercontent.com/mickaeltemporao/dotfiles/master/laptop | sh 2>&1 | tee ~/laptop.log
```

## Customize in `~/.laptop.local`

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
# Git credentials
# Not in the repository, to prevent people from accidentally committing under my name
GIT_AUTHOR_NAME="Mickael Temporão"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="mickael@temporao.com"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
git config --global user.email "$GIT_AUTHOR_EMAIL"
git config --global credential.helper osxkeychain
cd | curl --remote-name https://raw.githubusercontent.com/mickaeltemporao/dotfiles/master/.gitignore
git config --global core.excludesfile ~/.gitignore
```

## Thanks to
* [Thoughtbot](https://github.com/thoughtbot) and their [laptop repository](https://github.com/thoughtbot/laptop)
* [Mathias Bynens](https://github.com/mathiasbynens) and his amazing [dotfiles repository](https://github.com/mathiasbynens/dotfiles)
