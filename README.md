# B3 Devops - TP1

## Info
mail: thomas.flitterman@ynov.com  
github_username: tofl

## VMware
Sur VMware (Virtual Box ne marchant pas sur mon ordinateur), créer une nouvelle VM (`Cmd+m`). Choisir la bonne image et, dans la dernière étape d'importation de l'ISO, cliquer sur "Customize Settings". Dans "Processors & Memory", baisser la mémoire à 1024MB.

Avant d'installer NodeJS 12, il faut mettre à jour le dépôt APT:

```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```


Pour installer les paquets (OpenSSH, NodeJS et Nginx), utiliser APT:

```
sudo apt install openssh-server nodejs nginx
```

## Vagrant

Après avoir installé Vagrant, on lance la commande `vagrant up`. La configuration spécifiée dans le fichier `Vagrant` sera appliquée.