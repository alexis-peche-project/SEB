# Société des Experts Bois — proposition de refonte

Maquettes HTML statiques pour la refonte de l'annuaire d'experts de [experts-bois.com](https://www.experts-bois.com).
Aucun build, aucune dépendance à installer : ouvrir `index.html` ou publier le dossier sur GitHub Pages.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | Page « Trouver un expert » — recherche, filtres, carte Leaflet synchronisée avec la liste |
| `expert-laurent-fabregue.html` | Fiche expert enrichie, prise comme exemple |
| `assets/seb.css` | Feuille de style partagée |
| `assets/logo-seb.png` | Logo officiel, repalettisé (222 Ko → 29 Ko) |
| `assets/hero-charpente.jpg` | Bandeau de la charpente réticulée, recompressé |
| `audit-seo-experts-bois.md` | Audit SEO complet issu du crawl Screaming Frog du 26/08/2026 |

## Ce qui est réel et ce qui est maquette

**Réel :** les 8 experts de la première page de l'annuaire avec leurs coordonnées publiées, les 14 régions et 22 compétences avec leurs effectifs exacts, le logo, la photo du bandeau, la présentation et les compétences de Laurent Fabrègue.

**Maquette signalée :** sur la fiche expert, les blocs « types de missions » et « moyens techniques » portent la mention *exemple*. Ils illustrent les informations qui manquent aujourd'hui aux 73 fiches, pas des données fournies par l'expert.

## Parti pris visuel

La palette est extraite du logo — bleu d'encre `#0F3556`, bois `#C2A278`, ciel `#8FAFD2` — plutôt que du vert menthe actuel, qui ne s'y raccroche pas. Le vert n'est conservé que pour la mention « expert judiciaire », où il porte une information.

Typographie : Bricolage Grotesque en titrage, Public Sans en courant, IBM Plex Mono pour les données techniques (références de fiche, régions, téléphones).

Deux signatures :

- **Les fiches d'annuaire sont traitées comme des fiches techniques** : référence en monospace, filet bois sur le bord gauche, compétences en étiquettes plutôt qu'en listes imbriquées.
- **Les avatars des experts sans photo sont des cernes de croissance** générés à partir du nom. Ils remplacent l'initiale sur fond gris et rattachent la fiche au matériau. Le tracé est déterministe : un même nom donne toujours le même dessin.

## Améliorations fonctionnelles proposées

- Recherche par nom, ville, entreprise ou compétence, cumulable avec les deux filtres.
- Carte et liste synchronisées : survoler une fiche allume son marqueur, cliquer un marqueur ramène à la fiche.
- Compétences en étiquettes, avec un état explicite « compétences non renseignées » — visible sur trois des huit experts de la page 1, ce qui les rend aujourd'hui introuvables dès qu'un filtre est coché.
- Téléphones cliquables directement depuis la liste, sans passer par la fiche.
- Pied de page refondu avec des liens par région et par spécialité, qui servent à la fois la navigation et le maillage interne.
- Les liens `tel:` et `mailto:` du pied de page sont corrigés : le site actuel affiche un numéro et en compose un autre.

## Publication sur GitHub Pages

```bash
git init && git add . && git commit -m "Maquettes annuaire SEB"
git branch -M main && git remote add origin <url-du-depot> && git push -u origin main
```

Puis *Settings → Pages → Deploy from a branch → main / root*.
