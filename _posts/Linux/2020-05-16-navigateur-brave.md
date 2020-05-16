---
author: Funeoz
layout: post
permalink: /linux/brave-meilleure-alternative-chrome-linux.mtml
title: Brave, la meilleure alternative à Chrome sous Linux
category: linux
image: /assets/2020-05-16/image1brave.webp
---

Brave est un navigateur créé par Brendan Eich, aussi fondateur du navigateur Firefox et créateur du langage Javascript.
Il est basé sur Chromium qui sert aussi de base pour le navigateur Google Chrome.

## Pourquoi l'utiliser ?

- Il est open-source sous license MPL
- Il bloque les publicités par défaut, ce qui rend le navigateur beaucoup plus rapide
- Les fichiers torrent peuvent être lus à partir du navigateur en même temps que leur téléchargement
- Le mode de navigation privée fait passer automatiquement le trafic sous Tor
- Il intègre la BAT (Basic Attention Token) qui permet de rémunérer les utilisateurs lorqu'ils autorisent l'affichage de publicités.

## Installation sous Linux

### Pour Ubuntu, Mint et les distros Debian

Ouvrez votre terminal et mettez ces commandes:

{% highlight bash %}
# ajoutez les dépendances nécessaires à l'installation
$ sudo apt install apt-transport-https curl

# ajoutez le repository de Brave à votre liste
$ curl -s https://brave-browser-apt-release.s3.brave.com/brave-core.asc | sudo apt-key --keyring /etc/apt/trusted.gpg.d/brave-browser-releasegpg add -
$ echo "deb [arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main" | sudo tee /etc/apt/sources.list.d/brave-browser-releaselist
# Installez Brave
$ sudo apt update
$ sudo apt install brave-browser
{% endhighlight %}

### Pour Fedora

{% highlight bash %}
# ajoutez les dépendances nécessaires à l'installation
$ sudo dnf install dnf-plugins-core
# ajoutez le repository de Brave à votre liste
$ sudo dnf config-manager --add-repo https://brave-browser-rpm-release.s3.brave.com/x86_64/
$ sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc
# Installez Brave
$ sudo dnf install brave-browser
{% endhighlight%}

### Pour OpenSUSE

{% highlight bash %}
# ajoutez les dépendances nécessaires à l'installation
$ sudo zypper install curl
# ajoutez le repository de Brave à votre liste
$ sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc
$ sudo zypper addrepo https://brave-browser-rpm-release.s3.brave.com/x86_64/ brave-browser
# Installez Brave
$ sudo zypper install brave-browser
{% endhighlight%}