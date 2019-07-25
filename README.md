# clowder

Clowder (noun): A group of cats or other small felines. Because sometimes working with docker feels like herding cats.

```
Manage services/containers with docker-compose

Provided command will be run against the specified service, or against the entire project if no service is specified.

Usage clowder [-v] <project-name>[.<service-name>] <command>

Commands:
list          List all services within a project
list-running  List running services within a project
up            Create network/volumes/container (as required) and bring service up
down          Stop service and delete container
start         Alias of up
stop          Stop service, without deleting container
pull          Pull container sources
build         Build a container
update        Pull/build/start container
restart       Restart container
rm            Remove stopped container created by service
ps            Show information about running services in a project
check-update  Check whether a service can be updated

Example: clowder multimedia.lidarr update
```

## Example setup

Clowder is a primitive script and all the heavy lifting is done by docker-compose. This is intended to be nothing more than a simplistic script to make some commands easier to manage.

Clowder expects you to have a series of files named like `${service}-compose.json` (yes, I wrote it to use json. why? because my brain can't parse yaml).

Example directory structure:

```
project
|-clowder
|-service1-compose.json
|-service2-compose.json
|-service3-compose.json
```

Then run it like
```
./clowder service1 list-running
```
