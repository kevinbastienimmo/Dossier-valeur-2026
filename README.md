# Site Dossier Valeur 2026 — Kévin Bastien

Site statique prêt pour **GitHub Pages**, **Cloudflare Pages** ou **Netlify**.

## Contenu
- `index.html` : landing page principale
- `styles.css` : design responsive mobile / ordinateur
- `script.js` : formulaire + consentement Google Tags
- `config.js` : URL du formulaire + balises Google Ads/Analytics
- `google-apps-script.gs` : backend gratuit pour envoyer les leads dans Google Sheets
- `confidentialite.html` : modèle de politique de confidentialité à compléter
- `mentions-legales.html` : mentions légales à compléter
- `assets/kevin-bastien.jpg` : recadrage de votre photo fournie, sans retouche du visage
- `assets/signature-originale.jpg` : visuel original fourni

## 1 — Tester localement
Ouvrez simplement `index.html` dans votre navigateur.

Le formulaire est volontairement bloqué tant que `formEndpoint` n'est pas configuré : aucune donnée n'est perdue ou envoyée par erreur.

## 2 — Recevoir les prospects gratuitement dans Google Sheets
1. Créez un Google Sheet vide.
2. Copiez son identifiant depuis l'URL :
   `https://docs.google.com/spreadsheets/d/ICI_L_ID/edit`
3. Dans le Sheet : **Extensions > Apps Script**.
4. Collez le contenu de `google-apps-script.gs`.
5. Remplacez `REMPLACER_PAR_ID_GOOGLE_SHEET` par l'identifiant de votre Sheet.
6. **Déployer > Nouveau déploiement > Application Web**.
7. Exécuter en tant que : **Moi**.
8. Accès : **Tout le monde**.
9. Copiez l'URL terminant par `/exec`.
10. Dans `config.js`, collez-la :

```js
formEndpoint: "https://script.google.com/macros/s/XXXXX/exec"
```

Les leads créeront automatiquement un onglet `Leads` avec : date, prénom, téléphone, e-mail, commune, type de bien, surface, projet, consentement, source, campagne et mot-clé.

## 3 — Mettre en ligne gratuitement sur GitHub Pages
1. Créez un compte GitHub si nécessaire.
2. Créez un dépôt public, par exemple `dossier-valeur-2026`.
3. Ajoutez tous les fichiers de ce dossier à la racine du dépôt.
4. Dans GitHub : **Settings > Pages**.
5. Source : **Deploy from a branch**.
6. Branche : `main` / dossier `/root`.
7. Enregistrez.

Après quelques minutes, le site sera disponible sur une adresse du type :
`https://votre-utilisateur.github.io/dossier-valeur-2026/`

## 4 — Cloudflare Pages (alternative gratuite)
Importez le même dépôt GitHub dans Cloudflare Pages. Aucun framework ni commande de build n'est nécessaire : le site est 100 % statique.

## 5 — Google Ads / Analytics
Dans `config.js`, vous pouvez renseigner :

```js
googleTagId: "AW-XXXXXXXXX",
adsConversionLabel: "XXXXXXXXXXXX"
```

Aucune balise Google n'est chargée avant l'acceptation du bandeau de consentement.

Pour conserver les mots-clés / campagnes dans le Google Sheet, utilisez des URLs avec paramètres UTM, par exemple :
`?utm_source=google&utm_campaign=estimation_le_pontet&utm_term=estimation_maison_le_pontet`

## 6 — Avant publication commerciale
À compléter impérativement :
- mentions légales professionnelles exactes ;
- SIREN/SIRET et RSAC si requis ;
- mentions réseau / carte professionnelle applicables à votre statut ;
- adresse professionnelle de correspondance ;
- durée de conservation des données ;
- sous-traitants et politique RGPD réelle ;
- identité officielle / logo du réseau uniquement dans le respect de votre charte.

## Coordonnées déjà intégrées
- Kévin Bastien
- Mandataire immobilier
- 06 52 18 42 33
- kevin.bastien@iadfrance.fr
- Le Pontet, Avignon, Vedène, Sorgues, Morières-lès-Avignon, Montfavet
- « Un avis juste. Une stratégie claire. Un projet réussi. »
