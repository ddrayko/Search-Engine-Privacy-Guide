# 🔍 Guide de la vie privée pour les moteurs de recherche

> **Sais-tu qu'une simple recherche Google en dit long sur toi ?** Ta requête, ton IP, ton appareil, ta localisation, tes habitudes de navigation et, avec le temps, un profil terriblement précis de qui tu es. Choisis ton moteur de recherche avec soin.

Une comparaison approfondie et sans détour des moteurs de recherche, uniquement sous l'angle de la vie privée : juridiction, conservation des données, pistage publicitaire, origine de l'index, exposition au fingerprinting, et conseils pratiques.

![Markdown](https://img.shields.io/badge/format-Markdown-blue)
![Privacy](https://img.shields.io/badge/focus-Privacy-success)
![Language](https://img.shields.io/badge/language-Français-lightgrey)

---

## 📑 Sommaire

- [Pourquoi c'est important](#-pourquoi-cest-important)
- [Résumé express, une ligne par moteur](#-résumé-express-une-ligne-par-moteur)
- [Ce qu'une seule recherche révèle vraiment](#-ce-quune-seule-recherche-révèle-vraiment)
- [Tableau comparatif complet](#-tableau-comparatif-complet)
- [Classement vie privée uniquement](#-classement-vie-privée-uniquement-du-meilleur-au-pire)
- [Concepts clés expliqués](#-concepts-clés-expliqués)
- [Modèles de menace : contre qui te protèges-tu ?](#-modèles-de-menace-contre-qui-te-protèges-tu)
- [Comment choisir selon ton usage](#-comment-choisir-selon-ton-usage)
- [Conseils pratiques d'installation](#-conseils-pratiques-dinstallation)
- [Auto-héberger SearXNG, en profondeur](#-auto-héberger-searxng-en-profondeur)
- [Erreurs fréquentes qui ruinent ta vie privée](#-erreurs-fréquentes-qui-ruinent-ta-vie-privée)
- [FAQ](#-faq)
- [Glossaire](#-glossaire)
- [Sources](#-sources)

---

## 💡 Pourquoi c'est important

Les moteurs de recherche occupent une place à part dans le paysage de la vie privée : contrairement à un réseau social, où tu postes du contenu en connaissance de cause, une barre de recherche reçoit ton **intention brute**, des questions que tu ne poserais pas à un ami, des symptômes qui t'inquiètent, des relations que tu remets en question, des endroits que tu prévois de visiter, des achats que tu envisages, des personnes sur qui tu te renseignes. C'est sans doute le flux de données le plus intime que tu génères chaque jour, et il est facile d'oublier que chaque frappe sur un moteur non respectueux de la vie privée peut être enregistrée, horodatée, géolocalisée, et reliée à toi.

Une requête isolée paraît rarement sensible. **C'est le motif répété sur des milliers de requêtes qui construit le profil.**

---

## ⚡ Résumé express, une ligne par moteur

| | Moteur | Verdict |
|---|---|---|
| 🥇 | **SearXNG auto-hébergé** | L'option la plus solide, tu contrôles le serveur, les logs et les moteurs sources. Aucun tiers ne te profile. |
| 🥈 | **Startpage** | Qualité de résultats proche de Google, mais Google ne voit jamais qui recherche réellement. |
| 🥉 | **Mojeek** | Index totalement indépendant, basé au Royaume-Uni, réellement sans pistage. |
| | **DuckDuckGo** | Bon choix grand public par défaut ; index basé sur Bing ; juridiction américaine. |
| | **Brave Search** | Index indépendant, « privé par défaut », juridiction américaine. |
| | **Qwant** | Hébergé en UE (France), pas de pistage persistant, mais s'appuie sur Bing pour une partie de son index. |
| | **Ecosia** | Orienté écologie, propulsé par Bing, vie privée moyenne, publicités finançant la plantation d'arbres. |
| | **Yandex** | Grand index indépendant, juridiction russe, collecte de données importante. |
| | **Google / Bing / Yahoo** | Moteurs grand public qui construisent des profils comportementaux détaillés et pistent massivement à travers leurs écosystèmes. |

---

## 🕵️ Ce qu'une seule recherche révèle vraiment

Même une requête isolée, envoyée à un moteur adepte du pistage, peut exposer :

- **Ton adresse IP** : localisation approximative (souvent à l'échelle de la ville), ton FAI, parfois ton employeur ou ton réseau universitaire
- **L'empreinte de ton appareil** : version du navigateur, résolution d'écran, polices installées, fuseau horaire, langue. Combinés, ces éléments peuvent identifier un appareil de façon unique, même sans cookies
- **Ton identité de compte** : si tu es connecté à Google, Microsoft ou Yahoo dans la même session de navigateur, la requête est directement liée à ton vrai nom, ton email et tous les autres services que tu utilises
- **Les données de provenance** : la page d'où tu viens, ce sur quoi tu as cliqué ensuite
- **Les habitudes horaires** : l'heure de la journée ou de la nuit où tu cherches, ce qui reflète ta routine, tes horaires de travail, ton sommeil
- **Les signaux d'intention** : problèmes de santé, situations financières, difficultés relationnelles, questions juridiques, opinions politiques, orientation sexuelle. Tout cela peut être déduit des termes recherchés au fil du temps

Rien de tout ça ne nécessite de se « connecter » où que ce soit. Les cookies, la corrélation d'IP et le fingerprinting du navigateur suffisent souvent à eux seuls à construire un profil persistant à travers les sessions, même dans les fenêtres dites « privées » (qui n'empêchent que l'historique *local*, pas le pistage côté serveur).

---

## 📊 Tableau comparatif complet

| Moteur | Juridiction | Source des résultats | Conservation des données / profilage | Publicités ciblées ? | Points forts vie privée | Limites |
|---|---|---|---|---|---|---|
| **SearXNG (auto-hébergé)** | Là où tu l'héberges | Agrégateur de métarecherche (Google, Bing, Brave, etc., configurable) | Pas de logs centralisés si bien configuré ; tu contrôles toute la journalisation | Non (sauf si tu en ajoutes) | Open source, entièrement décentralisé, pas de compte requis, aucun traqueur tiers ne voit tes requêtes, tu choisis les moteurs sources | Nécessite une configuration technique et une maintenance ; qualité des résultats dépendante de ta configuration ; une instance *publique* de SearXNG demande de faire confiance à son administrateur |
| **Startpage** | Pays-Bas (UE) | Principalement les résultats Google via un proxy anonymisant, plus son propre index | Ne stocke pas les adresses IP, pas d'historique lié à un compte, pas de profil comportemental à long terme | Publicités contextuelles uniquement, pas basées sur un profilage inter-sessions | Résultats qualité Google sans que Google ne voie le demandeur ; politique stricte de non-pistage ; requêtes chiffrées ; pas de cookies de suivi persistants | Entreprise à l'origine américaine (Ideal Group), désormais néerlandaise ; dépend structurellement de l'index Google ; certaines options (paramètres sauvegardés) peuvent créer un identifiant semi-persistant si activées |
| **DuckDuckGo** | États-Unis | Principalement Bing, plus son propre robot d'indexation et d'autres partenaires | Pas d'historique lié à un compte, ne vend pas de données personnelles, peut conserver des logs anonymisés de courte durée | Publicités contextuelles basées uniquement sur le terme recherché, pas un profil à long terme | Très simple d'utilisation, « pas de pistage » par défaut, politique de confidentialité transparente, navigateur et extensions intégrés disponibles | Juridiction américaine (soumise au droit de surveillance US et aux demandes FISA) ; dépend de l'index Bing ; les raccourcis « !bang » redirigent directement vers des sites tiers (Amazon, Wikipédia) qui peuvent te pister là-bas |
| **Brave Search** | États-Unis | Index indépendant (propre robot de Brave), complété par d'autres sources | Ne collecte pas de données personnelles, pas d'historique lié à un compte, pas de profilage publicitaire | Publicités optionnelles, non basées sur un profilage comportemental à long terme quand activées | « Privé par défaut », véritablement indépendant de Google/Bing, forte intégration avec le navigateur Brave, index indépendant en croissance | Juridiction américaine ; index plus jeune et plus petit que Google ou Bing ; certaines fonctions avancées (Brave Rewards, synchronisation) sont optionnelles mais nécessitent un compte |
| **Mojeek** | Royaume-Uni | Index totalement indépendant (propre robot, aucune dépendance à Google/Bing) | Pas de pistage, pas de profilage utilisateur, pas de journalisation d'IP liée à une identité | Pas de ciblage publicitaire comportemental | Robot d'indexation véritablement indépendant (rare parmi les moteurs axés vie privée), basé au Royaume-Uni, politique transparente de non-pistage, option sans publicité disponible | Index plus petit que Google/Bing, donc couverture moindre pour les requêtes obscures ou de longue traîne ; juridiction britannique (considérations liées à l'Investigatory Powers Act) |
| **Qwant** | France (UE) | Propre index pour certaines catégories, Bing pour d'autres selon le type de requête | Pas de stockage d'IP, pas d'historique personnel lié à un compte, pas de cookies de suivi persistants | Publicités présentes, en principe contextuelles plutôt que fortement profilées | Hébergé en UE (encadré par le RGPD), alternative française et européenne, politique de « non-pistage » affichée, pas de revente de données personnelles | Modèle économique financé par la publicité ; dépendance partielle à Bing qui nuance la revendication d'indépendance totale ; a connu des instabilités financières et organisationnelles au fil des ans |
| **Ecosia** | Allemagne (UE) | Principalement Bing (avec quelques éléments d'index propre selon la configuration) | Ne vend pas de données, ne construit pas de profil publicitaire complet, mais conserve certains logs anonymisés et peut utiliser des cookies | Publicités présentes (finançant en partie la plantation d'arbres) ; ciblage limité mais non nul | Modèle économique orienté écologie, transparent sur son financement, pas de profilage agressif comparable à Google | Forte dépendance à Bing ; certaines données techniques (IP, etc.) transitent par l'infrastructure Microsoft ; protections de la vie privée plus faibles que Startpage, DDG ou Mojeek |
| **Yandex** | Russie | Index indépendant (vaste, principalement axé sur le contenu en langue russe mais avec une couverture mondiale) | Collecte de données étendue liée aux comptes et services Yandex ; utilisée pour la personnalisation publicitaire | Oui, publicités fortement ciblées dans tout l'écosystème Yandex | Grand index indépendant (véritable alternative à Google/Bing en termes d'échelle) | Juridiction russe avec des préoccupations d'accès légal et de souveraineté des données ; collecte de données importante ; généralement déconseillé pour un usage axé sur la vie privée |
| **Google** | États-Unis | Propre index massif | Construit un profil très détaillé (historique de recherche, localisation, activité YouTube, métadonnées Gmail si lié, pistage inter-appareils) | Publicités fortement ciblées basées sur ton profil complet | Pertinence de premier plan, intégration profonde de l'écosystème | Vie privée très faible : pistage extensif, corrélation des données entre services, conservation longue des données |
| **Bing** | États-Unis (Microsoft) | Propre index | Profilage utilisateur lié au compte Microsoft et à l'activité de navigation | Publicités ciblées basées sur le profil Microsoft/Windows/Edge | Forte intégration avec Windows, Office, Edge | Pistage et profilage significatifs, juridiction américaine |
| **Yahoo** | États-Unis | Principalement propulsé par Bing (via partenariat) | Conserve des logs, construit des profils publicitaires | Publicités ciblées | Portail généraliste (mail, actualités, etc.) | Vie privée faible ; hérite du pistage de Bing en plus de sa propre couche Yahoo/Verizon Media |

---

## 🏆 Classement vie privée uniquement (du meilleur au pire)

Classé purement sur la protection de la vie privée, pas sur la pertinence, pas sur l'éthique ou l'environnement, pas sur l'indépendance vis-à-vis des grands index.

1. **SearXNG auto-hébergé** : aucun serveur tiers ne te profile jamais ; tu décides quels moteurs sources interroger, et tu contrôles chaque log. La configuration la plus solide possible, surtout combinée à un VPN ou à Tor pour aussi cacher ton IP de ton FAI.

2. **Startpage** : politique stricte de non-pistage, pas de stockage d'IP, pas de profil à long terme, et livre l'index de Google sans que Google ne voie jamais le demandeur réel.

3. **Mojeek** : robot d'indexation totalement indépendant avec une politique de non-pistage claire, l'un des rares moteurs à être à la fois respectueux de la vie privée *et* indépendant de l'index de Google ou Bing.

4. **DuckDuckGo** : excellent choix pour un moteur grand public sans configuration : pas de compte requis, pas de revente de données, publicités non basées sur un profil persistant. Les principales réserves sont la juridiction américaine et la dépendance à Bing.

5. **Brave Search** : « privé par défaut » avec un index véritablement indépendant et aucun profilage publicitaire. Toujours basé aux États-Unis, mais la politique est sans ambiguïté.

6. **Qwant** : hébergé en UE (RGPD), pas de cookies de suivi, pas de revente de données, mais le modèle financé par la publicité et la dépendance partielle à Bing le placent un cran en dessous de Startpage, DDG ou Mojeek sur des critères techniques stricts.

7. **Ecosia** : position raisonnable sur la vie privée avec un angle écologique, mais la forte dépendance à Bing et certaines données techniques conservées le rendent moins strict que les moteurs précédents.

8. **Bing** : véritable profilage utilisateur et publicité ciblée liés à un compte Microsoft, bien que sur certains aspects un peu moins agressif que Google.

9. **Yahoo** : historique de pratiques de pistage, dépendant de Bing en plus de sa propre couche publicitaire, vie privée globalement faible.

10. **Yandex** : grand index indépendant mais collecte de données importante et juridiction avec de réelles préoccupations d'accès aux données.

11. **Google** : le moteur le plus puissant et le plus pertinent, mais aussi celui qui construit le profil inter-services le plus détaillé. La position la plus faible du groupe en matière de vie privée.

---

## 🧠 Concepts clés expliqués

<details>
<summary><strong>Ce que signifie vraiment « pas de pistage »</strong></summary>

<br>

Une politique de confidentialité disant « nous ne te pistons pas » couvre généralement :
- Pas d'identifiant unique persistant lié à tes recherches entre les sessions
- Pas d'adresse IP stockée à long terme ou liée à un profil
- Pas de vente ou de partage de données personnelles avec des courtiers en données
- Pas de ciblage publicitaire comportemental basé sur l'historique de recherche

Cela ne signifie généralement **pas** qu'aucune donnée ne touche jamais un serveur : la plupart des moteurs traitent quand même ta requête en temps réel pour renvoyer des résultats, et peuvent conserver des logs anonymisés de courte durée pour prévenir les abus ou optimiser les performances.

</details>

<details>
<summary><strong>Métarecherche vs index indépendant</strong></summary>

<br>

- Les **moteurs de métarecherche** (SearXNG) n'indexent pas le web eux-mêmes, ils interrogent d'autres moteurs (Google, Bing, Brave, etc.) en ton nom et agrègent les résultats, en supprimant souvent les détails identifiants avant de transmettre la requête.
- Les **moteurs à index indépendant** (Google, Bing, Brave, Mojeek, Yandex) font tourner leurs propres robots d'indexation et maintiennent leur propre index, ce qui est coûteux et techniquement difficile, d'où le petit nombre de véritables index indépendants.
- Des moteurs comme DuckDuckGo, Qwant, Ecosia et Startpage sont des **hybrides** : ils ajoutent leur propre technologie de confidentialité et/ou un index partiel par-dessus l'index principal d'un autre moteur (généralement Bing ou Google).

</details>

<details>
<summary><strong>La juridiction, ça compte</strong></summary>

<br>

Le lieu où une entreprise est légalement établie détermine à quelles demandes de données gouvernementales elle peut être contrainte de se conformer :

- **Basés aux États-Unis** (Google, Bing, DuckDuckGo, Brave, Yahoo) : soumis aux procédures légales américaines, y compris les lettres de sécurité nationale et les ordonnances FISA, qui peuvent s'accompagner d'ordres de bâillon empêchant l'entreprise de même révéler la demande.
- **Basés en UE** (Startpage, Pays-Bas ; Qwant, France ; Ecosia, Allemagne) : encadrés par le RGPD, qui impose une minimisation stricte des données, une limitation de finalité et des droits utilisateurs (accès, suppression, portabilité).
- **Basé au Royaume-Uni** (Mojeek) : soumis à l'Investigatory Powers Act, qui accorde des pouvoirs de surveillance et de collecte en masse plus larges que les juridictions encadrées uniquement par le RGPD.
- **Basé en Russie** (Yandex) : soumis aux lois russes de localisation des données et aux mécanismes d'accès des services de sécurité (par exemple SORM), un profil de risque très différent des juridictions occidentales.
- **Auto-hébergé** : la juridiction est celle où *toi* tu l'héberges, un avantage réel si tu contrôles ce choix (par exemple un VPS dans un pays respectueux de la vie privée, ou ton propre serveur à domicile derrière ton propre réseau).

</details>

<details>
<summary><strong>Le fingerprinting : le pistage qui survit aux cookies et aux VPN</strong></summary>

<br>

Même sans cookies ni compte connecté, ton navigateur expose une combinaison de caractéristiques (résolution d'écran, polices installées, particularités de rendu GPU/canvas, fuseau horaire, langue, extensions installées) qui forment ensemble une **empreinte** suffisamment unique pour te ré-identifier à travers les sessions, et même à travers différentes adresses IP. Un moteur de recherche respectueux de la vie privée réduit le pistage *côté serveur*, mais ne protège pas en soi contre le fingerprinting ; cela demande un durcissement au niveau du navigateur (par exemple Firefox avec `resistFingerprinting`, ou un navigateur résistant au fingerprinting comme Tor Browser).

</details>

---

## 🎯 Modèles de menace : contre qui te protèges-tu ?

Tout le monde n'a pas besoin du même niveau de protection. Sois honnête sur ton véritable modèle de menace : sur-ingénierier ta configuration peut ajouter de la friction sans réellement améliorer ta vie privée, alors qu'une sous-ingénierie laisse de vraies failles.

| Modèle de menace | Qui est concerné | Configuration recommandée |
|---|---|---|
| **Entreprises publicitaires / courtiers en données** | La plupart des gens qui ne veulent simplement pas être profilés à des fins publicitaires | DuckDuckGo ou Startpage comme moteur par défaut du navigateur, gain rapide, friction minimale |
| **L'opérateur du moteur de recherche lui-même** | Quiconque ne veut pas qu'une seule entreprise (Google en particulier) construise un profil comportemental de toute une vie | Startpage, Mojeek ou Brave Search, des politiques de non-pistage réelles |
| **Ton FAI / opérateur réseau** | Personnes sur des réseaux partagés, surveillés ou non fiables (travail, école, certains pays) | Ajoute un VPN ou Tor par-dessus n'importe quel moteur respectueux de la vie privée, le moteur seul ne cache pas ton trafic à ton réseau |
| **Surveillance gouvernementale / demandes légales** | Journalistes, militants, personnes dans des juridictions à haut risque | SearXNG auto-hébergé + Tor, hébergé dans une juridiction hors de portée légale de ta menace |
| **Accès physique à l'appareil (quelqu'un utilisant ton ordinateur)** | Appareils partagés, ordinateurs familiaux | Le mode privé/navigation privée du navigateur suffit, c'est un problème différent du pistage côté serveur |

---

## 🧭 Comment choisir selon ton usage

**Vie privée maximale, à l'aise techniquement :**
→ **SearXNG auto-hébergé**, idéalement associé à un VPN ou Tor pour aussi cacher ton IP à ton FAI. C'est le plafond en matière de vie privée parmi les options de recherche.

**Vie privée maximale, configuration simple :**
→ **Startpage** (résultats qualité Google, aucun profilage) ou **Mojeek** (totalement indépendant, sans pistage). Les deux fonctionnent bien comme moteur par défaut sans effort technique.

**Meilleur choix grand public, sans prise de tête :**
→ **DuckDuckGo**, le chemin de migration le plus simple pour quitter Google, Bing ou Yahoo, quasiment sans courbe d'apprentissage.

**Tu veux spécifiquement un moteur européen :**
→ **Qwant** (France) ou **Startpage** (Pays-Bas) pour des options axées vie privée en UE, ou **Ecosia** (Allemagne) si l'aspect environnemental compte aussi pour toi.

**Tu veux éviter entièrement les index Google et Microsoft/Bing :**
→ **Brave Search** ou **Mojeek** pour des index indépendants, ou **SearXNG** configuré pour interroger des sources hors des géants du numérique.

**Tu veux juste quelque chose de mieux que Google sans trop y réfléchir :**
→ **DuckDuckGo** ou **Startpage** comme moteur par défaut de ton navigateur, déjà une grande amélioration de la vie privée par rapport à Google, Bing ou Yahoo, sans aucune configuration.

**Tu es développeur, chercheur ou utilisateur avancé :**
→ **SearXNG auto-hébergé** te donne un contrôle total sur les moteurs sources, la mise en cache des résultats, et même un accès type API pour l'automatisation ou l'intégration dans d'autres outils.

---

## 🛠️ Conseils pratiques d'installation

- **Combine les couches** : un moteur de recherche respectueux de la vie privée + un navigateur respectueux de la vie privée (Brave, Firefox durci, LibreWolf) + un VPN ou Tor couvrent différents vecteurs de menace (profilage par le moteur, fingerprinting du navigateur, pistage au niveau du FAI ou du réseau), utiliser un seul de ces éléments ne couvre pas les autres.
- **Instances publiques de SearXNG** (listées par exemple sur searx.space) : un compromis intéressant, mieux que d'utiliser Google directement, mais tu fais confiance à la configuration et aux pratiques de journalisation de l'opérateur de cette instance, ce n'est pas équivalent à l'auto-hébergement.
- **Réglages par défaut du navigateur** : la plupart des navigateurs permettent de définir un moteur de recherche par défaut et même d'ajouter des moteurs personnalisés via OpenSearch, utile pour basculer rapidement entre Startpage, Mojeek, DDG ou ta propre instance SearXNG selon le contexte.
- **Les comptes connectés annulent tout** : si tu restes connecté à un compte Google ou Microsoft dans le même navigateur en utilisant un moteur « privé », le pistage inter-sites et les identifiants liés au compte peuvent quand même relier ton activité à toi. Utilise des profils de navigateur ou des conteneurs séparés si tu as besoin d'une séparation stricte.

---

## 🐳 Auto-héberger SearXNG, en profondeur

Pour quiconque gère sa propre infrastructure (VPS, homelab, Proxmox, hôte Docker), l'auto-hébergement de SearXNG est l'action à plus fort impact de cette liste.

### Comment ça marche
SearXNG est un **moteur de métarecherche** : il n'indexe pas le web lui-même. Il transmet plutôt ta requête à une liste configurable de moteurs sources (Google, Bing, Brave, DuckDuckGo, Wikipédia, Startpage, et bien d'autres), supprime les en-têtes et paramètres identifiants avant de la transmettre, agrège les résultats, les déduplique, et renvoie une seule page de résultats propre, sans qu'aucun moteur source ne te voie jamais directement, seulement le serveur SearXNG.

### Déploiement typique
- Fonctionne comme un **conteneur Docker** léger (image officielle disponible) ou comme un service Python/uWSGI en bare-metal
- Nécessite un **reverse proxy** (nginx ou Caddy) devant lui avec HTTPS s'il est exposé sur internet
- La configuration se trouve dans un seul fichier `settings.yml` où tu peux :
  - Activer ou désactiver chaque moteur source individuellement
  - Définir le comportement de mise en cache des résultats
  - Contrôler la journalisation (ou la désactiver entièrement)
  - Fixer des limites de débit pour éviter les abus si exposé publiquement
  - Personnaliser le thème de l'interface et les catégories de recherche par défaut (web, images, actualités, cartes, etc.)

### Pourquoi l'auto-hébergement surpasse même le meilleur moteur tiers axé vie privée
Chaque moteur tiers, aussi stricte que soit sa politique affichée, nécessite en dernier lieu de la **confiance** : tu fais confiance au fait que Startpage n'enregistre vraiment pas les IP, que Mojeek ne construit vraiment pas de profils, que leur politique affichée correspond à leur comportement réel côté serveur, et qu'aucun des deux ne sera jamais contraint ou compromis de manière à modifier silencieusement ce comportement. L'auto-hébergement supprime entièrement cette nécessité de confiance : les logs (ou leur absence) sont prouvablement ce que tu as configuré, parce que c'est toi qui fais tourner le serveur.

### Compromis à connaître
- Tu es responsable de la **disponibilité, des mises à jour et de la sécurité** de l'instance
- Certains moteurs sources (notamment Google) tentent activement de détecter et bloquer le trafic automatisé ou relayé, ce qui peut nécessiter un ajustement occasionnel de la configuration (rotation des user agents, limitation de débit) pour maintenir un flux de résultats fiable
- La qualité des résultats dépend uniquement des moteurs sources activés, désactiver tout sauf de petits moteurs indépendants réduira la couverture

---

## ⚠️ Erreurs fréquentes qui ruinent ta vie privée

- **Utiliser un moteur de recherche privé tout en restant connecté à Google ou Microsoft dans le même navigateur** : le pistage lié au compte peut quand même te suivre.
- **Croire que le « mode navigation privée » te cache du moteur de recherche** : il empêche seulement l'historique local du navigateur ; le serveur voit toujours ton IP et ta requête exactement comme avant.
- **Utiliser les `!bangs` de DuckDuckGo sans réaliser qu'ils redirigent directement vers le site cible** (Amazon, YouTube, etc.), qui te piste ensuite exactement comme il le ferait normalement.
- **Faire tourner une instance publique de SearXNG que tu ne contrôles pas en pensant que c'est équivalent à l'auto-hébergement** : tu fais confiance à la configuration et aux pratiques de journalisation d'un inconnu.
- **Ignorer le fingerprinting du navigateur** : changer de moteur de recherche ne fait rien pour arrêter le pistage basé sur l'empreinte à travers les sites ; c'est un problème au niveau du navigateur qui nécessite un durcissement séparé.
- **Oublier la couche réseau** : un moteur de recherche respectueux de la vie privée ne cache pas ton trafic à ton FAI ou à ton opérateur réseau ; cela nécessite un VPN ou Tor en plus.

---

## ❓ FAQ

**DuckDuckGo est-il vraiment privé, ou c'est juste du marketing ?**
Sa politique affichée est réellement solide (pas d'historique lié à un compte, pas de revente de données, pas de profilage publicitaire à long terme), et c'est une amélioration réelle et significative par rapport à Google. Les principales réserves sont la juridiction américaine et la dépendance à l'index de Bing.

**Un VPN suffit-il à lui seul, sans changer de moteur de recherche ?**
Non. Un VPN cache ton IP et ta localisation au moteur de recherche et à ton FAI, mais le moteur de recherche lui-même peut toujours construire un profil à partir de tes requêtes, de tes cookies et de tes connexions à des comptes, quelle que soit l'IP d'où vient la requête.

**Utiliser Tor rend-il n'importe quel moteur axé vie privée « parfait » ?**
Ça se rapproche beaucoup de l'anonymat au niveau réseau, mais Tor n'empêche pas un moteur de faire du fingerprinting sur ton navigateur ou de corréler des requêtes au sein d'une même session. Combiner Tor avec un moteur véritablement sans pistage (ou SearXNG auto-hébergé) est à peu près ce qu'il y a de plus solide pour la plupart des modèles de menace.

**Pourquoi Yandex n'est-il pas mieux classé malgré son propre index indépendant ?**
L'indépendance de l'index est une dimension de la « vie privée vis-à-vis des géants du numérique », mais elle ne dit rien sur *la quantité de données collectées par l'opérateur lui-même*. Yandex collecte massivement pour la personnalisation publicitaire et opère sous le droit russe d'accès aux données, deux éléments qui pèsent plus lourd que le bénéfice de l'indépendance de l'index dans un classement axé sur la vie privée.

**Ça vaut le coup de changer si je « n'ai rien à cacher » ?**
La vie privée ne consiste pas à cacher des actes répréhensibles, elle consiste à contrôler qui a le droit de construire un profil de tes centres d'intérêt, tes problèmes de santé, tes finances et tes relations, et qui a le droit de monétiser, vendre, ou être contraint de remettre ce profil. Le raisonnement « je n'ai rien à cacher » passe à côté du fait que la valeur de la vie privée réside dans le pouvoir et le contrôle sur tes propres données, pas dans la culpabilité.

---

## 📖 Glossaire

| Terme | Signification |
|---|---|
| **Moteur de métarecherche** | Un moteur qui agrège les résultats d'autres moteurs de recherche plutôt que d'indexer le web lui-même (par exemple SearXNG) |
| **Fingerprinting** | Identifier un appareil ou un navigateur via une combinaison de caractéristiques techniques, sans dépendre des cookies |
| **FISA** | Loi américaine sur la surveillance du renseignement étranger, base légale de certaines demandes de données du gouvernement américain aux entreprises |
| **RGPD** | Règlement général sur la protection des données de l'UE, loi stricte de protection des données encadrant les entreprises basées dans l'UE |
| **SORM** | Système russe d'interception légale des communications électroniques par les services de sécurité |
| **Bang (!bang)** | Un raccourci de DuckDuckGo qui redirige ta requête directement vers le moteur de recherche propre à un autre site (par exemple `!w` pour Wikipédia) |
| **Proxy anonymisant** | Un serveur qui transmet ta requête à un autre service sans révéler ton identité ou ton IP à ce service (utilisé par Startpage pour les résultats Google) |
| **Courtier en données** | Une entreprise qui collecte et vend des données personnelles agrégées provenant de multiples sources |

---

## 📚 Sources

- [PrivacyTools.io, moteurs de recherche privés](https://privacytools.io/fr/private-search)
- [Experte.com, moteurs de recherche anonymes](https://www.experte.com/fr/securite-informatique/moteurs-recherche-anonyme)
- [Panda Security, meilleurs moteurs de recherche pour la vie privée](https://www.pandasecurity.com/fr/mediacenter/les-10-meilleurs-moteurs-de-recherche-pour-la-vie-privee/)
- [BeVisible, alternatives à Google](https://www.bevisible.fr/alternatives-a-google/)
- [Norton, meilleurs moteurs de recherche privés](https://us.norton.com/blog/privacy-tips/best-private-search-engines)

---

*Cette comparaison se concentre spécifiquement sur la vie privée, pas sur la pertinence brute de recherche, les pratiques commerciales éthiques ou l'impact environnemental, bien que ces aspects soient mentionnés là où ils croisent la question de la vie privée (par exemple les modèles financés par la publicité).*
