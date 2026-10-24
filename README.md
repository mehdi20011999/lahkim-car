# Lahkim Car — Site web

Site vitrine de **Lahkim Car**, location de voitures à Casablanca, Sidi Moumen (Résidence El Boustane, MS 11, Imm F3, N°40). Ouvert 24h/24 selon la fiche Google.
Site statique : HTML, CSS et JavaScript, sans framework et sans build.

## Fonctionnalités

- 3 langues : **français, anglais, arabe** (l'arabe s'affiche de droite à gauche)
- La langue est choisie dans cet ordre : lien `?lang=fr|en|ar`, puis le dernier choix du visiteur, puis la langue du navigateur
- Formulaire de réservation qui ouvre **WhatsApp** avec la demande déjà écrite
- Flotte filtrable (Économique, Berline, SUV, Familiale), avec un bouton « Devis » WhatsApp par voiture
- Services, étapes, avis Google, FAQ, carte Google Maps, bouton WhatsApp flottant
- Adapté au mobile, page 404, favicon, balises SEO et données structurées (schema.org)

## Structure

```
lahkim-car/
├── index.html            Page principale
├── 404.html              Page d'erreur
├── site.webmanifest
├── robots.txt
├── .nojekyll             Nécessaire pour GitHub Pages
└── assets/
    ├── css/style.css     Design (couleurs dans :root en haut du fichier)
    ├── js/i18n.js        Tous les textes en FR / EN / AR
    ├── js/app.js         Numéro WhatsApp, liste des voitures, logique
    └── img/              Logo et favicon
```

## Modifier le contenu

| Je veux changer…        | Fichier                 | Où                                    |
|-------------------------|-------------------------|---------------------------------------|
| Le numéro WhatsApp      | `assets/js/app.js`      | `CONFIG.whatsapp`                     |
| Les voitures            | `assets/js/app.js`      | tableau `FLEET`                       |
| Un texte                | `assets/js/i18n.js`     | même clé dans `fr`, `en` et `ar`      |
| Les questions de la FAQ | `assets/js/i18n.js`     | tableau `faq` de chaque langue        |
| Les couleurs            | `assets/css/style.css`  | variables `--red` (Majorelle), `--saffron`, `--terra` |
| Le téléphone affiché    | `index.html`            | chercher `+212 6 61 08 11 02`         |

## Tester en local

Ouvrez `index.html` dans le navigateur, ou lancez :

```bash
python3 -m http.server 8000
# puis http://localhost:8000
```

## Mettre en ligne

**GitHub Pages**
```bash
git init
git add .
git commit -m "Site Lahkim Car"
git branch -M main
git remote add origin https://github.com/<utilisateur>/lahkim-car.git
git push -u origin main
```
Ensuite, sur GitHub : Settings → Pages → Branch `main`, dossier `/ (root)`.

**Vercel** : importez le dépôt, sans configuration (projet statique).

## À valider avec l'agence avant la mise en ligne

- La liste des voitures : seule la Renault Megane automatique est confirmée (un avis client), les autres sont des exemples. De vraies photos si possible
- Les services : aller simple, livraison à domicile
- Les tarifs, s'ils veulent les afficher
- Les réponses de la FAQ : documents, caution, aller simple
- La traduction arabe, à faire relire par un arabophone
