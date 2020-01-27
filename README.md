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

On personnalise le ficher /var/www/html/index.html en y plaçant le code suivant :

```html
<!DOCTYPE html>
<html>
    <head>
        <title>TP1 — Devops</title>
    </head>

    <body>
        <h1>TP 1 — Devops</h1>
        <p>It wrks !</h1>
    </body>
</html>
```

## Vagrant

Après avoir installé Vagrant, on lance la commande `vagrant up`. La configuration spécifiée dans le fichier `Vagrant` sera appliquée et le fichier `bootstrap.sh` sera aussi exécuté. Ce dernier installe tous les paquets nécessaires : openssh-server, NodeJS (version 12) et surtout Nginx.

Dans `Vagrant`, on rajoute des règles de redirection des ports :

- Lorsque l'utilisateur souhaite accéder au port 8080 dans son navigateur, il sera redirigé vers le port 80 qui correspond à HTTP.
- Le port 8081 redirigera à 443, qui correspond à HTTPS.
- Et le port 8082 redirigera au port 22 qui correspond à SSH.

Pour se connecter à la VM qui vient d'être créée, on peut utiliser `vagrant ssh` et pour la détruire, on peut utiliser `vagrant destroy`.