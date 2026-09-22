# OpenG7 Knowledge Core — architecture

## Mission et état

Fournir mémoire souveraine, provenance, recherche hybride et graphe de connaissances à OpenG7.
Le dépôt contient actuellement cadrage et gouvernance. Les modules décrits
dans le [README](../README.md) sont une architecture cible, pas du code livré.
Aucun build applicatif n’est disponible avant ajout de ses manifests et sources.

## Frontières

Ce dépôt possède ingestion, recherche et provenance; les consommateurs utilisent ses contrats publics. Il ne devient ni un moteur d’exécution d’agents ni un routeur de modèles.

API/worker → ingestion et retrieval → modèles/provenance/politiques → ports → connecteurs, index, embeddings, graphe et stockage. Le SDK expose des contrats, jamais une dépendance directe aux moteurs de stockage.

## Invariants de conception

Appliquer les [invariants du projet](../AGENTS.md#périmètre-local) aux contrats,
aux adaptateurs et à leurs tests; ils restent définis à cet endroit unique.

## Évolution

Garder les contrats de domaine indépendants des fournisseurs et les effets dans
les adaptateurs. Pour matérialiser un module, documenter ses entrées/sorties,
consommateurs, permissions, état d’implémentation et validations disponibles.
Mettre à jour cette frontière si elle change; les consignes d’exécution restent
dans [AGENTS.md](../AGENTS.md), sans recopier une autre stack.
