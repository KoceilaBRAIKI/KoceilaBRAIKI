<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=240&section=header&text=Koceila%20BRAIKI&fontSize=62&fontColor=ffffff&fontAlignY=38&desc=Étudiant%20L3%20Informatique%20·%20IGM%20Gustave%20Eiffel%20·%20Paris&descSize=16&descColor=a8b3cf&descAlignY=58&animation=twinkling" />

</div>

<div align="center">

```
╔══════════════════════════════════════════════════════════════╗
║  🎯  En recherche d'alternance · Informatique · Sept. 2026   ║
╚══════════════════════════════════════════════════════════════╝
```

</div>

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Koceila%20BRAIKI-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/koceila-braiki)&nbsp;
[![Email](https://img.shields.io/badge/braiki.koceila%40outlook.fr-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white)](mailto:braiki.koceila@outlook.fr)&nbsp;
[![GitHub](https://img.shields.io/badge/KoceilaBRAIKI-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/KoceilaBRAIKI)&nbsp;
[![Université](https://img.shields.io/badge/IGM-Gustave%20Eiffel-00A86B?style=for-the-badge&logo=academia&logoColor=white)](https://igm.univ-gustave-eiffel.fr)

</div>

<br/>

---

## `whoami`

```python
class KoceilaBRAIKI:
    def __init__(self):
        self.formation  = "L3 Informatique — Institut Gaspard Monge, Université Gustave Eiffel"
        self.localité   = "Paris 🇫🇷"
        self.objectif   = "Alternance informatique · Septembre 2026 → Master"
        self.langages   = ["C", "Python", "Java", "Haskell", "SQL", "NASM", "LaTeX"]
        self.domaines   = ["Compilation", "Systèmes", "Web Full-Stack", "Algorithmique", "Réseaux"]
        self.contact    = "braiki.koceila@outlook.fr"

    def en_deux_mots(self) -> str:
        return """
        Je construis des logiciels du bas niveau au web : gestion mémoire en C,
        chaîne de compilation complète, applications full-stack avec PostgreSQL,
        jeux en Java et Python. Curieux des fondamentaux, attentif à la qualité du code.
        """
```

---

## 🗂️ Projets

> Six projets couvrant **compilation**, **algorithmique**, **web**, **systèmes** et **jeu vidéo** — trois langages, trois paradigmes.

<br/>

### ⚙️ Compilateur TPC — Chaîne complète Flex · Bison · AST
> `C` &nbsp;`Flex` &nbsp;`Bison` &nbsp;`Make` &nbsp;`L3 · 2025-2026`

**Analyseur syntaxique complet** pour un sous-ensemble du langage C, développé from scratch.

| Fonctionnalité | Détail technique |
|---|---|
| 📐 Grammaire stratifiée | 7 niveaux de non-terminaux (`Exp → TB → FB → M → E → T → F`) pour respecter les priorités et associativités |
| 🌳 ASA complet | `makeNode` / `makeNodeVal` avec `strdup` — affichage graphique `--tree` |
| 🎯 Erreurs précises | Macro `YY_USER_ACTION` + `current_column` → localisation ligne **et** colonne |
| 🔁 Récursivité gauche | Accès `struct` chainés (`a.b.c`) sans ambiguïté |
| 🧹 Zéro fuite mémoire | `deleteTree` libère intégralement chaque nœud alloué |

```bash
./bin/tpcas --tree < programme.tpc   # Affiche l'ASA complet
./bin/tpcas < programme.tpc          # Retourne 0 si valide, 1 sinon
```

[![Repo](https://img.shields.io/badge/GitHub-tpas--C--Flex--Bison-181717?style=flat-square&logo=github)](https://github.com/KoceilaBRAIKI/tpas-C-Flex-Bison-)

---

### 🗜️ CoDec DIF — Codec de compression d'images lossless
> `C` &nbsp;`Algorithmique` &nbsp;`BitStream` &nbsp;`UNIX` &nbsp;`Licence Informatique`

**Format propriétaire `.dif`** combinant codage différentiel et encodage entropique à longueur variable.

| Étape | Technique |
|---|---|
| 1 · Transformation | Codage différentiel pixel-à-pixel + fonction de repliement dans `[0, 255]` |
| 2 · Encodage | 4 niveaux de préfixes : de **2 bits** (valeur 0-1) à **11 bits** (valeur 22-277) |
| 3 · Décompression | Décodage inverse bit à bit, reconstruction fidèle au pixel |
| 4 · Architecture | Bibliothèque partagée `libdif.so` + exécutable CLI découplés |

```
Entrée  : photo.pgm  →  786 448 octets
Sortie  : photo.dif  →  412 031 octets
Gain    : ████████████████████░░░░░░░░░░  47.61%
```

[![Repo](https://img.shields.io/badge/GitHub-codec--dif-181717?style=flat-square&logo=github)](https://github.com/KoceilaBRAIKI/codec-dif)

---

### 🛒 TrouveCompo — Application web Full-Stack
> `Python` &nbsp;`Flask` &nbsp;`PostgreSQL` &nbsp;`Jinja2` &nbsp;`2024`

**Plateforme e-commerce** de composants électroniques avec gestion multi-rôles complète.

```
Architecture 3 tiers
┌─────────────┐    psycopg    ┌──────────────┐
│  Flask +    │ ────────────► │  PostgreSQL  │
│  Jinja2     │               │  Base de     │
│  (Back+View)│ ◄──────────── │  données     │
└─────────────┘               └──────────────┘
       │
       ▼
  3 espaces distincts :
  👤 Client  →  Recherche, projets, factures
  🔧 Employé →  Gestion stock, création factures
  📊 Gérant  →  Dashboard, CRUD composants, reporting
```

[![Repo](https://img.shields.io/badge/GitHub-TrouveCompo-181717?style=flat-square&logo=github)](https://github.com/KoceilaBRAIKI/KoceilaBRAIKI)

---

### 🎒 BackpackHero — RPG Tactique Java
> `Java` &nbsp;`Zen 6.0` &nbsp;`MVC` &nbsp;`Apache Ant` &nbsp;`L3 · 2025-2026`

**RPG au tour par tour** centré sur la gestion d'inventaire en grille, architecture MVC complète.

| Système | Implémentation |
|---|---|
| 🎮 Inventaire en grille | Objets aux formes non-rectangulaires (L, T, Z, +), rotation, placement dynamique |
| ⚡ Synergies | Effets modifiés selon l'adjacence des objets dans le sac |
| 👹 Malédictions | Formes complexes écrasant les objets sous-jacents |
| 🏗️ Architecture | `model/` · `view/` · `controller/` · `data/` — séparation stricte des responsabilités |
| 🌍 Exploration | 3 étages, 5 types de salles, progression XP, économie or |

[![Repo](https://img.shields.io/badge/GitHub-backpack--hero--java-181717?style=flat-square&logo=github)](https://github.com/KoceilaBRAIKI/backpack-hero-java)

---

### 🚀 Stellar Assault — Space Shooter 2D
> `Python` &nbsp;`Pygame` &nbsp;`POO` &nbsp;`L2 · 2024`

**Jeu de tir spatial 100% procédural** — aucun asset externe, tout généré à l'exécution.

```
Architecture FSM
   ┌─────────┐   START   ┌──────────┐   GAME OVER   ┌──────────┐
   │  menu   │ ─────────►│ playing  │───────────────►│ gameover │
   └─────────┘           └──────────┘                └──────────┘
                              │                           │
                              └───────────────────────────┘
                                         RESTART

15 classes · 1173 lignes · Glow BLEND_ADD · Particules · Screen-shake
Boss toutes les 5 vagues · Combo x1–x8 · Power-ups aléatoires (15%)
```

[![Repo](https://img.shields.io/badge/GitHub-stellar--assault-181717?style=flat-square&logo=github)](https://github.com/KoceilaBRAIKI/stellar-assault-Python-Pygame-)

---

### ⚔️ Darkest Dungeon — RPG en C
> `C` &nbsp;`Listes chaînées` &nbsp;`Queue FIFO` &nbsp;`L2 · 2024-2025`

**RPG tactique en ligne de commande**, inspiré de Darkest Dungeon, entièrement en C.

- **Listes chaînées dynamiques** pour personnages, ennemis et accessoires
- **Queue FIFO** pour Sanitarium (HP) et Taverne (stress)
- 4 classes : Furie, Vestale, Chasseur de primes, Maître chien
- 10 ennemis de difficulté croissante, récompenses aléatoires
- **Sauvegarde / chargement** complet de l'état via fichier texte
- Gestion mémoire manuelle — zéro fuite

[![Repo](https://img.shields.io/badge/GitHub-darkest--dungeon--c-181717?style=flat-square&logo=github)](https://github.com/KoceilaBRAIKI/darkest-dungeon-c)

---

## 🛠️ Stack Technique

### 💻 Langages

<div align="center">

![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Haskell](https://img.shields.io/badge/Haskell-5D4F85?style=for-the-badge&logo=haskell&logoColor=white)
![SQL](https://img.shields.io/badge/SQL%20%2F%20PL--pgSQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![NASM](https://img.shields.io/badge/NASM-Assembleur-6E4C13?style=for-the-badge)
![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)

</div>

> **C** — programmation système, gestion mémoire manuelle, pointeurs, structures complexes
> **Java** — POO avancée, héritage, interfaces, design patterns, GUI (Zen)
> **Python** — scripting, web backend (Flask), jeux (Pygame), algorithmique
> **Haskell** — programmation fonctionnelle pure, récursivité, structures immuables
> **NASM** — génération de code assembleur x86, registres, pile d'appel

---

### 🔧 Compilation & Bas Niveau

<div align="center">

![Flex](https://img.shields.io/badge/Flex-Analyse%20Lexicale-E34F26?style=for-the-badge)
![Bison](https://img.shields.io/badge/Bison-Analyse%20Syntaxique-007ACC?style=for-the-badge)
![AST](https://img.shields.io/badge/AST-Arbre%20Syntaxique-8E24AA?style=for-the-badge)
![NASM](https://img.shields.io/badge/NASM-Génération%20Code-6E4C13?style=for-the-badge)

</div>

> Chaîne complète : **Flex** (lexical) → **Bison** (syntaxique + AST) → **NASM** (génération code machine)

---

### 🗄️ Bases de Données

<div align="center">

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![PL/pgSQL](https://img.shields.io/badge/PL%2FpgSQL-Triggers%20%7C%20Procédures-336791?style=for-the-badge)

</div>

> Modélisation relationnelle · PL/pgSQL, triggers, procédures stockées · Transactions & concurrence · Optimisation des requêtes et indexation

---

### 🌐 Web & Back-End

<div align="center">

![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

</div>

> Architecture 3 tiers avec Flask + psycopg · Web avancé avec Angular · PHP · HTML/CSS

---

### 🔒 Réseaux & Systèmes

<div align="center">

![TCP/IP](https://img.shields.io/badge/TCP%2FIP-Stack%20Complète-0052CC?style=for-the-badge)
![OSI](https://img.shields.io/badge/Modèle%20OSI-7%20Couches-1A73E8?style=for-the-badge)
![Linux](https://img.shields.io/badge/UNIX%20%2F%20Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)

</div>

> Pile TCP/IP et modèle OSI · Analyse de trafic Wireshark · Gestion de processus, mémoire virtuelle, appels système · Systèmes de fichiers

---

### 📐 Algorithmique

<div align="center">

![Graphes](https://img.shields.io/badge/Graphes-Dijkstra%20%7C%20Flots%20%7C%20ACM-8E24AA?style=for-the-badge)
![Arbres](https://img.shields.io/badge/Arbres-Huffman%20%7C%20Binaires%20%7C%20AST-00897B?style=for-the-badge)
![Tris](https://img.shields.io/badge/Tris-Rapide%20%7C%20Fusion%20%7C%20Complexité-F4511E?style=for-the-badge)
![Fonctionnel](https://img.shields.io/badge/Haskell-Récursivité%20%7C%20Filtrage-5D4F85?style=for-the-badge&logo=haskell&logoColor=white)

</div>

> Hachage · Arbres de Huffman · Dijkstra, flots maximums, arbres couvrants minimaux · Analyse de complexité théorique et empirique

---

### 🔨 Outils & Environnement

<div align="center">

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Make](https://img.shields.io/badge/Makefile-Build%20System-427819?style=for-the-badge)
![Ant](https://img.shields.io/badge/Apache%20Ant-A81C7D?style=for-the-badge&logo=apache&logoColor=white)
![VSCode](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Eclipse](https://img.shields.io/badge/Eclipse-2C2255?style=for-the-badge&logo=eclipse&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=KoceilaBRAIKI&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&include_all_commits=true" />
&nbsp;&nbsp;
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=KoceilaBRAIKI&layout=compact&theme=tokyonight&hide_border=true&langs_count=7" />

</div>

<div align="center">

<img src="https://github-readme-streak-stats.herokuapp.com/?user=KoceilaBRAIKI&theme=tokyonight&hide_border=true" />

</div>

---

## 🎓 Formation

```
2025 – 2026   L3 Informatique · Institut Gaspard Monge · Université Gustave Eiffel
                └─ Compilation · Systèmes · Réseaux · Bases de données · Web · POO avancée

2024 – 2025   L2 Informatique · Université Gustave Eiffel
                └─ Algorithmique · Structures de données · C · Java · Architecture machine
```

---

## 📬 Contact

<div align="center">

<table>
<tr>
<td align="center"><a href="mailto:braiki.koceila@outlook.fr"><img src="https://img.shields.io/badge/Email-braiki.koceila%40outlook.fr-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white"/></a></td>
<td align="center"><a href="https://www.linkedin.com/in/koceila-braiki"><img src="https://img.shields.io/badge/LinkedIn-koceila--braiki-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a></td>
<td align="center"><a href="https://github.com/KoceilaBRAIKI"><img src="https://img.shields.io/badge/GitHub-KoceilaBRAIKI-181717?style=for-the-badge&logo=github&logoColor=white"/></a></td>
</tr>
</table>

<br/>

<img src="https://komarev.com/ghpvc/?username=KoceilaBRAIKI&color=6e40c9&style=for-the-badge&label=Visites+du+profil" />

</div>

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer" />
