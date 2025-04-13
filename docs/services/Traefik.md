# Traefik

## Adding traefik labels to unraid containers
- Add a new label with key `traefik.enable` and set value to `true`
- Add another label with key `traefik.http.routers.<appname>.entryPoints` and value `https`

## Manual proxying
Whether it's because the service is on another machine, or because it requires some different, setup, there are scenarios where you need to create a proxy manually, rather than having Traefik doing the discovery through docker tags.

## Changes on fileConfig.yml

```YAML
http:
## EXTERNAL ROUTING - Only use if you want to proxy something manually ##
routers:
	ollama:
		entryPoints:
			- https
		rule: 'Host(`ollama.mydomain.com`)'
		service: ollama
	openwebui:
		entryPoints:
			- https
		rule: 'Host(`chat.mydomain.com`)'
		service: openwebui
```

## References
- https://docs.ibracorp.io/traefik/master/unraid
- [Proxying Your First App by Ibracorp](https://docs.ibracorp.io/traefik/master/unraid/proxying-your-first-app)