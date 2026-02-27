<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0f,30:0d1117,60:161b22,100:1a1f2e&height=200&section=header&text=Koceila%20BRAIKI&fontSize=60&fontColor=e6edf3&fontAlignY=38&desc=Étudiant%20L3%20Informatique%20—%20IGM%20Gustave%20Eiffel%20%7C%20En%20recherche%20d'alternance%20septembre%202026&descAlignY=60&descSize=14&descColor=8b949e&animation=fadeIn" />

</div>

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Koceila%20BRAIKI-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/koceila-braiki)
[![Email](https://img.shields.io/badge/Email-braiki.koceila%40outlook.fr-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white)](mailto:braiki.koceila@outlook.fr)
[![GitHub](https://img.shields.io/badge/GitHub-KoceilaBRAIKI-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/KoceilaBRAIKI)

</div>

---

## À propos de moi

Étudiant en **L3 Informatique** à l'Université Gustave Eiffel — Institut Gaspard Monge, je conçois et développe des logiciels couvrant un large spectre : **systèmes bas niveau en C**, **applications web full-stack**, **outils de compilation**, **jeux** et **algorithmes de compression**.

Mon parcours m'a conduit à maîtriser autant la gestion manuelle de la mémoire que les architectures web modernes — toujours avec un souci de code propre, documenté et fonctionnel.

> 🎯 **Objectif :** Alternance informatique — Septembre 2026 · Poursuite en Master

---

## Projets phares

### 🔬 TPC Syntactic Analyzer — Compilateur C (Flex & Bison)
> *L3 Informatique — 2025-2026*

**[`tpas-C-Flex-Bison-`](https://github.com/KoceilaBRAIKI/tpas-C-Flex-Bison-)** — Analyseur syntaxique complet pour un sous-ensemble du langage C.

- Grammaire **stratifiée à 7 niveaux** pour respecter les priorités d'opérateurs
- Construction et affichage d'un **Arbre Syntaxique Abstrait (ASA)**
- **Localisation précise des erreurs** : ligne + colonne via `YY_USER_ACTION`
- Récursivité gauche pour l'accès aux champs `struct` (`a.b.c`)
- Zéro fuite mémoire — libération complète via `deleteTree`

`C` `Flex` `Bison` `Make` `AST` `Compilation`

---

### 🗜️ CoDec DIF — Codec de compression d'images
> *Projet système — Licence Informatique*

**[`codec-dif`](https://github.com/KoceilaBRAIKI/codec-dif)** — Système de compression/décompression d'images développé from scratch en C, format propriétaire `.dif`.

- **Codage différentiel** : stockage des deltas inter-pixels pour réduire l'entropie
- **Encodage entropique à préfixes variables** sur 4 niveaux (2 à 11 bits)
- Compression **sans perte** (lossless), fidèle au pixel près
- Résultat : **~47% de réduction** sur images PGM réelles
- Architecture bibliothèque `.so` séparée de l'exécutable CLI

`C` `Algorithmique` `Compression` `BitStream` `Makefile` `UNIX`

---

### 🛒 TrouveCompo — Application web full-stack
> *Projet académique — 2024*

**[`KoceilaBRAIKI`](https://github.com/KoceilaBRAIKI)** — Plateforme de gestion de composants électroniques avec gestion multi-rôles.

- Architecture **3 tiers** : Flask + PostgreSQL + Jinja2
- 3 espaces distincts : **Client**, **Employé**, **Gérant**
- Recherche multicritères, gestion de stock, facturation
- Requêtes SQL optimisées avec `psycopg`

`Python` `Flask` `PostgreSQL` `Jinja2` `HTML/CSS`

---

### 🎒 BackpackHero — Jeu RPG tactique en Java
> *L3 Informatique — 2025-2026*

**[`backpack-hero-java`](https://github.com/KoceilaBRAIKI/backpack-hero-java)** — RPG au tour par tour avec gestion d'inventaire en grille (inspiré de Backpack Hero).

- **Placement spatial des objets** : formes L, T, Z, + avec rotation
- **Synergies** entre objets adjacents modifiant les effets en combat
- Architecture **MVC** complète : `model/`, `view/`, `controller/`, `data/`
- 3 héros, 3 étages, système d'économie, progression XP
- Malédictions non-rectangulaires écrasant dynamiquement l'inventaire

`Java` `Zen 6.0` `POO` `MVC` `Apache Ant`

---

### 🎮 Stellar Assault — Space Shooter 2D
> *L2 Informatique — 2024*

**[`stellar-assault-Python-Pygame-`](https://github.com/KoceilaBRAIKI/stellar-assault-Python-Pygame-)** — Jeu de tir spatial 100% procédural, aucun asset externe.

- **Système de particules** complet : explosions, sillage moteur, étincelles
- **Effets de glow** additifs `BLEND_ADD` — rendu néon sans GPU
- 4 types d'ennemis dont un Boss toutes les 5 vagues
- **Combo x1–x8** avec fenêtre temporelle, Power-Ups aléatoires
- 1173 lignes · 15 classes · FSM à 3 états

`Python` `Pygame` `POO` `Architecture` `Procédural`

---

### ⚔️ Darkest Dungeon — RPG en C
> *L2 Informatique — 2024-2025*

**[`darkest-dungeon-c`](https://github.com/KoceilaBRAIKI/darkest-dungeon-c)** — Jeu de rôle tactique au tour par tour en ligne de commande.

- **Listes chaînées dynamiques** pour personnages, ennemis et accessoires
- Mécaniques : stress, HP, équipements, boutique, soins (queue FIFO)
- **Sauvegarde et chargement** complets via fichier texte
- Gestion mémoire manuelle sans fuite

`C` `Listes chaînées` `Queue FIFO` `Gestion mémoire` `Fichiers`

---

## Compétences techniques

### Langages

| Langage | Niveau | Usage principal |
|---------|--------|----------------|
| **C** | ★★★★★ | Système, mémoire, compilation, algorithmes |
| **Java** | ★★★★☆ | POO avancée, design patterns, GUI |
| **Python** | ★★★★☆ | Web (Flask), scripting, jeux (Pygame) |
| **Haskell** | ★★★☆☆ | Programmation fonctionnelle |
| **SQL / PL-pgSQL** | ★★★★☆ | Modélisation, triggers, transactions |
| **HTML / CSS** | ★★★☆☆ | Interfaces web |
| **NASM** | ★★★☆☆ | Génération de code assembleur |

### Domaines

**Compilation** — Chaîne complète : Flex (lexical) → Bison (syntaxique) → AST → NASM  
**Systèmes** — Gestion mémoire, processus, appels système, UNIX/Linux  
**Bases de données** — PostgreSQL, MySQL, modélisation relationnelle, optimisation  
**Réseaux** — Pile TCP/IP, modèle OSI, Wireshark  
**Web** — Flask, Angular, PHP  
**Algorithmique** — Graphes (Dijkstra, flots), arbres (Huffman), tris, hachage

---

## Formation

🎓 **L3 Informatique** — Université Gustave Eiffel, Institut Gaspard Monge *(2025-2026)*  
🎓 **L2 Informatique** — Université Gustave Eiffel *(2024-2025)*

---

## Me contacter

<div align="center">

| 📧 Email | 💼 LinkedIn | 🐙 GitHub |
|----------|-------------|-----------|
| [braiki.koceila@outlook.fr](mailto:braiki.koceila@outlook.fr) | [koceila-braiki](https://www.linkedin.com/in/koceila-braiki) | [KoceilaBRAIKI](https://github.com/KoceilaBRAIKI) |

<br/>

<img src="https://komarev.com/ghpvc/?username=KoceilaBRAIKI&color=58a6ff&style=for-the-badge&label=Visites+du+profil" />

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1f2e,50:161b22,100:0a0a0f&height=100&section=footer" />
