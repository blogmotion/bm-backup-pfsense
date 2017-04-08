bm-backup-pfsense (blogmotion backup pfsense)
===
> english version below

### Description
Ce script permet de sauvegarder la configuration d'un pare-feu pfSense, en récupérant à distance le fichier XML via HTTP(S).

Deux versions du script existent, l'une est basée sur le binaire wget et l'autre sur cURL (plus rapide).
Suivant si l'un ou l'autre binaire est présent, choisissez la version en adéquation.

## Variables
Vous devez éditer le script (nano, vim, etc.) pour saisir à minima :
- [X] IP ou le nom FQDN (sans slash de fin)
- [X] identifiant
- [X] mot de passe

Je vous recommande de créer un utilisateur dédié (System > User Manager) ayant à minima le privilège "WebCfg - Diagnostics: Backup & Restore".
Pour des questions de sécurité le compte "admin" est déconseillé (mot de passe en clair dans le script).

## 🚦 Configuration minimale
Nécessite 
- [X] shell ou bash
- [X] wget ou cURL

Fonctionne en théorie sur n'importe quelle distribution Linux. Testé sur Debian, CentOS, pfSense.

## Compatibilité
Ce script est compatible avec pfSense:
- [X] 2.3.x et plus
- [X] 2.2.x

Non testé sur les versions inférieures.

Validé avec les versions :
- [X] 2.3.3
- [X] 2.3.2
- [X] 2.3.1
- [X] 2.2.5

### 🚀 Utilisation
Il est recommandé de créer un répertoire dédié pour y stocker le script. 
Les configurations XML sont stockées dans un sous-répertoire dédié.

```
chmod +x bm-backup-pfsense-curl.sh
./bm-backup-pfsense-curl.sh
```

```
chmod +x bm-backup-pfsense-wget.sh
./bm-backup-pfsense-wget.sh
```


### [EN] Description
soon

