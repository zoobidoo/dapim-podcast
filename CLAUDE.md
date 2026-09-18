# dapim-podcast — notes pour Claude

## Ce que c'est
Hébergement des **flux RSS et des jaquettes** du podcast AMA, en 7 langues :
`ama/{fr,en,de,es,it,jp,cn}/feed.xml` + `cover.png`. Aucun code, aucun build.

## ⚠️ Ce dépôt doit rester public
C'est un dépôt **public**, et il doit le rester : les jaquettes sont servies
par GitHub Pages (`https://zoobidoo.github.io/dapim-podcast/ama/...`) et référencées
depuis les flux. Le passer en privé casserait GitHub Pages, donc l'affichage des
jaquettes chez tous les agrégateurs qui consomment ces flux.

Corollaire : **rien de sensible ne doit entrer dans ce dépôt**. Pas de clé, pas de
brouillon, pas de note interne.

## Ce qui compte dans un feed
- Les URL d'enclosure pointent vers `archive.org/download/dapim-podcast-ama/...` — les
  fichiers audio ne sont pas dans le dépôt.
- La publication passe par Spotify for Podcasters / Anchor
  (`podcasters.spotify.com/pod/show/dapim`), et les flux déclarent un hub PubSubHubbub :
  une modification de feed se propage, elle n'est pas locale.
- Les jaquettes sont en **3000 × 3000** (exigence des annuaires de podcasts). Ne pas
  publier une taille inférieure.
- Volumétrie actuelle : 30 épisodes en français, 2 en en/de/es/it, 1 en jp/cn.

## Pièges
- Une erreur de XML dans un `feed.xml` casse le podcast chez tous les abonnés de cette
  langue. Valider avant de commiter.
- Le `README.md` ne contient que le mot « README.md ». Il y a mieux à faire s'il faut
  toucher à ce dépôt.

## Git
Commiter à chaque état qui fonctionne. Ne jamais pousser sans l'accord explicite du propriétaire du dépôt.
