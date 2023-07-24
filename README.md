# Ansible 

## Installation sur Ubuntu 22.04 LTS
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y software-properties-common sshpass
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt update
sudo apt install ansible
```

## Pour s'entrainer
Le script [deploy.sh](Script/deploy-ansible.sh) permet de créer à la volée des containers avec podman pour tester ses playbook sur du Debian.

[Vidéo de Xavki pour le script podman](https://www.youtube.com/watch?v=Ia9nwOLernk&list=PLn6POgpklwWoCpLKOSw3mXCqbRocnhrh-&index=129)


[ Dépôt Gitlab Xavki](https://gitlab.com/xavki/presentation-ansible-fr/-/tree/master/14-plateforme-dev-docker)

## Créer sa clef SSH
```bash
ssh-keygen -t rsa
```

## Copier sa clef sur les serveurs distant
```bash
ssh-copy-id $USER@IP_des_nodes
```
Si vous avez créer une clef a un autre endroit
```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub $USER@IP_des_nodes
```

### Créer des containers
Déployer 2 containers
```bash
./deploy.sh -c 2
```

Créer les fichiers pour démarrer

Cette commande crée un dossier ansible_dir qui contient l'inventaire le dossier host_vars et le dossier group_vars
```bash
./deploy.sh -a
```

Infos sur les containers
```bash
./deploy.sh -i
```

Stopper les containers
```bash
./deploy.sh -t
```

Destroy les containers
```bash
./deploy.sh -d
```

### Vérification de la présence des Hôtes
```bash
ansible -i inv.yml all -m ping   
```

output :
```bash
10.88.0.4 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
10.88.0.5 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

### Pour un inventaire en mode graphique
```bash
pip3 install ansible-inventory-grapher
sudo apt install graphviz graphicsmagick-imagemagick-compat
```
ensuite entrer la commmande suivante
```bash
ansible-inventory-grapher -i inventory.yml all | dot -Tpng | display png:-
```

## Youtube
[Playlist de Xavki pour tester tout ca](https://www.youtube.com/playlist?list=PLn6POgpklwWoCpLKOSw3mXCqbRocnhrh-)

Enjoy !!