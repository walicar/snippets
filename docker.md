# docker commands

## The usual

* `docker run container-name`: create and run container
* `docker build -t image-name .`: build image
* `docker create --name container-name image-name`: create container from image
* `docker run -it image-name sh`: create container from image and shell into it

## Setting up Docker on MacOS

1. `brew install docker docker-compose docker-buildx colima`
2. add this to `~/.docker/config.json`; remove `credStore` line because IDK; add `cliPluginsExtraDirs` because `docker-compose` and `docker-buildx` are plugins
```json
{
	"auths": {},
	"currentContext": "colima",
	"cliPluginExtraDirs": [
		"/opt/homebrew/lib/docker/cli-plugins"
	]
}
```

3. `colima start`

## Clear all space...

```sh
docker system prune -a
```
