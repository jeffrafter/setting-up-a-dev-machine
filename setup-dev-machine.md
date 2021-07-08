# Setting up my  development machine
#setup

You can run this: [Setup a new Macbook · GitHub](https://gist.github.com/jeffrafter/71d994acb35529744e62772704e8fa4e)

Copy the contents to `~/.macos` and `chmod +x`. Then you should be able to execute it.

## Touch Bar
Open System Preferences and go to the Keyboard settings.

Change to Extended Control Strip:

![](https://rpl.cat/uploads/OkTVCBr6S8jzGd_jwjJOF3lSFOvLiaqgpGGzBxpEJ3A/public.png)

Then edit the control strip to have fewer buttons (or spaces) using Customize Control Strip:

![](https://rpl.cat/uploads/4m5n263YIHqjtkDw8bu5cBHukenHdxZbTOItIq1K9b4/public.png)

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
* Install home-brew `/bin/bash -c “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)”`

## Set the path for zsh

If you are on an Apple M1 mac you might need to set the path to homebrew in zsh before continuing

### Setting up the shell (to fish)

* Install fish `brew install fish`
* Install Oh My Fish `curl -L https://get.oh-my.fish | fish`
* Install Spacefish `omf install spacefish`
* Add it to the shells `echo /usr/local/bin/fish | sudo tee -a /etc/shells` (if on Apple M1 mac: `echo /opt/homebrew/bin/fish | sudo tee -a /etc/shells`)
* Quit terminal and re-open
* Change your default shell to fish: `chsh -s /usr/local/bin/fish` (if on Apple M1 mac: `chsh -s /opt/homebrew/bin/fish`)
* Quit terminal and re-open, fish should be your default shell
* For latest homebrew, set the fish paths: `set -U fish_user_paths /opt/homebrew/bin $fish_user_paths`

### SSH

https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh

`ssh-keygen -t ed25519 -C "jeffrafter@github.com"`

Using `ssh-agent` in fish requires a couple of steps:

Copy the contents of [Auto-launching ssh-agent in fish shell · GitHub](https://gist.github.com/gerbsen/5fd8aa0fde87ac7a2cae) to  `~/.config/fish/config.fish` (create it if not present)

If the file doesn't already exist you can just run:

`curl https://gist.githubusercontent.com/gerbsen/5fd8aa0fde87ac7a2cae/raw/8c58a3711bc727f9a2d6de87e24cd5768e6a21d1/ssh_agent_start.fish -o ~/.config/fish/config.fish`


### Node and NVM

* Install NVM: `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash`
* Open  and new terminal window
* `nvm install 12.16.1`
* `omf install nvm`
* `brew install nodenv`

### Ruby and rbenv

* `brew install rbenv`
* `rbenv init`

You should see:

```
# Load rbenv automatically by appending
# the following to ~/.config/fish/config.fish:

status --is-interactive; and source (rbenv init -|psub)
```

Add it!

Also add `nodenv`:

```
# Load nodenv automatically by appending
# the following to ~/.config/fish/config.fish:

status --is-interactive; and source (nodenv init -|psub)
```

* `rbenv install 2.6.6`
* `rbenv global 2.6.6`

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

* Install rbenv: `rbenv install 2.6.6`
* Install bundler:  `gem install bundler`


### Github Terminal Login

`git config --global user.name jeffrafter`
`git config --global user.email jeffrafter@gmail.com`

Go to a private repo and `git pull` - you'll be asked for your username and password. If you can 2fa enabled you will need to generate a [personal access token](https://github.com/settings/tokens). When you do this, click the copy icon for the generated token before enabling SSO.

`ssh -T git@github.com`

> Hi jeffrafter! You've successfully authenticated, but GitHub does not provide shell access.

