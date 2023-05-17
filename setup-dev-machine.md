# Setting up my  development machine
#setup

You can run this: [Setup a new Macbook · GitHub](https://gist.github.com/jeffrafter/71d994acb35529744e62772704e8fa4e)

Copy the contents to `~/.macos` and `chmod +x`. Then you should be able to execute it.

## Install some software 
* Xcode (App Store, and command line developer tools)
* VSCode (https://code.visualstudio.com/download)
* Slack (https://slack.com/downloads/mac)
* ~Bear~
* Unity Hub (and the latest final version of Unity, https://unity3d.com/get-unity/download)
* Rpl.cat (http://rpl.cat/download/, set shortcuts,  login)
* Zoom (https://zoom.us/download, turn off video and audio when joining, touch up appearance, HD)
* GitHub Desktop (https://desktop.github.com/)
* 1Password 7 (https://1password.com/downloads/mac/)
* Cura (https://ultimaker.com/software/ultimaker-cura)
* Sequel Pro (https://sequelpro.com/download)
* PSequel (http://www.psequel.com/)
* Insomnia (Insomnia Core, https://insomnia.rest/download/)
* Highland 2 (app store)
* Kindle (https://www.amazon.com/kindle-dbs/fd/kcp/ref=klp_mn)
* Kap (https://getkap.co/)
* KeepingYouAwake (https://github.com/newmarcel/KeepingYouAwake/releases)
* Steam

## Setup some accounts
* Login to Apple (messages)
* Login to GitHub
* Setup Mail

## Terminal

Install [Homebrew](https://brew.sh):

* Install home-brew `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Set the path for zsh

If you are on an Apple M1 mac you might need to set the path to homebrew in zsh before continuing

```
echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/njero/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/njero/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### Setting up the shell (to fish)

* Install fish `brew install fish`
* Install Oh My Fish `curl -L https://get.oh-my.fish | fish`
* Install starship: `brew install starship`
* Add starship to fish: `echo "starship init fish | source" >> ~/.config/fish/config.fish`
* Add fish to your shells `echo /usr/local/bin/fish | sudo tee -a /etc/shells` (if on Apple M1 mac: `echo /opt/homebrew/bin/fish | sudo tee -a /etc/shells`)
* Quit terminal and re-open
* Change your default shell to fish: `chsh -s /usr/local/bin/fish` (if on Apple M1 mac: `chsh -s /opt/homebrew/bin/fish`)
* Quit terminal and re-open, fish should be your default shell
* For latest homebrew, set the fish paths: `set -U fish_user_paths /opt/homebrew/bin $fish_user_paths`

### SSH

https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh

`ssh-keygen -t ed25519 -C "jeffrafter@gmail.com"`

Using `ssh-agent` in fish requires a couple of steps:

Copy the contents of [Auto-launching ssh-agent in fish shell · GitHub](https://gist.github.com/gerbsen/5fd8aa0fde87ac7a2cae) to  `~/.config/fish/config.fish` (create it if not present)

If the file doesn't already exist you can just run:

`curl 
https://gist.githubusercontent.com/gerbsen/5fd8aa0fde87ac7a2cae/raw/8c58a3711bc727f9a2d6de87e24cd5768e6a21d1/ssh_agent_start.fish -o ~/.config/fish/config.fish`

### Ruby and rbenv

* `brew install rbenv`
* `rbenv init`

You should see:

```
# Load rbenv automatically by appending
# the following to ~/.config/fish/config.fish:

status --is-interactive; and source (rbenv init -|psub)
```

You can also just include the `source` part of the line in the interactive block if you have it already.

Restart the terminal.

* List ruby versions: `rbenv install -l`
* Install ruby: `rbenv install 2.6.8`
* Make it global: `rbenv global 2.6.8`
* Install bundler:  `gem install bundler`

# Gems

Make `~/.gemrc`:

```
--- 
:update_sources: true
:verbose: true
:bulk_threshold: 1000
:backtrace: false
:benchmark: false
gem: --no-ri --no-rdoc
```

### Nodenv 

* `brew install nodenv`
* `nodenv init`

You should see:

```
# Load nodenv automatically by appending
# the following to ~/.config/fish/config.fish:

status --is-interactive; and source (nodenv init -|psub)
```

You can also just include the `source` part of the line in the interactive block if you have it already.

Restart the terminal.

* List node versions: `nodenv install -l`
* Install node: `nodenv install 15.14.0` (note: 14.x versions may not compile on M1 Macs)
* Make it global: `nodenv global 15.14.0`

## Python 3.x and conda

* `brew install --cask miniforge`
* `conda init fish`
* Close and re-open terminal
* `conda activate`
* `conda install numpy scipy scikit-learn` (installing into the `base` env)

To install a version of Python, create a new environment:

* List available versions: `conda list python`
* `conda create -n name_of_env python=version`
* `conda activate name_of_env`
* `python -m pip install ipython`

### Github Terminal Login

`git config --global user.name jeffrafter`
`git config --global user.email jeffrafter@gmail.com`
`git config --global pull.rebase false`

Install `gh` to work with github CLI:

```
brew install gh
```

Then login:

```
❯ gh auth login                                                                            (base) 
? What account do you want to log into? GitHub.com
? What is your preferred protocol for Git operations? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser
```

Go to a private repo and `git pull` - you'll be asked for your username and password. 

#### Old : don't use personal access tokens

If you can 2fa enabled you will need to generate a [personal access token](https://github.com/settings/tokens). When you do this, click the copy icon for the generated token before enabling SSO.

`ssh -T git@github.com`

> Hi jeffrafter! You've successfully authenticated, but GitHub does not provide shell access.

# Git aliases

Put this at the end of your `~/.gitconfig`

```
[alias]
  wtf = for-each-ref --sort=-committerdate refs/heads --format='%(authordate:short) %(color:red)%(objectname:short) %(color:yellow)%(refname:short)%(color:reset) (%(color:green)%(committerdate:relative)%(color:reset))' --count=10
  remote-wtf = for-each-ref --sort=-committerdate refs/heads refs/remotes --format='%(authordate:short) %(color:red)%(objectname:short) %(color:yellow)%(refname:short)%(color:reset) (%(color:green)%(committerdate:relative)%(color:reset)) %(authorname)' --count=20
	open = "!f() { \
    open \"$(git ls-remote --get-url $(git config --get branch.$(git rev-parse --abbrev-ref HEAD).remote) \
    | sed 's|git@github.com:\\(.*\\)$|https://github.com/\\1|' \
    | sed 's|\\.git$||'; \
    )/compare/$(\
    git config --get branch.$(git rev-parse --abbrev-ref HEAD).merge | cut -d '/' -f 3- \
    )?expand=1\"; \
  }; f"
```


# UTM
https://docs.getutm.app/guides/windows/

Install homebrew (above)

```
brew install aria2 cabextract cdrtools wimlib
brew tap minacle/chntpw
brew install minacle/chntpw/chntpw
```