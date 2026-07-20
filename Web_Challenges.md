# Root-Me — Web Challenges


## Exercice 1 — Directory Traversal

**Lien** : https://www.root-me.org/fr/Challenges/Web-Serveur/Directory-traversal  
**Catégorie** : Web Serveur
**Difficulté** : Facile

**Technique** : Navigation dans l'arborescence du serveur via `../` pour accéder à des fichiers en dehors du répertoire web.

**Ce que j'ai appris** : L'accès aux fichiers sensibles doit être sécurisé même si le client ne les voit pas directement dans l'interface. Des attaques comme le directory traversal permettent de remonter l'arborescence du serveur et d'y accéder. Ce type d'attaque se détecte en surveillant les logs HTTP à la recherche de patterns ../ ou ..%2f dans les requêtes, et en déclenchant des alertes sur les tentatives d'accès à des chemins hors du répertoire web autorisé.

**Difficulté ressentie** : ==Facile== / Moyenne / Difficile

---

## Exercice 2 — PHP Injection de commande

**Lien** : https://www.root-me.org/fr/Challenges/Web-Serveur/PHP-Injection-de-commande
**Catégorie** : Web Serveur  
**Difficulté** : Facile

**Technique** : Injection de commandes système via un paramètre PHP non filtré.

**Ce que j'ai appris** : Tout champ de saisie utilisateur qui interagit avec le système (formulaires, barres de recherche, paramètres d'URL) est un vecteur d'attaque potentiel. Une injection de commande se produit quand l'entrée utilisateur est transmise directement à une commande système sans être filtrée — l'attaquant peut alors exécuter des commandes arbitraires sur le serveur. On peut s'en protéger grâce à la validation et au filtrage strict des entrées utilisateur, à l'utilisation de fonctions sécurisées qui n'appellent pas directement le shell, et à l'application du principe de moindre privilège sur les processus exécutés par le serveur web.

**Difficulté ressentie** : ==Facile== / Moyenne / Difficile

---

## Exercice 3 — Injection de commande — Contournement de filtre

**Lien** : https://www.root-me.org/fr/Challenges/Web-Serveur/Injection-de-commande-Contournement-de-filtre
**Catégorie** : Web Serveur  
**Difficulté** : Moyenne

**Technique** : Bypass de filtres de sécurité sur les injections de commandes.

**Ce que j'ai appris** : Certains filtres de sécurité ne couvrent pas tous les vecteurs d'injection de commande . Un attaquant peut contourner un filtre basique en utilisant des syntaxes alternatives pour obtenir le même résultat. Ce challenge m'a appris qu'un filtre par blacklist n'est jamais suffisant et qu'une approche par whitelist (n'autoriser que ce qui est attendu) est beaucoup plus robuste.

**Difficulté ressentie** : Facile / Moyenne / ==Difficile==

