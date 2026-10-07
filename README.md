# shx_climb

Petit script FiveM permettant de grimper sur certains murs et rebords avec une mécanique simple et fluide.

Ce script est inspiré du style de gameplay observé sur des serveurs comme Nopixel et FlashbackWL, avec une logique de "climb"/"wall climb" pensée pour donner un rendu plus immersif et réaliste lors des déplacements en ville.

## Description

Le script détecte automatiquement :
- un mur devant le joueur,
- un rebord ou une hauteur de ledge compatible,
- puis active l'animation de montée si le joueur garde la touche de sprint/contrôle appuyée pendant un court instant.

Il repose sur des raycasts pour vérifier la géométrie du mur et de la zone de prise, puis appelle l'animation de montée de GTA V via `TaskClimb`.

## Fonctionnalités

- Détection de mur avec raycast horizontal
- Détection de rebord / hauteur de ledge
- Vérification de la faisabilité du climb
- Activation sur appui prolongé de la touche sprint
- Affichage visuel de debug 3D en mode développement
- Script léger et facilement adaptable

## Structure du script

- `clients/main.lua` : logique principale de détection et activation du climb
- `clients/function.lua` : fonctions utilitaires (`DrawText3D`, `displayHelpText`, `climb`)
- `clients/netEvent.lua` : évènement de déclenchement du climb
- `config.lua` : configuration du script

## Configuration

Dans `config.lua` :

```lua
Config = {}
Config.EnableDebug = true
```

- `true` : active les messages de debug et les textes 3D
- `false` : désactive les textes de débogage pour un usage propre en production

## Installation

1. Place le dossier `shx_climb` dans le répertoire `resources/` de votre serveur FiveM.
2. Ajoute la ressource dans votre `server.cfg` :

```cfg
ensure shx_climb
```

3. Redémarre le serveur ou recharge la ressource.

## Utilisation

Approchez-vous d'un mur avec un rebord accessible et maintenez la touche de sprint pendant un moment. Si la zone est compatible, le personnage va grimper.

## Note importante

Ce script est une base de gameplay inspirée par les mécaniques modernes de climb visibles sur certains serveurs RP. Il est conçu pour être simple à modifier et à intégrer dans un serveur, sans être une copie directe d'un script existant.

## Credits

- Inspiration visuelle et gameplay : Nopixel / FlashbackWL
- Script développé et adapté pour un usage personnel / serveur FiveM

## Licence

À adapter selon le contexte de votre serveur. Si vous utilisez ce script en public, il est recommandé d'indiquer clairement qu'il s'agit d'un script personnalisé/inspiré et non d'un port officiel d'un projet tiers.
