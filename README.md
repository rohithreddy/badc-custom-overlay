# badc-custom-overlay


[badc-custom-overlay]
 
# A Overlay for custom package ebuilds that are mostly ripped off shamelessly from other people repos 
 
location = /usr/local/portage/badc-custom-overlay
sync-type = git
sync-uri = https://github.com/rohithreddy/badc-custom-overlay.git
priority = 50
auto-sync = yes





This is a personal [Gentoo Portage Overlay](https://wiki.gentoo.org/wiki/Overlay). It mostly contains ebuilds of applications and libraries that I am/was interested to try on one of my Gentoo boxes or that solve a particular issue with an upstream ebuild.

Feel free to use any ebuild for your own purpose, however I might not be able to help you with any problems, as I'm not regularly using most of the packaged applications. Still every ebuild published here is in a fully functional condition at the time of upload.


### Installing the overlay

In order to manage the overlay, the package **app-portage/layman** must be installed into your environment:

```
emerge -av app-portage/layman
```

If the installation of _layman_ was successfully completed, enable custom overlays by uncommenting the following line in `/etc/layman/layman.cfg`:

```
overlay_defs : /etc/layman/overlays
```

Add this overlay by fetching its remote list as showed below:

```
wget -O /etc/layman/overlays/badc-custom-overlay.xml https://raw.githubusercontent.com/rohithreddy/badc-custom-overlay/master/overlay.xml
```

At this point you can execute:

```
layman -a badc-custom-overlay
```

Finally make sure that _emerge_ can find the ebuilds of the custom overlay:

```
echo "source /var/lib/layman/make.conf" >> /etc/portage/make.conf
```


### Updating the overlay

Keep the overlay up to date with:

```
layman -s badc-custom-overlay
```


### Removing the overlay

The process of removing this overlay from your Gentoo environment is quite straightforward:

```
layman -d badc-custom-overlay
rm /etc/layman/overlays/badc-custom-overlay.xml
```
