# bundle-firmup

Complète automatiquement les bundles « 4 accounts » de Swiss Firmup : pour chaque commande
payée d'un bundle, le script crée les comptes manquants (jusqu'à 4) dans le même programme
que le compte créé par le checkout. Relancer le script ne crée jamais de doublons.

## Réglages

- **Secret** `YPF_API_KEY` (Settings › Secrets and variables › Actions › Secrets) :
  clé API client YourPropFirm. Elle n'est jamais écrite dans le dépôt.
- **Variable** `YPF_API_BASE_URL` (facultative, onglet Variables) : adresse de l'API si
  ce n'est pas celle de `config.json` (par exemple l'adresse sandbox).
- `config.json` : produits bundle, date de départ (`start_at`), fenêtre de recherche,
  limite de sécurité par passage.

## Utilisation

Onglet **Actions** › *Bundles 4 comptes* › **Run workflow** :

- `simulation` : liste ce qui serait créé, ne crée rien ;
- `reel` : crée les comptes manquants.

Le passage automatique (toutes les 30 min) est prêt dans
`.github/workflows/bundles.yml` ; il suffit de décommenter le bloc `schedule`.
