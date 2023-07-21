# Ansible 

## Pour s'entrainer
Le script [deploy.sh](Script/deploy-ansible.sh) permet de créer à la volée des containers avec podman pour tester ses playbook sur du Debian.

[Vidéo de Xavki pour le script podman](https://www.youtube.com/watch?v=Ia9nwOLernk&list=PLn6POgpklwWoCpLKOSw3mXCqbRocnhrh-&index=129)


[ Dépôt Gitlab Xavki](https://gitlab.com/xavki/presentation-ansible-fr/-/tree/master/14-plateforme-dev-docker)

### Créer des container 
Déployer 2 containers
```bash
./deploy.sh -c 2
```

Créer son inventaire de container
```bash
./deploy.sh -a
```

Stopper les containers
```bash
./deploy.sh -t
```

Destroy les containers
```bash
./deploy.sh -d
```

## Youtube
[Playlist de Xavki pour tester tout ca](https://www.youtube.com/playlist?list=PLn6POgpklwWoCpLKOSw3mXCqbRocnhrh-)

<br>

Enjoy !!