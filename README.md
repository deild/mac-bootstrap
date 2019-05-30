# Mac Bootstrap

![dotfiles screenshot][screenshot]

> Forked & Inspired by from [joshukraine's mac-bootstrap](https://github.com/joshukraine/mac-bootstrap/blob/master/bootstrap)

Le but de ce script est de provisionner une nouvelle machine exécutant une nouvelle installation de macOS.
Il installe et configure les logiciels, les `dotfiles` et les préférences générales que j'utilise.

Le script [bootstrap] est très spécifique à la plate-forme Mac.
La version 1.x a été testée avec succès sur les versions suivantes de macOS :

- Mojave (10.14)
- High Sierra (10.13)

Les versions plus anciennes peuvent fonctionner mais ne sont pas testées régulièrement. Les rapports de bogues pour les anciennes versions sont les bienvenus.

## Prérequis

1. Assurez-vous que votre logiciel est à jour :

```sh
sudo softwareupdate -i -a --restart
```

1. Installez les outils en ligne de commande d'Apple :

```sh
xcode-select --install
```

1. Redémarrez, vérifiez les mises à jour supplémentaires, puis réinstallez et redémarrez si nécessaire.

## Installation

Pour installer en une seule ligne, exécutez ceci :

```sh
curl -fsSO https://raw.githubusercontent.com/deild/mac-bootstrap/master/bootstrap \
&& sh bootstrap 2>&1 | tee ~/bootstrap.log
```

## Qu'est-ce que ça fait

Lorsque vous invoquez `bootstrap`, voici ce qu'il fait :

1. Installe et configure `Homebrew`
1. Vérifie la version de `Ruby` & `Gem`
1. Installe [mes Dotfiles](https://github.com/deild/dotfiles.git)
1. Configure `Vim` avec [mes préférences](https://github.com/deild/vimrc.git)
1. Renseigne le nom de la machine
1. Renseigne le timezone
1. Définit une variété de valeurs par défaut de macOS

[screenshot]: https://zupimages.net/up/19/22/k2by.png
[bootstrap]: https://github.com/deild/mac-bootstrap/blob/master/bootstrap
