# Arch Linux Tips

## Maintenance

### Remove all packages no longer required as dependencies (orphans)

	pacman -R $(pacman -Qdt | awk '{ print $1 }' | tr '\n' ' ')

### Update mirror list

	sudo su -c "curl 'https://www.archlinux.org/mirrorlist/?country=US&protocol=https&ip_version=4&ip_version=6&use_mirror_status=on' | sed -e 's/^#Server = /Server = /g' -e '/^#/d' | head -n 6 > /etc/pacman.d/mirrorlist"

### Remove package cache

	pacman -Sc
