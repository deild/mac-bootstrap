# Mac Bootstrap [![Build Status](https://travis-ci.org/deild/mac-bootstrap.svg?branch=master)](https://travis-ci.org/deild/mac-bootstrap)

> Your laptop is your sword. Don't go into battle without it.

![dotfiles screenshot][screenshot]

> Forked & Inspired by from [joshukraine's mac-bootstrap]

The purpose of this script is to provision a new machine running a fresh install of macOS.

It can be run multiple times on the same machine safely. It installs, upgrades, or skips packages based on what is already installed on the machine.

The [bootstrap] script is very specific to the Mac platform.
Version 1.x has been successfully tested on the following versions of macOS:

- Catalina (10.15)
- Mojave (10.14)
- High Sierra (10.13)

Older versions may work but are not tested regularly.
Bug reports into a new [GitHub Issue] for older versions are welcome.

## Install

Download the script:

```sh
curl -fsSO https://raw.githubusercontent.com/deild/mac-bootstrap/master/bootstrap
```

Review the script (avoid running scripts you haven't read!):

```sh
less bootstrap
```

Execute the downloaded script:

```sh
sh bootstrap 2>&1 | tee ~/bootstrap.log
```

Optionally, review the log:

```sh
less ~/bootstrap.log
```

Or to install with a one-liner, run this:

```sh
curl -fsSO https://raw.githubusercontent.com/deild/mac-bootstrap/master/bootstrap \
&& sh bootstrap 2>&1 | tee ~/bootstrap.log
```

## Debugging

Your last bootstrap run will be saved to ~/bootstrap.log.
Read through it to see if you can debug the issue yourself.
If not, copy the lines where the script failed into a new [GitHub Issue] for us.
Or, attach the whole log file as an attachment.

## What it sets up

When you invoke `bootstrap`, here's what it does:

- Ensuring Apple's command line tools are installed
- Checking `Homebrew` and installs a variety of packages
- Checking which `Ruby` and `Gem` installs we are using
- Installing [dotfiles](https://github.com/deild/dotfiles.git)
- Configure & install `Vim` Plugin with [vimrc](https://github.com/deild/vimrc.git)
- Set computer name
- Set the timezone
- Setting macOS [preferences](https://github.com/deild/mac-bootstrap/blob/master/macos-defaults)

## LICENSE

[![MIT](https://img.shields.io/badge/license-MIT-BLUE)](LICENSE)

[joshukraine's mac-bootstrap]: https://github.com/joshukraine/mac-bootstrap/blob/master/bootstrap
[screenshot]: https://zupimages.net/up/19/22/k2by.png
[bootstrap]: https://github.com/deild/mac-bootstrap/blob/master/bootstrap
[GitHub Issue]: https://github.com/deild/mac-bootstrap/issues/new
