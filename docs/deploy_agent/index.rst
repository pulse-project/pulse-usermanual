============================
Déploiement de l'agent Pulse
============================

| Cette section concerne la partie déploeiemnt de l'agent de l'outil Pulse.
|
|


| L'agent Pulse peut être installé via différentes méthodes :
| 
| -	GPO
| -	PsExec
| -	PXE

Déploiement par GPO
====================

| Il est possible de créer une GPO contenant l'agent Pulse et de la configurer pour que l'installation se lance au démarrage du poste.
| 
| Une vidéo explicative est disponible à cette adresse :
| https://vimeo.com/97123295

Déploiement via PsExec
=======================

| Un déploiement via PsExec est possible. Pour se faire, il faut utiliser la commande suivante :
| psexec \\ordi-cible -c agent-pulse.exe -u Administrateur -p password  
| 
| Il est à noter que cette méthode nécessite que les postes aient la clé suivante :
| HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\system /v LocalAccountTokenFilterPolicy /t REG_DWORD /d 1 /f

Déploiement via PXE
====================

| Il est également possible de déployer l'agent via PXE.
| Pour se faire, il faut transformer le script de post-imaging « Déployer les Agents Pulse » en un boot service et l'ajouter au menu par défaut de Pulse.
| 
| Il faut ensuite démarrer le poste en PXE, puis sélectionner « Déployer les Agents Pulse ». Lors du reboot du poste, l'agent Pulse s'installera automatiquement.
