# Procédure de Préparation pour le Parcours Web & IoT (mise à jour S1/S2 – version simplifiée)

Objectif
- Préparer un environnement minimal, clair et peu chargé cognitivement pour 60 élèves.
- Adopter une structure mono‑page (Option B), avec des chemins d'assets stables et simples.
- Conserver `.vscode/` (réglages simples) et éviter les dossiers vides.
- Laisser la "LICENCE MIT" en Extension Pro (optionnelle, non exigée au socle).

Contexte
- Utilisateur : @lidouni
- Postes : Gelés via Deep Freeze (peuvent être dégelés)
- Réseau : Atelier indépendant
- Élèves : Travail individuel, dépôt GitHub personnel
- Séances : S1 (prise en main/structure), S2 (init Git + premier push + README + commits), PR en extension.

Principes de simplification
- Montrer le minimum de dossiers/fichiers au départ.
- Créer les éléments avancés uniquement au moment où ils sont utiles (multi‑page, data, sql, docs…).
- Conserver des conventions cohérentes: CSS et JS sous `assets/`, mono‑page initiale.
- Ne pas ignorer `.vscode/` dans `.gitignore` (on versionne des réglages simples utiles à tous).

Phases
1) Préparation de l'infrastructure GitHub (dépôt "modèle" minimal – Option B)
2) Préparation du poste "Master" (image Deep Freeze)
3) Déploiement et vérification finale

---

## Phase 1 — Dépôt "modèle" (minimal S1–S2, Option B)

But: créer un template très simple, mono‑page, pour démarrer sans surcharge.

1. Créer le dépôt modèle
- Compte: @lidouni
- Nouveau dépôt public: `parcours-iot-template`
- Cocher "Add a README file"
- Ajouter un `.gitignore` (sera simplifié après clonage)
- Après push: Settings → activer "Template repository"

2. Cloner localement
```bash
git clone https://github.com/lidouni/parcours-iot-template.git
cd parcours-iot-template
```

3. Créer la structure minimale (Option B)
- Fichiers:
  - `README.md` (court)
  - `.gitignore` (minimal, voir plus bas)
  - `index.html`
  - `assets/css/style.css` (basique)
  - `assets/js/main.js` (basique)
- Dossiers conservés selon vos pratiques:
  - `.vscode/` (avec `settings.json` simple)
  - `assets/images/` seulement si des images existent (ne pas créer de `.gitkeep`)
- Ne PAS créer: `produits.html`, `contact.html`, `.github/`, `data/`, `docs/`, `sql/`, `scripts/`, `procedures/` dans le modèle élève.

4. Contenus minimalistes recommandés
- `.gitignore` (ne PAS ignorer `.vscode/`)
```gitignore
# OS
.DS_Store
Thumbs.db

# Éventuels builds/dépendances
node_modules/
dist/

# Logs
*.log
```

- `.vscode/settings.json` (simple)
```json
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.wordWrap": "on",
  "files.trimTrailingWhitespace": true,
  "editor.formatOnSave": true
}
```

- `assets/css/style.css` (base lisible)
```css
* { box-sizing: border-box; }
html, body { margin: 0; padding: 0; font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; line-height: 1.5; }
header, nav, main, footer { padding: 1rem; }
a { color: #0ea5e9; text-decoration: none; }
a:hover { text-decoration: underline; }
.container { max-width: 1000px; margin: 0 auto; padding: 0 1rem; }
```

- `assets/js/main.js` (point d'entrée minimal)
```js
console.log("app.js chargé");
document.addEventListener("DOMContentLoaded", () => {
  // Interactions à ajouter plus tard (S7)
});
```

5. Commit/push et activer le template
```bash
git add .
git commit -m "chore: starter minimal mono-page (S1–S2)"
git push
```
- Sur GitHub → Settings → cocher "Template repository"

Checklist Phase 1
- [ ] Dépôt `parcours-iot-template` public créé sur @lidouni
- [ ] Arborescence minimale S1–S2 poussée (mono‑page)
- [ ] `.vscode/` présent (settings simples) et NON ignoré
- [ ] `assets/images/` créé seulement si images disponibles (sans `.gitkeep`)
- [ ] `.gitignore` minimal en place
- [ ] "Template repository" activé
- [ ] URL du template prête à diffuser

---

## Phase 2 — Poste "Master" (image Deep Freeze)

But: un poste modèle prêt à l'emploi sans réinstallations hebdomadaires.

1. Dégeler le poste, redémarrer
2. Installer/mettre à jour
- Git for Windows
- VS Code
- Extensions VS Code: Live Server (essentiel). HTMLHint et Markdown All in One sont facultatives.
- DB Browser for SQLite (utile plus tard)
- Chrome/Firefox
3. Paramétrer Git (système)
- `init.defaultBranch = main`
- `credential.helper = manager` (Windows)
4. Tester
- `git --version`
- Cloner le template, ouvrir dans VS Code, lancer Live Server (`index.html`)

Checklist Phase 2
- [ ] Poste "Master" dégelé
- [ ] Git/VS Code/Extensions installés
- [ ] Credential Manager actif (connexion GitHub fluide)
- [ ] Live Server OK avec `index.html`
- [ ] Redémarrage test: tout persiste

---

## Phase 3 — Déploiement et Vérification

But: dupliquer l'image et valider un échantillon de postes.

1. Geler l'image du poste "Master"
2. Déployer l'image sur tous les postes
3. Vérifier 2–3 postes
- VS Code + extensions présentes
- `git --version` OK
- Accès GitHub OK (HTTPS)
4. Préparer les consignes S2 (affichage en classe)
- "Use this template" → nom dépôt `techstore-<nom>`
- `git clone` → `git add/commit` → `git push`
- README court (Objectif, Auteur)
- 3 à 5 commits courts et clairs (socle)
- PR/branche = Extension Pro (non obligatoire)
- LICENCE MIT = Extension Pro (non obligatoire)

Checklist Phase 3
- [ ] Image déployée sur tous les postes
- [ ] Sondage concluant (outils/accès OK)
- [ ] Consigne S2 imprimée/projetée (socle + extension pro)

---

## Arborescence minimale attendue (S1–S2, Option B)

```
parcours-iot-template/
├─ .vscode/
│  └─ settings.json
├─ assets/
│  ├─ css/
│  │  └─ style.css
│  ├─ js/
│  │  └─ main.js
│  └─ images/        (créer SEULEMENT si des images existent; sinon, ne pas créer)
├─ .gitignore
├─ README.md
└─ index.html
```

Éléments reportés (créer au moment opportun)
- Multi‑page (produits.html, contact.html) → séance dédiée ultérieure (ex: S3)
- `.github/` (templates Issues/PR) → quand vous lancez les PR (extension pro)
- `data/` (capteurs JSON) → S5
- `sql/` (schema/requêtes) → S12
- `docs/` (audits, captures, diagrammes) → S14
- LICENCE MIT → Extension Pro (ajout facultatif quand l'élève est prêt)

---

## Conduite de S2 (charge cognitive faible)

Socle minimal (prioritaire)
- Créer dépôt depuis le template (Use this template)
- Cloner localement
- `git add/commit` initial ("feat: init structure mono‑page")
- Lier et `git push` vers GitHub
- Enrichir `README.md` (Objectif + Auteur)
- Viser 3 à 5 commits courts et clairs

Extension Pro (si temps et autonomie)
- Créer 1 issue simple → 1 branche `feat/...` → petite modif → PR → merge
- Ajouter LICENCE MIT et un tag `v0.1.0`

Conseils pédagogiques
- Afficher 5 commandes clés (init, add, commit, remote/push, branch)
- Garder 10 min de fin de séance pour `git push`
- En cas de 403: utiliser la fenêtre d'auth GitHub (Credential Manager); PAT en dernier recours

---

## Go/No‑Go avant S2

- [ ] Le template minimal mono‑page (avec `.vscode/`) est prêt et fonctionnel
- [ ] Les postes ont VS Code, Git et Live Server opérationnels
- [ ] La consigne de nommage dépôt est fixée: `techstore-<nom>`
- [ ] La fiche "socle S2 + extension pro" est prête (projection ou PDF)
- [ ] (Option) Une démonstration rapide (clone → commit → push) est prête

---

Document maintenu par: @lidouni
Dernière mise à jour: 2025‑10‑14
