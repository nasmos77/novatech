# Réponses TP final Git

## Mission 5
1. Identifiant court du premier commit : `<cd739b8>`
2. Commit d'ajout de la page Contact : `<2a979dc>`
3. Nombre actuel de commits : 8
4. Historique sous forme graphique : `git log --oneline --graph --all --decorate`
5. Examen d'un commit de la fonctionnalité Contact : `git show <id>`

## Mission 8
- Commande : `git reset HEAD~1` (équivalent de `git reset --mixed HEAD~1`).
- Les modifications sont toujours présentes car reset déplace la branche sur le commit précédent et vide le staging.

## Mission 9
- Commande : `git revert HEAD`.
- Le commit étant déjà récupéré par l'équipe, il ne faut pas réécrire l'historique.
- Revert ajoute un nouveau commit qui applique l'inverse et conserve `Ajout promotion`.
- En mission 8, le commit n'était partagé avec personne : le retirer avec reset ne gênait personne.
## Mission 11
- Commande : `git cherry-pick -x <id>`.
- Commit récupéré : `<5a747ff>` sur test/experimentations (`<b3be67e9ae3daf3ddbe3e717d3bc4b387f6a2380>` sur main).
- Une fusion classique aurait aussi apporté les commits 1 et 3 (couleurs expérimentales et
  texte de test), qui ne doivent pas arriver sur la branche principale.

## Mission 12
- Le 1 de gauche (majeur) : changements importants, potentiellement incompatibles.
- Le 0 du milieu (mineur) : nouvelles fonctionnalités compatibles.
- Le 0 de droite (correctif) : corrections de bugs compatibles.

Versions suivantes à partir de 1.0.0 :
- Correction de bug mineur : 1.0.1
- Nouvelle fonctionnalité compatible : 1.1.0
- Refonte majeure : 2.0.0


## Réponses finales
- Zone de travail, staging, historique : la zone de travail contient les fichiers tels qu'ils sont sur le disque. Le staging contient la sélection préparée pour le prochain commit (git add). L'historique contient les commits enregistrés (git commit).

- Branche dédiée : le travail est isolé, la branche principale reste stable, plusieurs fonctionnalités peuvent avancer en parallèle, et une fonctionnalité peut être abandonnée sans impact.

- Reset ou revert : reset déplace la branche et retire le commit de l'historique, donc il réécrit l'historique et se réserve au travail non partagé. revert ajoute un commit inverse et conserve l'historique, donc il convient au travail partagé.

- Stash : quand il faut changer de tâche ou de branche en urgence alors que le travail en cours n'est pas prêt à être committé.

- Cherry-pick : il récupère une seule correction sans apporter les autres commits de la branche, qui peuvent être expérimentaux ou inachevés.

- HEAD : c'est le pointeur vers la position actuelle dans l'historique, en général le dernier commit de la branche courante.

- HEAD~2 : c'est le commit situé deux crans avant HEAD, en remontant par le premier parent.

- Tag : c'est un nom fixe posé sur un commit précis, par exemple pour marquer une version. Un tag annoté ajoute un auteur, une date et un message.

- Petits commits : ils sont plus faciles à comprendre, à relire et à annuler ou récupérer séparément, et ils aident à retrouver l'origine d'un bug.

- Fichiers non versionnés : les secrets (.env) resteraient lisibles dans l'historique. Les logs et le cache sont régénérables, propres à chaque machine, et alourdissent le dépôt.