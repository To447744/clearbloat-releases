# ClearBloat — téléchargements

Ce dépôt ne sert qu'à **distribuer les installeurs Windows de ClearBloat**.
Il ne contient aucun code source : le logiciel n'est pas open source.

**Page officielle de téléchargement :**
https://clearbloat-cloud.vercel.app/telechargement

Elle affiche l'empreinte SHA-256 du fichier réellement servi, un lien
d'analyse VirusTotal et la configuration requise. Passe par elle plutôt que
par la page « Releases » : elle vérifie que le fichier publié correspond bien
à celui qui a été relu avant publication, et refuse d'afficher un lien si ce
n'est pas le cas.

## L'installeur n'est pas signé

Windows affichera un écran bleu *« Windows a protégé votre ordinateur »*, puis
une demande d'autorisation portant la mention **« Éditeur inconnu »**.

Cette mention veut dire quelque chose de précis : **Windows ne peut pas
confirmer qui a publié ce fichier**. Ce n'est ni un faux positif, ni un bug.
Signer un logiciel demande un certificat payant qui n'a pas été acheté pour
cette bêta.

**Ne prends pas l'habitude d'ignorer cet écran** — il te protège réellement.
Pour ClearBloat, vérifie plutôt l'empreinte toi-même :

```powershell
Get-FileHash .\ClearBloat-<version>-x64-Setup.exe -Algorithm SHA256
```

Compare le résultat à celui affiché sur la page de téléchargement. S'ils
diffèrent, **n'installe pas**.

## Ce que fait le logiciel

ClearBloat modifie des réglages de Windows : registre, services, tâches
planifiées, paramètres d'alimentation. Il exige les droits administrateur.

Chaque modification est prévisualisée, sauvegardée et réversible, et les
réglages jugés dangereux sont exclus des profils automatiques. Cela ne
supprime pas tout risque : garde la restauration système activée.

ClearBloat n'aide en aucun cas à contourner un dispositif anti-triche.

## Licence

Tous droits réservés. Aucune licence de redistribution, de décompilation ou
de revente n'est accordée.
