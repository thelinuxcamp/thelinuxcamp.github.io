---
layout: default
show_sidebar: false
title: Serveur Discord
---

Un serveur Discord a été mis en place pour les utilisateurs du site.

&nbsp;
&nbsp;

<script type="text/javascript" src="//cdn.jsdelivr.net/gh/restingcoder/discord-widget@1.1/discord-widget.min.js"></script>
<script type="text/javascript">
    discordWidget.init({
        serverId: '638374749688561664',
        title: 'TheLinuxCamp',
        join: true,
        joinText: 'Rejoindre le serveur',
        alphabetical: false,
        theme: 'dark',
        hideChannels: ['Chat des rédacteurs'],
        showAllUsers: true,
        allUsersDefaultState: true,
        showNick: false,
        userName: '',
        useCDN: true
    });
    discordWidget.render();
</script>
<div class="discord-widget"></div>