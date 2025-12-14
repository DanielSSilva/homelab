# Actual Budget

## What is it?

_Actual Budget is a super fast and privacy-focused app for managing your finances. At its heart is the well proven and much loved Envelope Budgeting methodology._ 

&emsp;&emsp;\- [Source](https://actualbudget.org/)

## Docker Compose
```yaml
networks:
  proxy:
	external: true

services:
  budget:
	image: actualbudget/actual-server:latest
	container_name: actual-server
	restart: unless-stopped
	networks:
	  - proxy
	ports:
	  - 5006:5006
	volumes:
	  - ${APPDATA_DIR}/actual-server:/data
	labels:
	  - traefik.enable=true
	  - traefik.http.routers.budget.entryPoints=https
	  - glance.name=Actual Budget
	  - glance.icon=si:actualbudget
	  - glance.url=https://budget.${DOMAIN_BASE_URL}
	  - glance.hide=false
	  - net.unraid.docker.icon=https://github.com/actualbudget/actual/raw/master/packages/desktop-electron/icons/icon.png
```

## References
- [Official Website](https://actualbudget.org/)
- [Documentation](https://actualbudget.org/docs/)
- [GitHub Repository](https://github.com/actualbudget/actual)