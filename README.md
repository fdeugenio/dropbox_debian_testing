# dropbox_debian_testing
Patch to dropbox *deb - solves libpango dependency error on libpango1.0-0

These instructions should allow you to create the deb package yourself, starting from the original version available on the Dropbox website.
Install the resulting package with sudo dpkg -i dropbox_2020.03.04_pangox_amd64.deb

$ mkdir drobo
$ dpkg-deb -R dropbox_2020.03.04_amd64.deb dropbox/
$ vim dropbox/DEBIAN/control 
# Edit libpango entry in "depends", by replacing:
# "libpango1.0-0 (>= 1.36.3),"
# with:
# "libpangox-1.0-0 (>= 0.0.0),"
$ dpkg-deb -b dropbox
$ mv dropbox.deb dropbox_2020.03.04_pangox_amd64.deb
# Voila`
