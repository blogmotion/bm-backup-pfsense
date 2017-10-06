bm-backup-pfsense (blogmotion backup pfsense)
===
> english version below

### Description
Ce script permet de sauvegarder la configuration d'un pare-feu pfSense, en récupérant à distance le fichier XML via HTTP(S).

3 versions du script existent :
- une basée sur le binaire wget 
- une basée sur le binaire cURL (plus rapide)
- une basée sur le binaire cURL (plus rapide) version multi

Suivant si l'un ou l'autre binaire est présent, choisissez la version en adéquation.

La version multi permet de sauvegarder plusieurs pare-feu dans le même script.

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

_Note : la modification des variables BACKUP_RRD, BACKUP_PKGINFO, BACKUP_PASSWORD n'est pour l'instant pas supportée._

## Compatibilité
Ce script est compatible avec pfSense:
- [X] 2.3.x et plus
- [X] 2.2.x

Non testé sur les versions inférieures.

Validé avec les versions :
- [X] 2.3.4-RELEASE-p1
- [X] 2.3.3
- [X] 2.3.2
- [X] 2.3.1
- [X] 2.2.5

### 🚀 Utilisation
Il est recommandé de créer un répertoire dédié pour y stocker le script. 
Les configurations XML sont stockées dans un sous-répertoire dédié.

Version cURL:
```
chmod +x pfmotion_curl.sh
./pfmotion_curl.sh
```

Version cURL multi:
```
chmod +x pfmotion_curl_multi.sh
./pfmotion_curl_multi.sh
```

Version wget :
```
chmod +x pfmotion_curl_wget.sh
./pfmotion_curl_wget.sh
```


Le fichier de backup contient le nom du pare-feu :
```
/tmp/conf_backup/config-<nom-hote>_<domaine>-<YYYYmmJJHHMMSS>.xml
```
Exemple :
```
/tmp/conf_backup/config-pf_blogmotion.fr-20171007002812.xml
```

### [EN] Description
soon

