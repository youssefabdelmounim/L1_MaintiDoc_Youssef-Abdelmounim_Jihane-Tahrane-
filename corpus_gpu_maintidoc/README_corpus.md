# Corpus MaintiDoc v2 - plateforme IA de dépannage GPU (NVIDIA / AMD, PC de bureau et portables)

Corpus synthétique en français : **78 documents PDF** (304 pages, 3 pages minimum chacun) et **83 images** (13 schémas générés, 4 infographies sources, 66 panneaux découpés).

## Cas d'usage visé
L'utilisateur envoie du texte et des images (photo du matériel, capture d'écran, message d'erreur) sur un problème physique ou logiciel d'un GPU de PC de bureau ou de portable. L'agent répond par une explication et une solution :
- problème **physique** : explication, instructions pas à pas, mise en sécurité, escalade ; aucune action automatique ;
- problème **logiciel corrigeable** : plan d'actions du catalogue (GPU-064), demande d'autorisation (Autoriser / Refuser, panneau PNL-D20), exécution, vérification par mesures, journal ;
- problème logiciel non automatisable (BIOS, mode sans échec, flash) : instructions ;
- information insuffisante ou hors périmètre : clarification ou abstention (GPU-041, GPU-044).
Protocole complet : GPU-063. Catalogue d'actions ACT-01 à ACT-16 et actions interdites : GPU-064.

## Contenu
- `documents/` : GPU-001 à GPU-078. Chaque PDF = sections, tableau et/ou schéma, illustrations, compléments, scénarios, erreurs fréquentes, FAQ, références croisées, Annexe A (fiche de contrôle), Annexe B (fiche de relevé).
- `images/` : `*.png` (13 schémas IMG-xxx), `sources/` (SRC-A à SRC-D : les 4 infographies), `panels/` (PNL-A01 à PNL-D20 : 66 vignettes découpées).
- `images_manifest.json` : toutes les images (niveau, légende française, texte alternatif, mots-clés, documents liés ; pour les panneaux : libellé anglais d'origine, domaine, autonomie de l'agent, plateforme, mode de réponse).
- `panels_manifest.csv` : tableau des 66 panneaux.
- `manifest.json` / `manifest.csv` : documents (version, famille, type, groupes d'accès, pages, element_id table_/figure_/image_<page>_<n> avec image_id, image_ids).

## Niveaux d'autonomie de l'agent (champ agent_autonomy des panneaux)
- `agent_avec_autorisation` : logiciel (pilote, système, application) ; plan + autorisation.
- `instructions_utilisateur` : l'utilisateur agit, l'agent guide.
- `escalade_atelier` : dommage physique, atelier habilité ou RMA.
- `solution_illustree` : étape de solution à vérifier par des mesures.
- `interface_agent` : exemples d'interface (PNL-B16, PNL-D20), non des preuves.

## Documents de référence selon le symptôme
Index général : GPU-061. Panneaux et infographies : GPU-065. Pannes électriques : GPU-066, GPU-067. Thermique et bruits : GPU-068, GPU-069. Dommages graves : GPU-070. Pas de signal / non détecté / BIOS : GPU-071. Artefacts : GPU-072. Pilotes : GPU-073. Plantages : GPU-074. Performances : GPU-075. Firmware : GPU-076. eGPU et portable : GPU-077. Solutions de base : GPU-078.

## Remarques
- Les infographies et panneaux sont des **illustrations générées par IA** : valeurs, textes d'interface et logos sont illustratifs ; ils ne prouvent aucun diagnostic. GeForce Experience (citée) a été remplacée par NVIDIA App.
- Le panneau « Reflow » est traité comme une réinsertion (reseat) ; le chauffage d'une carte est exclu.
- Valeurs chiffrées, codes et commandes sont indicatifs : à valider sur les sources constructeur et sur la plateforme cible.
- Les images de test fournies précédemment (AIO, condensateur de TV hors périmètre, connecteur 600W, ports, artefacts, voyant rouge, carte affaissée, doigts PCIe, ventilateurs) restent couvertes par les documents GPU-001 à GPU-062 (voir GPU-061).
