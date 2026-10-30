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