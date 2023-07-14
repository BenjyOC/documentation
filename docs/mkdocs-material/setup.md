# Setup

La documentation officiel se trouve [ici](https://squidfunk.github.io/mkdocs-material/getting-started/)

On peut créer le dossier dans lequel il y aura la doc : `mkdir -p /srv/mkdocs-material/`

Ensuite on bootstrap le site :

```bash
cd /srv/mkdocs-material/
docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material new .
```

Il ne reste plus qu'à lancer le container via un docker-compose file :

```yaml title="docker-compose.yml"
doc:
	image: squidfunk/mkdocs-material
	container_name: mkdocs-material
	volumes:
		 - /srv/mkdocs-material/:/docs
	restart: always
	networks:
		- web
	labels:
		- "traefik.enable=true"
		- "traefik.http.routers.doc.rule=host(`doc.bracloud.fr`)"
		- "traefik.http.services.doc.loadbalancer.server.port=8000"
		- "traefik.http.routers.doc.entrypoints=websecure"
		- "traefik.http.routers.doc.tls.certresolver=myresolver"
```
