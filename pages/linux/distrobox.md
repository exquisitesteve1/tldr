# distrobox

> Use any Linux distribution inside your terminal by running it as a container.
> Created container will be tightly integrated with the host, allowing sharing of the HOME directory of the user, external storage, external USB devices and graphical apps (X11/Wayland), and audio.
> Uses `podman` or `docker` underneath
> You can install any software inside it. Eg: installing a `.deb` package inside an ubuntu container running on an Arch Linux host system. 
> Packages inside container can access host's files
> More information: <https://distrobox.privatedns.org>
> More command usage examples: <https://github.com/89luca89/distrobox/blob/main/docs/usage/usage.md>


- Create a distrobox using the Ubuntu Linux image:

`distrobox-create {{container_name}} --image {{ubuntu:latest}}`

- List all distrobox containers with verbose information:

`distrobox-list -v`

- Enter a distrobox:

`distrobox-enter {{container-name}}`

- Execute command on the host, while inside of a container:

`distrobox-host-exec {{command}}`

- Export an app (atom) from the container to the host (will show up in your host system's application list):

`distrobox-export --app {{atom}} --extra-flags "--foreground"`

- Export a binary(ranger) from the container to the host:

`distrobox-export --bin {{/usr/bin/ranger}} --export-path {{$HOME/.local/bin}}`

- Export a service (syncthing) from container to the host (`--sudo` will run the service as root inside the container):

`distrobox-export --service {{syncthing}} --extra-flags "--allow-newer-config" --sudo`

- Unexport/delete an exported app (atom)

`distrobox-export --app {{atom}} --delete`

- Upgrade a container using the container's package manager:

`distrobox-upgrade {{container_name}}`

- Clone a distrobox:

`distrobox-create --clone {{container_name}} {{cloned_container_name}}`

- Stop a distrobox container:

`distrobox-stop {{container-name}}`

- Remove a distrobox forcefully (to remove normally, don't include `--force`):

`distrobox-rm {{container_name}} --force`
