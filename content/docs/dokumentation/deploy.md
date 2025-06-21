---
title: Deploy
weight: 50
draft: false
math: false
---

Um das Veröffentlichen von Änderungen zu vereinfachen, wird diese Seite über GitHub-Actions gebaut.
Dadurch müssen keine Zugangsdaten zum Webserver eingerichtet und ausgetauscht werden.
Auch ist eine lokale Installation von Hugo nicht zwingend erforderlich.

## Github-Action

Mit jedem Push in den Main-Branch des Repositories wird eine GitHub-Action ausgeführt.
Diese liegt in [`.github/workflows/hugo.yaml`](https://github.com/johannesbuehl/dokumentation/blob/main/.github/workflows/hugo.yaml) und beinhaltet im wesentlichen nur zwei Schritte:

1. Bauen mit `Hugo`
2. Mit `rsync` auf den Server kopieren

Hierzu sind in den Repository-Secrets ein Private-SSH-Key hinterlegt, mit welchem sich rsync beim Server authentifiziert.
