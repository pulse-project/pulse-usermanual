===========
Imaging
===========

| Cette section concerne la partie imaging de l'outil Pulse, avec notamment le boot en iPXE, la page d'accueil et les différentes options.
|
|

Boot initial
============================

| Lors du lancement d'une machine en amorçage PXE (sigle de Pre-boot eXecution Environment, qui permet à une station de travail 
| de démarrer depuis le réseau en récupérant une image de système d'exploitation qui se trouve sur un serveur)
| nous avons plusieurs choix qui s'offrent à nous.
|
| Tout d'abord, quand la machine n'est pas enregistrée (*Reconnaissable grâce au message "Host is NOT registered"*) :
|
| - L'option par défaut est "Continue Usual Startup", qui permet de booter la machine normalement. Cette option par défaut sera automatiquement
| sélectionnée après un certain temps, sauf si l'on appui sur une touche.

.. image:: images/continueUsual.png

|
| - La seconde option, "Register as Pulse client", permet d'enregistrer la machine en tant que client Pulse. Un inventaire de la machine va être fait et celle-ci
| sera intégrée à l'outil Pulse.

.. image:: images/register.png

|
| Une fois cette option sélectionnée, il est alors demandé d'entrer le nom de la machine :

.. image:: images/askingHostname.png

|
| S'en suit un message demandant si le nom est correct, afin d'éviter une quelconque erreur de typo par exemple (taper "Y" pour continuer ou "N" pour corriger le nom)

.. image:: images/correct.png

Machine enregistrée dans Pulse
===============================

| Une fois la machine enregistrée (*Reconnaissable grâce au message "Host _hostname_ registered!"*), nous pouvons :
|
| - Booter la machine normalement, avec l'option "Continue Usual Startup" (similaire à l'option du boot initial)

.. image:: images/continueUsualReg.png

|
| - Créer une sauvegarde de la machine

.. image:: images/createBackup.png

|
| - Ou encore de restaurer une image créée en amont sur la machine nouvellement créée. Dans notre exemple, le master s'appelle "master"

.. image:: images/master.png