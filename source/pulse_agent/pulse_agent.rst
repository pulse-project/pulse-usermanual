=============
Agent Pulse
=============

| L'agent Pulse est composé de 5 services :
| -	FusionInventory : agent d'inventaire compatible « OCS »
| -	OpenSSH : serveur d'accès à distance « SSH »
| -	TightVNC : bureau à distance « VNC »
| -	Pulseagent : le service de l’agent pulse.
| -	Pulse Network Notify : Service qui permet de detecter des changements d’interfaces
| L’agent est décliné pour Windows, Mac et Linux.

Agent Windows
==============

| Par défaut lors de son installation, Pulse génère un ensemble d’agents :
|
| -	Pulse-Agent-windows-Minimal-Latest.exe	← Dernière version de l'agent interactif contenant le strict minimum. Lors de l’installation sur le serveur, l'agent va télécharger les dépendances et les composants nécessaires.
| -	Pulse-Agent-windows-Minimal-x.x.x.exe	← Agent interactif contenant le strict minimum tagué par version.
| -	Pulse-Agent-windows-Full-Latest.exe	← Dernière version de l'agent avec interaction et interface visible contenant l’ensemble des composants pour réaliser l’installation.
| -	Pulse-Agent-windows-Full-x.x.x.exe	← Agent avec interaction et interface visible tagué par version.
|
| Les agents sont accessibles depuis l’url suivante :
|	http://ippulse/dowloads/clients/win/

Génération des agents
----------------------

| Depuis la console Pulse se rendre :
| # cd /var/lib/pulse2/clients/
| # ./generate-pulse-agent.sh
| 
| Usage: 
| ./generate-pulse-agent.sh [--conf-xmppserver=<ip du serveur de configuration XMPP>] 
|         [--conf-xmppport=<port du serveur de configuration XMPP>] 
|         [--conf-xmpppasswd=<Mot de passe du serveur de configuration XMPP>] 
|         [--aes-key=<32-character AES PSK>] 
|         [--xmpp-passwd=<Mot de passe du serveur XMPP>] 
|         [--chat-domain=<Domaine XMPP>] 
|         [--inventory-tag=<Tag ajouté lors de l’inventaire>] 
|         [--minimal [--base-url=<URL utilisée pour télécharger l’agent et ses dépendances>]] 
|         [--disable-vnc (Désactiver le support vnc)] 
|         [--vnc-port=<Port VNC, par défaut 5900>] 
|         [--ssh-port=<Port SSH, par défaut 22>] 
|         [--disable-rdp (Désactiver le support RDP)] 
|         [--disable-inventory (Désactiver le support de l’inventaire)] 
|         [--linux-distros (Distributions linux utilisées)]

Agent et TAG
-------------

| L’agent Pulse peut être tagué afin d’offrir un discriminant supplémentaire.
|
| Il existe plusieurs façons de générer ce TAG :
| -	Déployer un TAG sur un ordinateur possédant déjà un agent Pulse
| -	Générer un agent Pulse avec un TAG

Déployer un TAG sur un ordinateur possédent déjà un agent Pulse
----------------------------------------------------------------

Il suffit de créer la clé de base de registre adéquate et utiliser Pulse pour la déployer.


Générer un agent Pulse avec un TAG
-----------------------------------------

| Il faut aller dans le dossier suivant :
| # cd /var/lib/pulse2/clients
| 
| Et générer l'agent Pulse avec le tag voulu (Exemple : bureau101)
| # ./generate-pulse-agent.sh --inventory-tag bureau101

Agent Mac
==========

| L’agent est accessible depuis l’url suivante :
| 	http://ippulse/dowloads/clients/mac/Pulse2AgentsInstaller.tar
|     
| Il faudra autoriser l’installeur à s’exécuter dans les paramètres de sécurité.
| Par ailleurs, en pré-requis avant d’installer le package Pulse, il faut que Xcode correspondant à votre version soit installé.

Générer un agent Pulse avec un TAG
-----------------------------------

| Similaire à Windows, il faut aller dans le dossier suivant :
| # cd /var/lib/pulse2/clients/
| 
| Puis lancer cette commande avec le TAG voulu (Exemple : bureau101)
| # ./generate-agent.sh --tag=bureau101

Agent Linux
============

| L’agent est accessible depuis l’url suivante :
| 	http://ippulse/dowloads/linux/Pulse-Agent-linux-MINIMAL-latest.sh

Générer un agent Pulse avec un TAG 
-----------------------------------

| La manipulation est la même que pour Mac :
|
| # cd /var/lib/pulse2/clients/
| # ./generate-agent.sh --tag=bureau101
