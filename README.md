# WAATH — Programme d'entraînement (app mobile)

App autonome hébergée sur GitHub Pages :
**https://sharpdev-admin.github.io/waath-programme/**

Programme hybride 4 semaines (congé paternité) — muscle + force + grip + skill double-unders.
5 phases (dont phase hôpital sans matériel), calendrier 28 jours, banque de 27 séances de
15-20 min, tracker double-unders, progression grip, et annexe de vidéos d'exécution WAATH.

## Modifier le programme (via Claude Code sur iOS)

1. Ouvre ce repo dans Claude Code.
2. Décris la modification (ex. « remplace la séance du J7 par une séance jambes »,
   « ajoute une séance grip le dimanche », « change l'objectif double-unders de la semaine 3 »).
3. Claude Code édite la donnée du programme **dans `index.html`**, à l'intérieur du bloc
   `<script id="program" type="application/json"> … </script>` (JSON).
4. Commit + push sur `main`.
5. GitHub Pages reconstruit automatiquement (~1 min) → l'app en ligne est à jour.
   Recharge la page sur l'iPhone pour voir les changements.

## Fichiers

- **`index.html`** — l'app complète et autonome (CSS + JS + données JSON embarqués).
  C'est CE fichier qui est servi en ligne. La donnée du programme est dans le bloc
  `<script id="program">`. Toute modif du programme doit passer par ce bloc.
- **`program.json`** — la même donnée, en version lisible (source de vérité pratique pour
  raisonner/éditer). Après l'avoir modifiée, il faut répercuter le contenu dans le bloc
  `<script id="program">` de `index.html` (Claude Code peut faire les deux d'un coup).

## Notes

- Les liens « Vidéos d'exécution WAATH » pointent vers les vraies vidéos YouTube WAATH.
- La progression (jours faits, records double-unders) est stockée en localStorage sur l'appareil.
- Source complète (scripts de build, wiki, analyses des agents) : repo privé `Personal-WAATH`.
