---
author: Funeoz
layout: post
permalink: /hacking/installer-outils-kali-linux-ubuntu.html
title: Installer les outils de Kali Linux sous Ubuntu
category: hacking
image: /assets/2020-05-13/image1kalibuntu.webp
---

Ubuntu est une distribution Linux très populaire. Mais avoir en plus les outils de Kali seraient un vrai plus. C'est pour cela que certaines personnes ont créé des outils pour les installer très facilement: Katoolin3 et Kalibuntu. 
Katoolin3 permet d'installer les paquets de Kali en configurant directement ses repositories dans Ubuntu (au dépend de l'intégrité du système) tandis que Kalibuntu permet d'installer les outils de Kali sans passer par les repositories de Kali.

A vous de choisir !

## Installation de Katoolin3

Avertissement du développeur:

> Warning for Ubuntu users
> 
> Installing programs from repositories for different operating systems is generally considered dangerous!
> Some packages might (and probably will) break your system. Be careful when installing the tools and don't blame katoolin3 for any 
> inconveniences.
> The optimal solution is to install specific tools from tools.kali.org.
> It is not recommended to install all tools.

Clonez tout d'abord le repository du projet:

{% highlight bash %}
$ git clone https://github.com/s-h-3-l-l/katoolin3
# entrez dans le répertoire
$ cd katoolin3
# donner les droits d'exécution au fichier d'installation
$ chmod +x ./install.sh
# exécuter ce fichier
$ sudo ./install.sh
{% endhighlight %}

Vous pourrez ensuite installer/chercher les outils grâce à un menu.

Pour supprimer un paquet, insérez ce symbole `~` devant le nom du paquet.

## Installation de Kalibuntu

Kalibuntu est un outil que j'ai développé afin justement d'éviter de passer par les repositories de Kali et ainsi limiter au maximum la casse
du système. Néanmoins, la mise à jour de certains outils est impossible à mettre en place. On ne peut donc que les installer ou les désinstaller.

Clonez le repository du projet:

{% highlight bash %}
$ git clone https://github.com/funeoz/kalibuntu
$ cd kalibuntu
# donner les droits d'exécution à tous les scripts shell dans le répertoire
$ find . -type f -iname "*.sh" -exec chmod +x {} \;
# lancer le script de premier démarrage
$ sudo ./first_run.sh
{% endhighlight %}

Pour lancer Kalibuntu, il suffit d'exécuter le fichier `kalibuntu.sh`:

{% highlight bash %}
$ sudo ./kalibuntu.sh
{% endhighlight %}

Le fonctionnement reste le même que pour Katoolin3 avec un système de menus.

