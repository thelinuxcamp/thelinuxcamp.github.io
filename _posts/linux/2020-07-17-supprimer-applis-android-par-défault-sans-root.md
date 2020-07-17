---
author: Funeoz
permalink: /linux/supprimer-applis-android-par-défaut-sans-root-adb.html
title: Supprimer les applis Android par défaut sans root avec ADB
category: linux
image: /assets/2020-07-17/image1adb.webp
---

Les constructeurs de téléphones mobiles décident souvent d'installer des applications que l'on ne peut que désactiver. Voici une méthode pour supprimer ces applications sans root avec ADB.

## Installation d'ADB

### Sous Ubuntu et Debian

Lancez votre terminal et installez adb avec apt:

{% highlight bash %}
$ sudo apt-get update
$ sudo apt-get install adb
{% endhighlight %}

### Sous Arch et Manjaro

{% highlight bash %}
$ sudo pacman -Syyu
$ sudo pacman -S android-tools
{% endhighlight %}

### Sous Fedora et OpenSUSE

{% highlight bash %}
$ sudo dnf install android-tools
{% endhighlight %}

## Activation du débogage USB de votre téléphone

Pour pouvoir utiliser ADB avec votre appareil, il va falloir activer le débogage USB disponible dans les options développeurs.

Pour cela:

1. Allez dans les paramètres.
2. Descendez jusqu'à `A propos du téléphone` et cliquez dessus.
3. Descendez jusqu'au `Numéro de build` et cliquez indéfiniment jusqu'à qu'une notification vous dise que les options développeurs sont activées.
4. Revenez sur le menu principal des paramètres et rendez-vous dans la catégorie `Options développeurs`.
5. Descendez jusqu'à `Débogage USB` et activez l'option.

## Suppression des applications

Maintenant, connectez votre téléphone avec votre câble et choisissez le mode `Transfert de fichiers`.

Lancez la commande `adb devices` dans votre terminal:

{% highlight bash %}
$ adb devices
List of devices attached
ZH33C2DSH5      device
{% endhighlight %}

Si vous ne voyez pas votre appareil, c'est que vous n'avez pas autoriser l'accès de l'ordinateur à votre téléphone (un pop-up doit apparaître sur votre téléphone pour autoriser cet accès).

Lancez ensuite un shell:

{% highlight bash %}
$ adb shell
{% endhighlight %}

Pour lister la liste des paquets sur votre téléphone:

{% highlight bash %}
$ pm list packages
{% endhighlight %}

Pour chercher un paquet particulier:

{% highlight bash %}
$ pm list packages | grep "[paquet]"
{% endhighlight %}

Si cette méthode vous semble compliquée, vous pouvez vous rendre sur le [Play Store](https://play.google.com/store), chercher l'application à supprimer. Le nom du paquet sera disponible dans l'URL à la suite de `?id=`.

![image2](/assets/2020-07-17/image2adb.webp)

Pour suppprimer une application:

{% highlight bash %}
$ pm uninstall -k --user 0 [nom-du-paquet]
{% endhighlight %}

Le shell devrait vous renvoyer `Success` si l'application a bien été supprimée.

**Remarque** : Supprimer des applications telles que Play Musique, Play Livres, Chrome est sans risque. Néanmoins, supprimer des applications dont le système est dépendant (ex: Google Play Store) pourrait vous poser des problèmes et briquer votre téléphone. Vous devrez donc ensuite le réinitialiser.