## How to use `xbps-src`
xbps-src used to build and install packages from source which is not in offical repo.

### Step 1: download template of the packages
```
git clone https://github.com/void-linux/void-packages
cd void-packages
```

### Step 2: Install build tools 
```
./xbps-src binary-bootstrap
```
NOTE: Build tools doesn't installed system-wide. The eviroment is chroot like env.

### Step 3: Build packages
```
sudo xbps-src <only_package_name>
```
### Step 4: Install package
```
sudo xbps-install -R hostdir/binpkgs/<only_package_name>
```


## Services
### List of all services
```
ls /etc/sv
```
### List of enabled services 
```
ls /var/service/
```
### Enable a service
```
ln -s /etc/sv/<service_name> /var/service/
```
### Remove(disable) a service
```
sudo rm /var/service/<service-name>
```
### Delete some ttys
```
sudo rm /var/service/agetty-tty[3-6]
```
### Service status
```
sudo sv status <service-name>
```

## Sound
### Record voice
```
arecord -d 5 -f cd test.wav
aplay test.wav
```


## Package Management
### xbps-query
### Query list
`sudo xbps-query -l`

### Package deps
what are the dependecies of the <pkg-name>
`sudo xbps-query -x <pkg-name>`

### Packages require the package
what packages are depend on <pkg-name>
`sudo xbps-query -X <pkg-name>`


## Doas instead of sudo
install doas
```
sudo xbps-install doas

# config doas
nvim /etc/doas.conf

# add this to doas.conf
permit persist :wheel
```

Force to remove sudo
`sudo xbps-remove -F sudo` 


Another way to delete sudo
(**Recommended** it didn't use this technique.)
```
# create 00-xbps-settings.conf file
nvim /etc/xbps.d/00-xbps-settings.con

# add this
ignorepkg=sudo

# remove sudo
sudo xbps-remove sudo
```



