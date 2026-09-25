# Synchronisation vers le dépôt privé

Chaque nouvelle issue publique déclenche immédiatement le workflow `Envoyer le feedback vers Check Mate`.

Le workflow crée une issue miroir dans le dépôt privé `homebrw/checkmate` sans recopier aucun contenu privé vers ce dépôt public.

## Secret requis

Le workflow utilise le secret GitHub Actions :

`PRIVATE_FEEDBACK_TOKEN`

Il doit contenir un **fine-grained personal access token** limité à :

- propriétaire : `homebrw` ;
- repository access : **Only select repositories** → `checkmate` uniquement ;
- Repository permissions → **Issues: Read and write** ;
- aucune autre permission en écriture.

Ajoutez le secret dans :

`homebrw/checkmate-feedback → Settings → Secrets and variables → Actions → New repository secret`

Tant que ce secret n'est pas configuré, le workflow sort proprement et le polling privé reste le filet de sécurité.
