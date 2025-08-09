# OSINT Password Challenge – DevBook

## Objectif
Sensibiliser les utilisateurs à la sécurité des mots de passe via un jeu interactif inspiré de l’OSINT. Chaque joueur lit une fiche utilisateur avec bio et indices cryptiques, puis tente de deviner le mot de passe.

---

## Modes de jeu
1. **Partie express** : 1 fiche.
2. **Campagne** : 5 fiches aléatoires.
3. **Options** :
   - **Mode du pendu** : indique le nombre de caractères corrects dans la tentative.
   - **Révéler les faits** : affiche des infos supplémentaires contre un coût en points.

---

## Difficulté
- **Facile**, **Moyen**, **Difficile** – choisies avant le début.
- Chaque niveau a son mot de passe et 3 indices cryptiques.

---

## Règles de scoring
- **Score initial par fiche** : 1000 points.
- **Drain** : –1.666 pt/sec (score tombe à 0 en 10 minutes).
- **Coûts** : Indice 1 (–100), Indice 2 (–150), Indice 3 (–200), Mauvaise réponse (–20), Révéler les faits (–50).
- **Bonus rapidité** :
  - < 30s → +100 pts
  - ≤ 60s → +50 pts
- Score fiche ajouté au score total à la validation.

---

## Fiche type
- **Profil** : Nom, âge, ville, métier, biographie.
- **Facts** : Infos publiques trouvées.
- **Passwords** :
  - `Facile` : valeur + 3 indices
  - `Moyen` : idem
  - `Difficile` : idem

---

## Fonctionnalités implémentées
- Écran d’intro avec choix du mode, difficulté et options.
- Affichage fiche profil + indices cryptiques verrouillés.
- Système de pénalités et animations (-XX qui s’envolent).
- Barre de progression avec drain du score.
- Mode du pendu (compte caractères corrects).
- Gestion campagne et express.
- Effets visuels (shake, pulse, glitch). (effet visuel lorsque l'on se trompe de mot de passe, utilise un indice... hop on voit [-50] si c'est 50 points en moins qui part de la partie score et qui monte dans l'écran en s'affadissant une peu comme pour un jeu vidéo)

---

## Fonctionnalités à implémenter / améliorer
1. **Centraliser les paramètres** (durées, coûts, bonus) dans un objet `RULES` configurable.
2. **Plus de fiches** avec indices bien pensés.
3. **Effets supplémentaires** (par ex. explosion de points gagnés).
4. **Gestion responsive avancée** pour mobiles.
5. **Sauvegarde des scores** et leaderboard.
6. **Accès JSON externe** pour ajouter facilement des fiches.
7. **Tests d’accessibilité** et clavier.

---

## Use cases
- **UC1** : Lancer une partie express et tenter un mot de passe sans indices.
- **UC2** : Lancer une campagne avec mode pendu et indices utilisés.
- **UC3** : Révéler les faits puis trouver le mot de passe.
- **UC4** : Jouer jusqu’à la fin du temps (score fiche = 0).
- **UC5** : Faire plusieurs erreurs pour tester les pénalités.

---

## Stack technique
- HTML/CSS/JS pur, aucune dépendance externe.
- Jeu contenu dans un seul fichier HTML.
- Données fiches dans un objet `GAME_DATA`.
