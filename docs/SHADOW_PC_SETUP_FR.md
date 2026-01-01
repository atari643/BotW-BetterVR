# Guide d'installation BotW BetterVR sur Shadow PC avec Virtual Desktop

Ce guide vous explique comment configurer et jouer à BotW BetterVR sur **Shadow PC** en utilisant **Virtual Desktop** pour diffuser en VR sur votre casque Meta Quest (ou autre casque compatible).

## Table des matières
1. [Prérequis](#prérequis)
2. [Configuration requise](#configuration-requise)
3. [Installation sur Shadow PC](#installation-sur-shadow-pc)
4. [Configuration de Virtual Desktop](#configuration-de-virtual-desktop)
5. [Optimisation des performances](#optimisation-des-performances)
6. [Résolution des problèmes](#résolution-des-problèmes)

---

## Prérequis

### Matériel nécessaire
- **Shadow PC** (abonnement actif avec un GPU dédié)
- **Casque VR** compatible avec Virtual Desktop (Meta Quest, Quest 2, Quest 3, Quest Pro, etc.)
- **Connexion Internet** : 
  - Minimum 30 Mbps de débit descendant
  - Recommandé : 50+ Mbps avec latence < 30ms
- **Routeur Wi-Fi** : Wi-Fi 5 (802.11ac) minimum, Wi-Fi 6 recommandé pour le casque VR
- **Connexion Ethernet** pour Shadow PC (fortement recommandé)

### Logiciels requis
- **Virtual Desktop** (application payante sur Quest Store ~20€)
- **Virtual Desktop Streamer** (application PC gratuite)
- **Cemu 2.6 ou plus récent**
- **BotW BetterVR** (dernière version)
- Une copie légale de **The Legend of Zelda: Breath of the Wild** pour Wii U

---

## Configuration requise

### Shadow PC - Configurations recommandées

Shadow propose différents niveaux de service. Voici les recommandations pour BotW BetterVR :

#### ✅ Shadow Power Upgrade (RECOMMANDÉ)
- **GPU** : NVIDIA GTX 1080 / RTX équivalent ou supérieur
- **CPU** : Intel Xeon ou équivalent (performance mono-thread élevée)
- **RAM** : 12-16 GB
- **Résultat attendu** : Expérience fluide à 72-90 FPS en VR

#### ⚠️ Shadow PC Base
- **GPU** : NVIDIA GTX 1080 équivalent
- **CPU** : Performance variable
- **RAM** : 12 GB
- **Résultat attendu** : Expérience jouable mais peut nécessiter des compromis graphiques

#### ❌ Shadow PC Boost (Configuration minimale)
- Peut fonctionner avec des paramètres graphiques réduits
- FPS limité à 60-72 FPS
- Non recommandé pour une expérience VR optimale

### Carte graphique Intel intégrée (i7 13ème génération)

**Réponse courte : Non recommandé pour VR**

Les cartes graphiques Intel intégrées (Intel Iris Xe Graphics) sur les processeurs i7 de 13ème génération :

❌ **Ne sont PAS recommandées** pour BotW BetterVR car :
- **Performance insuffisante** : Les iGPU Intel ne peuvent pas maintenir 60+ FPS en VR avec Cemu
- **Pas de support Vulkan robuste** : Compatibilité limitée avec l'API Vulkan utilisée par BetterVR
- **Latence élevée** : La VR nécessite des temps de rendu très faibles que les iGPU ne peuvent pas garantir
- **Streaming VR impossible** : Virtual Desktop nécessite un GPU dédié pour encoder le flux VR

**Alternative recommandée :**
- Utilisez **Shadow PC** qui fournit un GPU dédié dans le cloud
- Ou investissez dans un PC avec GPU dédié (NVIDIA GTX 1660 minimum, RTX 3060 recommandé)

### Configuration réseau optimale

Pour minimiser la latence en streaming VR :

1. **Shadow PC → Internet**
   - Connexion filaire (Ethernet) fortement recommandée
   - Latence vers Shadow : < 20ms idéal, < 30ms acceptable

2. **Casque VR → Routeur**
   - Wi-Fi 5 GHz (802.11ac) minimum
   - Wi-Fi 6 (802.11ax) recommandé
   - Le casque VR doit être proche du routeur (même pièce de préférence)

3. **Test de connexion**
   ```
   Latence totale recommandée : < 40ms
   Latence idéale : < 25ms
   ```

---

## Installation sur Shadow PC

### Étape 1 : Accéder à Shadow PC

1. Lancez votre application Shadow sur votre PC local ou téléphone
2. Connectez-vous à votre Shadow PC
3. Une fois connecté, vous travaillez maintenant sur votre PC dans le cloud

### Étape 2 : Installer Cemu

1. Téléchargez **Cemu 2.6 ou plus récent** depuis [cemu.info](https://cemu.info/)
2. Extrayez Cemu dans un dossier (ex: `C:\Games\Cemu`)
3. Configurez Cemu en suivant [ce guide](https://cemu.cfw.guide/)
4. **IMPORTANT** : Testez que BotW fonctionne correctement à 60+ FPS **avant** d'installer le mod VR
   - Lancez le jeu normalement
   - Vérifiez que vous obtenez 60 FPS constants
   - Si non, ajustez les paramètres graphiques

### Étape 3 : Configurer Cemu pour de bonnes performances

1. Ouvrez Cemu → `Options` → `General Settings` → onglet `Graphics`
2. Configurez :
   - **API Graphique** : Vulkan (OBLIGATOIRE)
   - **Device** : Sélectionnez votre GPU NVIDIA
   - **VSync** : OFF (désactivé)

3. Fermez Cemu complètement

### Étape 4 : Installer BotW BetterVR

1. Téléchargez la dernière version de BotW BetterVR depuis [Releases](https://github.com/Crementif/BotW-BetterVR/releases)
2. Extrayez **TOUS les fichiers** du .zip dans le dossier où se trouve `Cemu.exe`
   - Vous devriez voir : `.dll`, `.json`, et plusieurs fichiers `.bat` à côté de `Cemu.exe`
3. NE LANCEZ PAS encore Cemu

### Étape 5 : Installer Virtual Desktop Streamer

1. Sur Shadow PC, téléchargez **Virtual Desktop Streamer** depuis [https://www.vrdesktop.net/](https://www.vrdesktop.net/)
2. Installez l'application
3. Lancez Virtual Desktop Streamer
4. Connectez-vous avec le **même compte Oculus/Meta** que votre casque
5. Configurez :
   - **Codec** : H.264 ou HEVC (testez les deux)
   - **Bitrate** : Automatique ou 100 Mbps pour commencer
   - **Résolution** : Automatique
   - Activez **"Use hardware encoding"**

---

## Configuration de Virtual Desktop

### Sur le casque Quest

1. Installez **Virtual Desktop** depuis le Quest Store (achat nécessaire ~20€)
2. Lancez Virtual Desktop sur votre casque
3. L'application devrait détecter automatiquement votre Shadow PC (assurez-vous que Virtual Desktop Streamer est lancé)
4. Sélectionnez votre Shadow PC et connectez-vous

### Paramètres VR optimaux dans Virtual Desktop

Une fois connecté au Shadow PC via Virtual Desktop :

1. Ouvrez le menu Virtual Desktop (bouton menu gauche)
2. Allez dans **Streaming**
   - **Codec vidéo** : H.264+ (ou HEVC si supporté et connexion excellente)
   - **Refresh rate** : 72 Hz ou 90 Hz (selon votre casque)
   - **Bitrate** : 100-150 Mbps (ajustez selon votre connexion)
   - **Slice mode** : Automatique
   - **SSW** : Désactivé pour VR native
   - **Résolution** : Élevée ou Automatique

3. Allez dans **Environment**
   - Choisissez n'importe quel environnement (vous serez dans le jeu de toute façon)

### Lancer BotW BetterVR

1. Dans Virtual Desktop, vous voyez votre bureau Shadow PC
2. Sur Shadow PC, double-cliquez sur **`BetterVR LAUNCH CEMU IN VR.bat`**
   - Ceci lance Cemu et installe automatiquement le graphic pack BetterVR
3. Dans Cemu, allez dans `Options` → `Graphic packs` → `The Legend of Zelda: Breath of the Wild`
4. **Activez les graphic packs suivants** :
   - ✅ **BetterVR** (obligatoire)
   - ✅ **FPS++** (obligatoire, sinon crash)
   - ✅ Cliquez sur **"Download Community Graphic Packs"** pour mettre à jour
5. Configurez les paramètres graphiques recommandés :
   - **Graphics** : 1440p ou 1800p (pas d'ultrawide), Anti-aliasing : Nvidia FXAA
   - **FPS++** : Limite FPS à 120 ou 144
   - **Enhancements** : Filtrage anisotropique 16x
6. Fermez les paramètres et lancez le jeu depuis la liste de jeux Cemu
7. **Mettez votre casque VR** - le jeu devrait maintenant être en VR! 🎮

---

## Optimisation des performances

### Si vous avez des ralentissements (FPS < 60)

1. **Réduire la résolution dans Graphic Packs**
   - Passez de 1800p à 1440p ou 1080p
   
2. **Ajuster Virtual Desktop**
   - Réduisez le bitrate à 80-100 Mbps
   - Passez en 72 Hz au lieu de 90 Hz
   
3. **Paramètres Cemu**
   - Désactivez les ombres haute résolution
   - Réduisez la distance d'affichage
   
4. **Fermez les applications Shadow PC en arrière-plan**
   - Seuls Cemu et Virtual Desktop Streamer doivent tourner

### Pour améliorer la qualité visuelle

Si vous avez des FPS stables > 90 :

1. Augmentez la résolution à 1800p ou 2160p
2. Activez des améliorations graphiques supplémentaires
3. Augmentez le bitrate Virtual Desktop à 150-200 Mbps

### Réduire la latence

- **Utilisez une connexion Ethernet** pour votre PC local si vous pilotez Shadow depuis là
- **Rapprochez votre casque du routeur Wi-Fi**
- **Fermez tous les téléchargements/streaming** sur votre réseau
- Vérifiez la latence dans l'overlay Virtual Desktop (doit être < 40ms total)

---

## Résolution des problèmes

### Le jeu ne s'affiche pas en VR

1. Vérifiez que vous avez lancé Cemu avec **`BetterVR LAUNCH CEMU IN VR.bat`** (PAS Cemu.exe directement)
2. Le graphic pack **BetterVR** doit être activé dans Options → Graphic packs
3. Redémarrez Cemu en utilisant le fichier .bat

### Latence/Lag important

1. **Testez votre connexion** :
   - Ouvrez l'overlay Virtual Desktop
   - Vérifiez "Network latency" et "Total latency"
   - Si > 50ms, le problème vient du réseau

2. **Solutions réseau** :
   - Passez en Wi-Fi 5 GHz
   - Rapprochez le casque du routeur
   - Vérifiez que personne ne télécharge sur votre réseau
   - Redémarrez votre routeur

### Shadow PC lent / FPS bas

1. Vérifiez que Shadow utilise bien le GPU dédié (pas l'iGPU)
2. Fermez tous les programmes en arrière-plan
3. Réduisez les paramètres graphiques dans Cemu
4. Contactez le support Shadow si les performances sont anormalement basses

### Virtual Desktop ne détecte pas Shadow PC

1. Assurez-vous que **Virtual Desktop Streamer** est bien lancé sur Shadow PC
2. Vérifiez que vous utilisez le **même compte** sur le casque et le streamer
3. Désactivez temporairement le pare-feu Windows sur Shadow
4. Redémarrez Virtual Desktop sur le casque

### Crash au lancement du jeu

1. Vérifiez que **FPS++** est activé dans les graphic packs (sinon crash garanti)
2. Assurez-vous que Vulkan est bien sélectionné (pas OpenGL)
3. Mettez à jour les graphic packs communautaires
4. Vérifiez que votre jeu est bien en version V208 (mise à jour 1.5.0)

---

## Commandes à partir de maintenant

Une fois tout configuré :

1. **Lancer Shadow PC** (depuis votre app Shadow)
2. **Lancer Virtual Desktop** sur votre casque Quest
3. **Se connecter** à Shadow PC via Virtual Desktop
4. **Double-cliquer** sur `BetterVR LAUNCH CEMU IN VR.bat` sur le bureau Shadow
5. **Lancer le jeu** depuis Cemu
6. **Mettre le casque** et profiter ! 🎮

---

## Ressources supplémentaires

- **Discord Flat2VR** : [https://discord.gg/flat2vr](https://discord.gg/flat2vr) - Support communautaire
- **Guide Cemu** : [https://cemu.cfw.guide/](https://cemu.cfw.guide/)
- **GitHub BotW BetterVR** : [https://github.com/Crementif/BotW-BetterVR](https://github.com/Crementif/BotW-BetterVR)
- **Shadow Support** : [https://help.shadow.tech/](https://help.shadow.tech/)
- **Virtual Desktop Support** : [https://www.vrdesktop.net/](https://www.vrdesktop.net/)

---

## FAQ Rapide

**Q : Puis-je utiliser mon PC avec Intel i7 13ème gen (graphiques intégrés) au lieu de Shadow ?**  
R : Non, les graphiques Intel intégrés ne sont pas assez puissants pour faire tourner Cemu + VR. Shadow PC est nécessaire.

**Q : Virtual Desktop est-il obligatoire ?**  
R : Non, mais c'est la solution la plus simple pour Quest. Vous pouvez aussi utiliser Air Link (Meta) ou ALVR (gratuit), mais Virtual Desktop offre généralement de meilleures performances.

**Q : Quel est le coût total ?**  
R : Shadow PC (~30€/mois) + Virtual Desktop (~20€ une fois) + le jeu BotW (si vous ne l'avez pas)

**Q : Puis-je utiliser un casque PCVR filaire au lieu de Quest ?**  
R : Oui ! Si vous avez un Valve Index, HP Reverb, etc., branchez-le directement à Shadow PC (via USB over Network) ou à votre PC local si celui-ci a un GPU dédié suffisant.

**Q : La latence est-elle acceptable pour jouer ?**  
R : Avec une bonne connexion (< 30ms vers Shadow, Wi-Fi 5GHz pour le casque), la latence totale est de 30-50ms, ce qui est acceptable pour BotW. Les jeux rapides comme Beat Saber seraient plus difficiles.

---

**Bon jeu en VR ! 🎮✨**
