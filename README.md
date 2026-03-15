# 🎮 DayZ Server Manager (v1.1)

Bienvenue dans **DayZ Server Manager**, une application de bureau moderne et robuste conçue pour faciliter l'installation, la configuration, le modding et la gestion de vos serveurs DayZ (Standalone) sur Windows.

L'application a été entièrement refondue en version 1.1 pour offrir une stabilité accrue (Architecture MVC) et un monitoring en temps réel performant.

---

## ✨ Nouveautés de la v1.1

Cette version apporte des changements majeurs réclamés par la communauté :
- **📊 Nouveau Dashboard** : Vue d'ensemble avec monitoring en temps réel de la RAM, de l'Uptime et statut du serveur.
- **🚀 Éditeur XML Haute Performance** : Un moteur d'édition paginé et réactif, capable de gérer des fichiers `types.xml` de plus de 2000 entrées sans ralentissement.
- **✖️ Multiplicateurs Économie** : Ajustez la rareté de votre butin en un clic (ex: doubler tout le "Nominal" ou diviser la "Lifetime").
- **🏗️ Architecture MVC & EventBus** : Une base de code découplée et robuste utilisant le pattern Observer pour des mises à jour d'UI fluides et asynchrones.
- **🧪 Suite de Tests** : Une infrastructure de tests unitaires pour garantir la sécurité de vos configurations.

---

## 📥 Téléchargement

Pour obtenir la dernière version stable de l'application :

1. Rendez-vous sur la page **[Releases](https://github.com/)** du projet (à droite sur GitHub).
2. Repérez la version la plus récente (marquée **Latest**).
3. Dans la section **Assets**, téléchargez le fichier `DayZServerManager.exe`.

---

## 🚀 Installation Rapide

L'avantage de cet outil est qu'il est autonome ! Voici comment commencer de zéro :

1. **Téléchargez** le fichier `DayZServerManager.exe` (ou lancez `main.py` si vous êtes développeur).
2. Placez l'exécutable dans un **nouveau dossier vide** (Exemple : `C:\DayZ_Server\`).
3. **Lancez l'application en tant qu'Administrateur** (Indispensable pour SteamCMD et le réseau).
4. Les sous-dossiers locaux (`logs/`, `dayz_server/`, `steamcmd/`) seront créés automatiquement.

---

## 🛠️ Prérequis Système

DayZ Server requiert les bibliothèques Microsoft Visual C++ pour fonctionner.
1. Allez dans l'onglet **🔧 Dépendances**.
2. Cliquez sur **Vérifier les prérequis**.
3. Assurez-vous que toutes les lignes sont au vert (✅). Si une croix rouge (❌) apparaît, téléchargez le package correspondant via le lien fourni.

---

## 🚀 Guide d'Utilisation (Navigation Sidebar)

L'interface est organisée via une barre latérale moderne :

### 1. Dashboard (Tableau de bord)
Votre centre de contrôle. Démarrez ou arrêtez le serveur en un clic et surveillez sa consommation de ressources en temps réel.

### 2. Serveur (Installation & MAJ)
Gérez le cœur du jeu. Installez SteamCMD, puis téléchargez ou mettez à jour les fichiers du serveur DayZ.

### 3. Configuration (Édition Intelligente)
Éditez vos fichiers `.cfg` et `.xml` via une interface intuitive :
- **Mode Formulaire** : Pour les fichiers `.cfg` simples.
- **Mode Tableur Performance** : Pour les gros fichiers XML (`types.xml`, `globals.xml`).
- **Outil Multiplicateur** : Sélectionnez plusieurs lignes et appliquez un facteur (ex: `x2`) instantanément.

### 4. Mods (Gestion Automatisée)
Entrez les IDs Steam Workshop (ex: `1559212036`), et l'application s'occupe de tout :
- Téléchargement Workshop.
- Copie dans le dossier serveur.
- Synchronisation automatique des clés `.bikey`.

---

## 🏗️ Pour les Développeurs

Le projet suit maintenant une architecture **Model-View-Controller (MVC)** stricte :
- **Core** : Logique métier (SteamCMD, Launcher, Éditeurs).
- **GUI** : Interface CustomTkinter organisée en Views et Tabs.
- **Events** : `EventBus` (Singleton) centralisant la communication entre couches via des événements asynchrones.

### Tests Unitaires
Pour lancer les tests de validation de configuration :
```bash
python -m pytest tests/test_config.py
```

### Build
Un script `build.bat` est disponible pour générer l'exécutable via PyInstaller.

---

## ⚠️ Dépannage

- **Erreur RAM / "Descripteur non valide"** : Corrigé en v1.1 via l'intégration de `psutil` et `taskkill` pour une gestion propre des processus.
- **XML corrompu** : L'éditeur valide désormais la structure XML avant chaque sauvegarde.
- **Permission refusée** : Assurez-vous d'avoir lancé l'application en mode Administrateur.

---

_Développé avec 💙 en Python. Interface propulsée par CustomTkinter._
