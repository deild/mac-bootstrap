# Mac Bootstrap [![Build Status](https://travis-ci.org/deild/mac-bootstrap.svg?branch=master)](https://travis-ci.org/deild/mac-bootstrap) [![MIT](https://img.shields.io/badge/license-MIT-BLUE)](LICENSE)

> Your laptop is your sword. Don't go into battle without it.

![dotfiles screenshot][screenshot]

> Forked & Inspired by from [joshukraine's mac-bootstrap]

Bootstrap is a script to provision a new machine running a fresh install of macOS ([Catalina 10.15]).

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
curl -fsSO https://bit.ly/deild_bootstrap
```

Review the script (avoid running scripts you haven't read!):

```sh
less deild_bootstrap
```

Execute the downloaded script:

```sh
sh deild_bootstrap 2>&1 | tee ~/.bootstrap.log
```

Optionally, review the log:

```sh
less ~/.bootstrap.log
```

Or to install with a one-liner, run this:

```sh
curl -fsSO https://bit.ly/deild_bootstrap && sh deild_bootstrap 2>&1 | tee ~/.bootstrap.log
```

## Debugging

Your last bootstrap run will be saved to ~/.bootstrap.log.
Read through it to see if you can debug the issue yourself.
If not, copy the lines where the script failed into a new [GitHub Issue] for us.
Or, attach the whole log file as an attachment.

## What it sets up

When you invoke `bootstrap`, here's what it does:

- Set the timezone to Europe/Paris
- Set computer name to Higuma
- Ensure Apple's command line tools are installed, and install it if not
- Disable or enable Gatekeeper control
- Install or update [Homebrew]
- Ensure last bash version is installed, and update it if not
- Install or upgrade formula dependencies
- Install or upgrade cask
- Install or upgrade and then reload [dotfiles]
- Check which Ruby and Gem installs we are using at this point
- Generate ed25519 and RSA key
- Set macOS [preferences]

[preferences]: https://github.com/deild/mac-bootstrap/blob/master/macos-defaults
[joshukraine's mac-bootstrap]: https://github.com/joshukraine/mac-bootstrap/blob/master/bootstrap
[screenshot]: https://zupimages.net/up/20/20/i92s.png
[bootstrap]: https://github.com/deild/mac-bootstrap/blob/master/bootstrap
[GitHub Issue]: https://github.com/deild/mac-bootstrap/issues/new
[Catalina 10.15]: https://www.apple.com/macos/catalina/
[Homebrew]: https://brew.sh/
[dotfiles]: https://bitbucket.org/deild/home/wiki/Home
